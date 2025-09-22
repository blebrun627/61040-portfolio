# Problem Set 2

**Concept Questions**

1. To meaningfully be able to shorten any URL there is a set number of permutations possible before the URL starts becoming too long and the shortening function is useless. To delay this, different contexts are used that group possible URLS. In this way there can be duplicate nonces as long as they belong to different contexts. Therefore, the Context represents the shortURLBase as the base acts as a sort of grouping under which the generated shortened URLs can fall under.

2. The counter should be equal to the number of used strings under each context. If it were less than, it means we somehow generated too many shortenings or didnt properly account for one. If it were greater than, then it would mean we generated the same URL twice for the same context which would break the implied invariant that the strings under each context are unique. 

3. One advantage is that it would be much easier to share URLs with others by giving them a singular word instead of a sequence of characters. However the disadvantage is that this dramatically limits the amount of possible nonces generated per context which could force users to start using a different context instead of the one they may have been using for all their other links. 

&emsp;&emsp;&emsp;Updated Concept:\
    &emsp;&emsp;&emsp;&emsp;**concept** NonceGeneration [Context]\
    &emsp;&emsp;&emsp;&emsp;**purpose** generate unique dictionary words within a context\
    &emsp;&emsp;&emsp;&emsp;**principle** each generate returns a dictionary word not returned before for that context\
    &emsp;&emsp;&emsp;&emsp;**state**\
    &emsp;&emsp;&emsp;&emsp;a set of Contexts with\
        &emsp;&emsp;&emsp;&emsp;&emsp;a used word set of Strings\
    &emsp;&emsp;&emsp;&emsp;**actions**\
    &emsp;&emsp;&emsp;&emsp;&emsp;generate (context: Context) : (nonce: String)\
        &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**effect** returns a nonce that is a word from the english dictionary and not already used by this context

**Synchronization Questions**

1. The choice of argument is determined by what fields are actually required for the invocations to take place. In the case of the first Request.shortenURL, we don't care about what the target URL is because we're exclusively generating a short nonce and not creating any links. However in the second case, when we invoke register, we are creating a link between the new shortened URL adn the targetUrl. The only way to get access to the targetUrl is it being passed through the request, which is why we see a difference in the completions in these two calls based on the invocation.

2. From a readibility perspective, it wouldn't be good practice to use this convention in every case as it becomes confusing what parameter each argument corresponds with. This would make it harder to debug and also has the potential of confusing the program as well on how to interpret each input.

3. Generating a new nonce and registering a URL are dependent on a URL request being made. Setting the expiry is instead dependent on the URL request being completed. If its when was based on a URL request being made, it could try to set an expiry for an object that has yet to be created. Additionally, the when being UrlShortening.register already implies that a URL request was made at some point for register to have been called so its not necessary for it to be an additional when parameter. 

4. Neither the generate nor register syncs would take in a shortUrlBase as that corresponds to the domain name. Instead of that variable input, the subsequent program would just have the chosen domain hardcoded in. 

5. \
&emsp;**sync** expireResource \
    &emsp;&emsp;**when** ExpiringResource.expireResource (): (resource: shortUrl)\
    &emsp;&emsp;**then** UrlShortening.delete(shortUrl)\

**Extending the Design**

Concepts:

**concept** UsageCount[ShortUrl]\
**purpose** Keeps count of how many times a short Url is accessed\
**principle** After a successful lookup, the count for the given Url increases by 1\
Count can be accessed at any time\
**state**\
&emsp;a set of Tallies with \
&emsp;&emsp;shortUrl String\
&emsp;&emsp;count Number\
**actions**\
&emsp;startCount(shortUrl: String)\
&emsp;&emsp;**requires** no tally exists for ShortUrl\
&emsp;&emsp;**effects** creates a new tally with count = 0<br /><br /> 
&emsp;increase(shortUrl: String)\
&emsp;&emsp;**requires** tally for ShortUrl exists\
&emsp;&emsp;**effectes** increase count for ShortUrl by 1<br /><br />
&emsp;getCount(shortUrl: String): (count: Number)\
&emsp;&emsp;**requires** tally for ShortUrl exists\
&emsp;&emsp;**effects** returns the count of ShortUrl\

**concept** UrlOwner[ShortUrl, User]\
**purpose** Keeps track of who owns a shortUrl\
**principle** Attaches a user to a certain shortUrl\
**state**\
&emsp;a set of Pairings with \
&emsp;&emsp;shortUrl String\
&emsp;&emsp;owner User\
**actions**\
&emsp;link(shortUrl: String, owner: User)\
&emsp;&emsp;**requires** no owner exists for shortUrl\
&emsp;&emsp;**effects** owner linked to shortUrl<br /><br />
&emsp;checkOwner(shortUrl: String, requester: User): (linked: Boolean)\
&emsp;&emsp;**requires** a pairing exists for shortUrl\
&emsp;&emsp;**effects** returns true if the requester is the owner of the ShortUrl\

Syncs:\
** Assuming Request are abstract actions done by the user not included in concepts**

&emsp;**sync** register \
    &emsp;&emsp;**when**\
    &emsp;&emsp;&emsp;UrlShortening.register (): (shortUrl)\
    &emsp;&emsp;&emsp;Request.getUser (): (user)\
    &emsp;&emsp;**then** \
    &emsp;&emsp;&emsp; UrlOwner.link(shortUrl, owner: user)\
    &emsp;&emsp;&emsp;UsageCount.startCount(shortUrl)

&emsp;**sync** translate \
    &emsp;&emsp;**when** UrlShortening.lookup (shortUrl): (targetUrl)\
    &emsp;&emsp;**then** UsageCount.increase(shortUrl)\

&emsp;**sync** analyzeData \
    &emsp;&emsp;**when**\
    &emsp;&emsp;&emsp; Request.getAnalytics (shortUrl)\
    &emsp;&emsp;&emsp; Request.getUser (): (user)\
    &emsp;&emsp;&emsp; UrlOwner.checkOwner(shortUrl, requester: user): (linked)\
    &emsp;&emsp;**then** UsageCount.getCount(shortUrl)\

Modularity:

1. Allowing user to choose their own URL is already a compatible feature as their able to pass in a shortUrlSuffix. This would require a change to the register sync where instead you would get rid of generating a nonce and add the additional shortUrlSuffix parameter to Request.ShortenUrl

2. To use the "word as nonce" strategy, you could add an alternative generator for nonce called generateWord, that has essentially the same effect but it specifically pulls all nonces from a dictionary. 

3. Including the target URL in analytics may not be the best feature to add as multiple users could have a shortening to the same targetUrl and adding this feature would break the rule that analytics are only visible to the owner of the shortneing.

4. To make short Urls harder to guess would require elevating the standards of the shortening generated by nonce and adding different caveats to it to make the Url stronger. However, this wouldn't necessarily be a desirable function as Urls are usually shortened with the intent of making it easier to be used by other. Making the Urls harder to guess makes it seem like we're trying to decrease usage rather than make it more accesible to others.

5. Supporting analytics to unregistered users also wouldn't be desirable as analytics are supposed to be exclusively viewed by the owner of the Url shortening. If users aren't registered its much harder to keep track of who owns what and could lead to breaking a privacy barrier. 