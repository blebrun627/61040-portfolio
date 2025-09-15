# Problem Set 1

**Exercise 1**

1. One of the invariants is that the count for any item can never be negative. A second would be that every item purchased should have an associated request regardless of count. I believe the second invariant is the most important because the count going negaative simply means you would get a little extra of something you wanted, but a purchaswe not being something on the registry means you'll be receiving an item that you didnt want at all which defeats the purpose of having a registry in the first place. The purchase action is most affected by this invariant but the invariant is preserved as purchase() checks that a request for the item exists.
2. The removeItem() action could break this invariant. There's a scenario where someone purchases an item from the registry and then the registry owner removes that item, which would then make that previously valid purchase "unwanted". There's a few ways to fix this problem. For one, changing the requires clause for removeItem() such that the action can only take place if no purchase of that item has happened yet. Additionally, if the owner of the registry really doesn't want that item anymore but its already been purchase, adding a decreaseCount() action so that at the very least they won't receive any more of that item. 
3. According to the concept actions, the registry can in fact be open and closed multiple times. A reason to do this would be if the registry owner wants to make several updates to the registry whetehr that be a sequence of addign items, removing items, or both. If someones making purchases during the time of these updates, one, it may decrease the likelihood of the new items being purchased and two, it opens the potential for the important invariant being broken if someone purchases an item before it can be removed. It's instead much easier to close the registry when making mass updates to avoid these issues.
4. No, it doesn't matter that there isn't an option to delete the registry. Most likely once the event has passed no one will be checking the registry and regardless the owner could always just permanently close the registry which would essentially have the same effect.
5. A common query from a registry owner would be checking what has already been purchased and by whom. A query from gift givers should be checking what current requests have a nonzero amount. 
6. The last line of the principle would have to be deleted as that's solely about the recipeient seeing which items have been purchased. Also in the state we could add an extra flag under the set of recipient for viewing that when toggled would determine whether or not the recipient could view the purchases. 
7. For both the User and the Item type, the actual program doesn't care about the specific fields that would describe them unlike with Registrys or Requests. Using a generic type is better in that specific situation when we want an object to carry multiple pieces of information but the specifics of it all aren't integral to the program we're writing. For example, Items is only ever used as a way to determine what object is being requested or purchased. It's not necessary for to know the exact name or price of the Item for the same functionality to hold so its more efficient to omit it and let that be packed up inside the Item generic type. 

**Exercise 2**

1. 
    &emsp;**state**\
        &emsp;&emsp;a set of Users with\
            &emsp;&emsp;&emsp;a username String\
            &emsp;&emsp;&emsp;a password String
2. 
    &emsp;**actions**\
        &emsp;&emsp;register(username: String, password: String): (user: User)\
        &emsp;&emsp;**requires** The username is not already taken by a different User\
        &emsp;&emsp;**effects** A new User is created with the given username and password<br /><br />
        &emsp;&emsp;authenticate (username: String, password: String): (user: User)\
        &emsp;&emsp;**requires** There exists a User with the given username and the password matches the one associated with that User\
        &emsp;&emsp;**effects** The User associated with that username is returned
3. The invariant would be there cannot be any Users with the same username. It's preserved because whenever we add a new User, we first check that there isn't an existing one with that same username to prevent from breaking the invariant.
4. To add in the email confirmation function, we're going to rewrite the concept with a few new features added in.<br /><br />
    &emsp;**concept** PasswordAuthentication\
    &emsp;**purpose** limit access to known users\
    &emsp;**principle** after a user registers with a username and a password,\
    &emsp;they can authenticate with that same username and password\
    &emsp;and be treated each time as the same user\
    &emsp;**state**\
        &emsp;&emsp;a set of Users with\
            &emsp;&emsp;&emsp;a username String\
            &emsp;&emsp;&emsp;a password String\
            &emsp;&emsp;&emsp;a email String\
            &emsp;&emsp;&emsp;a token String\
            &emsp;&emsp;&emsp;a confirmed Flag\
    &emsp;**actions**\
        &emsp;&emsp;register(username: String, password: String, email: String): (user: User, token: String)\
        &emsp;&emsp;**requires** The username is not already taken by a different User\
        &emsp;&emsp;**effects** A new User is created with the given username, email and password, a token is\
        &emsp;&emsp;generated that will also be assigned to User, and the confirmed flag is set to False. The generated\
        &emsp;&emsp;token will also be sent to the given email<br /><br />
        &emsp;&emsp;authenticate (username: String, password: String): (user: User)\
        &emsp;&emsp;**requires** There exists a User with the given username and the password matches the one\
        &emsp;&emsp;associated with that User\
        &emsp;&emsp;**effects** The User associated with that username is returned<br /><br />
        &emsp;&emsp;confirm(username: String, token: String)\
        &emsp;&emsp;**requires** There exists a User with the given username, their confirmed flag is False\
        &emsp;&emsp;and the inputed token matches the token associated with the user\
        &emsp;&emsp;**effects** The confirmed flag for the associated User is set to True

**Exercise 3**

Passwords vs. Personal Access Tokens

&emsp;**concept** PersonalAccessToken[User, Scope]\
&emsp;**purpose** provide an alternative to password based authentication for Github operations\
&emsp;**principle** a user create a new token on Github,\
&emsp;Github generates a random string and securly stores it\
&emsp;the user uses the token when authenticating for Git or API access\
&emsp;Github validates the token and grants the user permissions\
&emsp;the user can remove or regenerate the token at any time\
&emsp;**state**\
    &emsp;&emsp;a set of Tokens with\
        &emsp;&emsp;&emsp;an owner User\
        &emsp;&emsp;&emsp;a tokenString String\
        &emsp;&emsp;&emsp;a scope Scope\
        &emsp;&emsp;&emsp;an active Flag\
        &emsp;&emsp;&emsp;a date Date\
&emsp;**actions**\
    &emsp;&emsp;createToken(owner: User, scope: Scope, date: Date): (token: Token)\
    &emsp;&emsp;**requires** The owner exists\
    &emsp;&emsp;**effects** Creates a new token with the given owner, date, and scope, and with active set to True<br /><br />
    &emsp;&emsp;useToken (user: User, tokenString: String)\
    &emsp;&emsp;**requires** There exists a token with the given tokenString, it's active, it belongs to this user,\
    &emsp;&emsp;and it isn't expired\
    &emsp;&emsp;**effects** Authenticates user with permissions defined by the token's scope<br /><br />
    &emsp;&emsp;removeToken(token: Token)\
    &emsp;&emsp;**requires** The given token exists and is active\
    &emsp;&emsp;**effects** Sets the token's active flag to False<br /><br />
    &emsp;&emsp;regenerateToken(token: Token, date: Date): (newToken: Token)\
    &emsp;&emsp;**requires** The given token exists\
    &emsp;&emsp;**effects** Removes the originally token from the set of Tokens and replaces it with the new toke\
    &emsp;&emsp;created with the fields copied from the original Token but with the given expiration date.

PersonalAccessTokewns differ from PasswordAuthentication as the user has no control on what their token is. There's also the fact that the token automatically expires after a year of inactivity which users don't have to worry about with regular password. Another key difference is that Personal Access Tokens allows users to determine a scope of what their token will actually with others, while giving out your username and password is muhc more all-or-nothing and you have no control over what other are actually accessing. 

In terms of changing the GitHub site, I think it could be better to explain the difference between passwords and tokens more clearly at the very beginnign of the page fo users to better understand the pros and cons of using tokens over passwords. 

**Exercise 4**

**URL Shortener:**

&emsp;**concept** URLShortner[URL]\
&emsp;**purpose** provide short, more easily shareable links that redirect to the much longer, original links\
&emsp;**principle** a user supplies a URL\
&emsp;a shorter ending is generated or provided by the user\
&emsp;this new ending is linked with the longer URL\
&emsp;when anyone uses the shorter URL, they are automatically redirected to the longer URL\
&emsp;**state**\
    &emsp;&emsp;a set of Mappings with\
        &emsp;&emsp;&emsp;a link URL\
        &emsp;&emsp;&emsp;an ending String\
&emsp;**actions**\
    &emsp;&emsp;definedMapping(link: URL, ending: String)\
    &emsp;&emsp;**requires** The ending is not already in use and the link is valid\
    &emsp;&emsp;**effects** Creates a new mapping that links the given ending to the original link<br /><br />
    &emsp;&emsp;autoMapping (link: URL)\
    &emsp;&emsp;**requires** The link is valid\
    &emsp;&emsp;**effects** Creates a new mapping with a system-generated ending<br /><br />
    &emsp;&emsp;resolve(ending: String)\
    &emsp;&emsp;**requires** There exists a mapping with the given ending\
    &emsp;&emsp;**effects** Returns the original URL associated with this ending

**Notes** The algorithm to generate suffixes must ensure that there are no duplicates across URLs. 

**Conference Room Booking:**

&emsp;**concept** ConferenceRoomBooking[User, Room, Interval]\
&emsp;**purpose** allows users in an organization to reserve conference rooms and prvent double-bookings\
&emsp;**principle** a user requests a room at a specific time interval\
&emsp;the system confirms that the room is available\
&emsp;the booking is created and associated with the given user\
&emsp;that time interval is now blocked and other users cannot book the room at the same time\
&emsp;**state**\
    &emsp;&emsp;a set of Rooms with\
        &emsp;&emsp;&emsp;a name String\
    &emsp;&emsp;a set of Bookings with\
        &emsp;&emsp;&emsp;a room Room\
        &emsp;&emsp;&emsp;a requester User\
        &emsp;&emsp;&emsp;a time Interval\
&emsp;**actions**\
&emsp;**actions**\
    &emsp;&emsp;requestBooking(requester: User, room: Room, time: Interval)\
    &emsp;&emsp;**requires** The chosen room exists and is available for the entirety of the given time period\
    &emsp;&emsp;**effects** Creates a new booking with the given requester, room, and time<br /><br />
    &emsp;&emsp;cancelBooking(requester: User, booking; Booking)\
    &emsp;&emsp;**requires** The requester is the same as the one who created the booking\
    &emsp;&emsp;**effects** Removes the booking and makes the room available again during the removed booking time interval<br /><br />
    &emsp;&emsp;**effects** Returns the original URL associated with this ending

**Electronic Boarding Pass:**

&emsp;**concept** ElectronicBoardingPass[User, Manifest]\
&emsp;**purpose** allows passengers to present a digital boarind pass that updates automatically as their flight changes\
&emsp;**principle** an airline generates a boarding pass for a user linked to their flight\
&emsp;the pass contains all the user's indentifying and flight information\
&emsp;the pass can be added to the user's digital wallet\
&emsp;if any details of the flight change the pass is updatedL\
&emsp;the pass is scanned at boarding to verify the user's boarding\
&emsp;**state**\
    &emsp;&emsp;a set of Flights with\
        &emsp;&emsp;&emsp;a flight ID String\
        &emsp;&emsp;&emsp;a gate String\
        &emsp;&emsp;&emsp;a departure time Time\
        &emsp;&emsp;&emsp;a flight manifest Manifest\
    &emsp;&emsp;a set of Passses with\
        &emsp;&emsp;&emsp;a passenger User\
        &emsp;&emsp;&emsp;a flight Flight\
        &emsp;&emsp;&emsp;a pass ID String\
&emsp;**actions**\
    &emsp;&emsp;issuePass(passenger: User, flight: Flight): (pass: Pass)\
    &emsp;&emsp;**requires** The flight exists and the user appears on the flight's manifest\
    &emsp;&emsp;**effects** A new boarding pass is created and returned to the user<br /><br />
    &emsp;&emsp;updatePass(pass: Pass, flight: Flight)\
    &emsp;&emsp;**requires** The pass and flight exist, and the flight details have changed\
    &emsp;&emsp;**effects** The pass is updated with the new flight details<br /><br />
    &emsp;&emsp;deletePass(pass: Pass)\
    &emsp;&emsp;**requires** The pass exists\
    &emsp;&emsp;**effects** The pass is deleted and the user removed from the flight manifest associated with the pass<br /><br />
    &emsp;&emsp;validatePass(pass: Pass, flight: Flight)\
    &emsp;&emsp;**requires** The pass exists and the associated passenger is on the flight manifest\
    &emsp;&emsp;**effects** The passenger's right to board is confirmed

**Notes** This works if updates from the airline are basically automatic to ensure that the user's pass is always up to date and can be correctly validated.

