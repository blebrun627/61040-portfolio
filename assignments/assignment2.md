# Assignment 2

**Problem Statement:**

&emsp;Problem Domain:\
&emsp;&emsp;Reading books &rarr; This entails reading new books, trading recommendations, and discussing plots with others. Reading has always been one of my favorite\
&emsp;&emsp;hobbies and something I tend to do whenever I need to destress. It also has a very large market with it being so accessible in many different forms. I think it's a\
&emsp;&emsp;really easy way to make connections and bond over a story that you enjoyed.

&emsp;Problem:\
&emsp;&emsp;Connecting with Readers &rarr; Despite the fact that we are all more online now and its very easy to communicate with the world around us, it can be difficult to\
&emsp;&emsp;find others that are interested in the same type of media as you. In most cases, people are only able to discuss what they're reading with a friend who started\
&emsp;&emsp;the book at the same time as them or if they've joined a designated bookclub. I often have moments where I read something incredibly interesting in a book and\
&emsp;&emsp;have no one to talk to about it or I'm forced to spoil the entire thing to a friend who will never read it so they can understand the emotions I'm experiencing. I\
&emsp;&emsp;think solving this problem could be very beneficial to the reading community and allow for more sharing of ideas about literature and media in general.  

&emsp;Stakeholders: 

&emsp;&emsp;1. Booksellers: With more commentary surrounding a book, there's a good chance for a fluctuation in ratings which can impact sales at book stores.\
&emsp;&emsp;2. Readers: These are the direct users, who benefit from the experience of using the software\
&emsp;&emsp;3. Authors/Publishers: In the same way as booksellers, if the commentary on a book causes the ratings to increase, it could lead to more sales of said book\
&emsp;&emsp;which increases the profits of authors & publishers.<br /><br />
&emsp;&emsp;Readers are the most directly affected, since they often want to share thoughts and reactions to books but may not know others who have read the same title. &emsp;&emsp;Without a community, the reading experience can feel less engaging and isolating. Booksellers also have a stake in this problem, as discussions often spark &emsp;&emsp;new purchases, and stronger reading communities can encourage repeat customers. Authors and publishers benefit as well, since word-of-mouth remains one &emsp;&emsp;of the most powerful drivers of book sales and reputation, and easier reader connections could amplify visibility for their work.

&emsp;Evidence & Comparables: 

&emsp;&emsp;1. [How to Find an Online Book Club—or Start One Yourself](https://www.wired.com/story/how-to-find-or-start-online-book-club) : Highlights how digital book clubs like Bookclubs, BookMovement, and Fable make connecting with &emsp;&emsp;readers easier—yet choosing the right one can still be a task.\
&emsp;&emsp;2. [What Makes Book Clubs So Important?](https://medium.com/counterarts/what-makes-book-clubs-so-important-0c80cf63df66) : Reflects on the emotional value of book discussions.\
&emsp;&emsp;3. [Anobii](https://www.anobii.com/en/about): A reader social network allowing users to catalog, review, and discuss books—popular in parts of Europe.\
&emsp;&emsp;4. [Bookclubs.com](https://bookclubs.com/about) (formerly Bookclubz) : enables organized book clubs, both online and in person, including messaging, voting, scheduling, and discussion &emsp;&emsp;guides.\
&emsp;&emsp;5. [The Importance of Finding a Reading Community](https://blog.getbookly.com/reading-community/): Discusses how reading communities enhance motivation and enjoyment, therefore necessitating\
&emsp;&emsp;connection to get the most out of your reading experience.\
&emsp;&emsp;6. [Building and Engaging with Online Platforms and Community as an Author](https://mybookcave.com/authorpost/building-author-platform-online-community/): Describes how authors and readers use platforms to interact, showing growing &emsp;&emsp;demand for discussion spaces. 

**Application Pitch:**

&emsp;Name: LitLink

&emsp;Motivation: This app solves the problem of readers lacking immediate, meaningful ways to connect with others who are experiencing the same books and genres, &emsp;enabling real-time discussion, discovery, and community.

&emsp;Key Features:

&emsp;&emsp;1. In-Line Commenting: When the user opens the book their reading, each seperate paragraph will have an optional comment section where readers can leave\
&emsp;&emsp;&emsp;their own response or reply & react to other. In adding this feature, readers are able to have real-time discourse with others reading the story as well as\
&emsp;&emsp;&emsp;receiving immediate feedback on other reactions to a certain section of writing. This feature most directly affects readers as by reading comments and\
&emsp;&emsp;&emsp;leaving their own responses they're able to find like-minded readers they could potentially connect with. Highly commented books could be a sign of\
&emsp;&emsp;&emsp;increased demand for a specific title which could affect sales of different booksellers. Authors could also use these comment sections to get more feedback\
&emsp;&emsp;&emsp;on their audience's opinion on their book, which would offer more insight than a normal review. \
&emsp;&emsp;2. Instant Discussion Matchmaking: After finishing a book, users will instantly be paired with others who recently completed the same title. From there they\
&emsp;&emsp;&emsp;have the ability to immediately reach out to this other user to discuss their thoughts and opinions on the book. This significantly lowers the barrier to entry of\
&emsp;&emsp;&emsp;discussion compared to searching for book clubs or other forums. In doing so it  helps readers feel less isolated as they get to share their experience. This\
&emsp;&emsp;&emsp;also has the most apparent benefit to readers as they'll feel less isolated as this feature reduces friction to meaningful conversations. The more a specific\
&emsp;&emsp;&emsp;book is being discussed, there's a good chance it will spark more or renewed interest in it which could increase sales and benefit booksellers. This also\
&emsp;&emsp;&emsp;benefits an authors notoriety as extended discussion of a book means that it stays relevant longer and has more of a chance to gain popularity.\
&emsp;&emsp;3. Direct Messaging: After finding an interesting user profile or being automatically matched with someone after finishing a book, user's are able to\
&emsp;&emsp;&emsp;communicate by opening a new chat and sending messages. This is much more personalized and convenient than alternative methods. For example, with a\
&emsp;&emsp;&emsp;bookclub you generally have to wait for a specific time and date to start a discussion, whereas starting a chat is instantaenous and is only bound by the other\
&emsp;&emsp;&emsp;users response time. Similarly with other online forums, you're talking with a mass group of people at once whereas by direct messaging you can get a 1-on-1\
&emsp;&emsp;&emsp;or smaller group experience that allows you to form a better connection and not have your opinions get lost among hundreds of others. This benefits readers\
&emsp;&emsp;&emsp;as it makes reading a more social experience and gives them the opportunites to form more connections. In forming these connections, there's a higher\
&emsp;&emsp;&emsp;likelihood that people will begin to recommend more content to each other which benefits booksellers. Similarly to discussion matchmaking, authors benefit\
&emsp;&emsp;&emsp;from the sustained engagement with their work which allows them to stay relevent.

**Concept Design:**

*Concept Specifications*

&emsp;**concept** BookReading[User, Book, Section]\
&emsp;**purpose** Lets users read a book in-app and track their progress\
&emsp;**principle** \
&emsp;&emsp;a user opens a book from their library\
&emsp;&emsp;the book is divided into sections (e.g. paragraphs, pages, chapters) with a defined order\
&emsp;&emsp;the user moves through the sections, and their position is stored\
&emsp;&emsp;when finished reading, the book is marked completed\
&emsp;**state**\
&emsp;&emsp;a set of Libraries with \
&emsp;&emsp;&emsp;owner User\
&emsp;&emsp;&emsp;a set of Books\
&emsp;&emsp;a set of BookStructures with \
&emsp;&emsp;&emsp;a book Book\
&emsp;&emsp;&emsp;section list of Section\
&emsp;&emsp;a set of Progresses with\
&emsp;&emsp;&emsp;a reader User\
&emsp;&emsp;&emsp;a book Book\
&emsp;&emsp;&emsp;a currentPlace Section\
&emsp;&emsp;&emsp;a finished Flag\
&emsp;**actions**\
&emsp;&emsp;addToLibrary(owner: User, book: Book)\
&emsp;&emsp;&emsp;**requires** book is not already in owner's library\
&emsp;&emsp;&emsp;**effects** add book to owner's library<br /><br />
&emsp;&emsp;openBook(reader: User, book: Book)\
&emsp;&emsp;&emsp;**requires** book is in reader's library\
&emsp;&emsp;&emsp;**effects** if a Progress exists for the reader and book already, do nothing\
&emsp;&emsp;&emsp;&emsp; else create Progress with currentPlace being the first section of the book and finished = false<br /><br />
&emsp;&emsp;jumpTo(reader: User, book: Book, section: Section)\
&emsp;&emsp;&emsp;**requires** set Progress.currentPlace to section\
&emsp;&emsp;&emsp;**effects** <br /><br />
&emsp;&emsp;nextSection(reader: User, book: Book)\
&emsp;&emsp;&emsp;**requires** Progress exists for the reader and book and a subsequent section exists for the book\
&emsp;&emsp;&emsp;**effects** currentPlace is set to the next section in the book's section list<br /><br />
&emsp;&emsp;markFinished(reader: User, book: Book)\
&emsp;&emsp;&emsp;**requires** Progress exists for the reader and book, and finished = false\
&emsp;&emsp;&emsp;**effects** set finished = true<br /><br />
&emsp;&emsp;resetProgress(reader: User, book: Book)\
&emsp;&emsp;&emsp;**requires** Progress exists for the reader and book\
&emsp;&emsp;&emsp;**effects** set currentPlace to the first section of the book and finsihed = false<br /><br />
&emsp;&emsp;removeFromLibrary(owner: User, book: Book)\
&emsp;&emsp;&emsp;**requires** book is in the owner's library\
&emsp;&emsp;&emsp;**effects** remove the book from the owner's library and remove Progress for the owner and book if it exists

&emsp;**concept** Commentary[User, Book, Section, Text, ReactionType]\
&emsp;**purpose** Allows readers to comment, reply, and react to parts of a book\
&emsp;**principle** \
&emsp;&emsp;Every section of the book has an associated discussion thread.\
&emsp;&emsp;Users can add comments, reply to others, and leave reactions\
&emsp;**state**\
&emsp;&emsp;a set of Threads with \
&emsp;&emsp;&emsp;a book Book\
&emsp;&emsp;&emsp;a section Section\
&emsp;&emsp;&emsp;a set of Comments\
&emsp;&emsp;a set of Comments with\
&emsp;&emsp;&emsp;an author User\
&emsp;&emsp;&emsp;a body Text\
&emsp;&emsp;&emsp;a parent Comment?\
&emsp;&emsp;&emsp;a set of Reactions\
&emsp;&emsp;a set of Reaction with\
&emsp;&emsp;&emsp;a reactor User\
&emsp;&emsp;&emsp;a target Comment\
&emsp;&emsp;&emsp;a type ReactionType\
&emsp;**actions**\
&emsp;&emsp;postComment(author: User, book: Book, section: Section, body: Text): (comment: Comment)\
&emsp;&emsp;&emsp;**requires** section belongs to the book\
&emsp;&emsp;&emsp;**effects** if Thread already exists for book and section, add a new comment to it\
&emsp;&emsp;&emsp;&emsp; else create a new Thread, then add the comment. Return the comment<br /><br />
&emsp;&emsp;reply(author: Author, parent: Comment, body; Text): (comment: Comment)\
&emsp;&emsp;&emsp;**requires** parent exists\
&emsp;&emsp;&emsp;**effects** create a new Comment with parent = parent in the same thread as the parent. Return the comment<br /><br />
&emsp;&emsp;react(reactor: User, target: Comment, type: ReactionType): (reaction: Reaction)\
&emsp;&emsp;&emsp;**requires** target exists and there's no existing reaction with (reactor, target, type)\
&emsp;&emsp;&emsp;**effects** creates a new Reaction with reactor, target and type, then attaches it to target. Return the reaction<br /><br />
&emsp;&emsp;deleteComment(requestor: User, target: Comment): (?)\
&emsp;&emsp;&emsp;**requires** target exists and requestor is the author of the target\
&emsp;&emsp;&emsp;**effects** remove target and all its decendant replies for its Thread

&emsp;**concept** Profiles[User, Genre, Book]\
&emsp;**purpose** Creates a representation of each reader's identity, interests, and history\
&emsp;**principle** \
&emsp;&emsp;Each user has a profile that includes genres they enjoy, books they've completed and book they'r still reading\
&emsp;&emsp;this profile helps others learn about them and is used for other features like matching & recommendations\
&emsp;**state**\
&emsp;&emsp;a set of Profiles with \
&emsp;&emsp;&emsp;an owner User\
&emsp;&emsp;&emsp;a set of Genres\
&emsp;&emsp;&emsp;a set of finishedBooks Book\
&emsp;&emsp;&emsp;a set of currentBooks Book\
&emsp;**actions**\
&emsp;&emsp;createProfile(owner: User)\
&emsp;&emsp;&emsp;**requires** owner does not already have a profile\
&emsp;&emsp;&emsp;**effects** creates a new Profile with empty genres, finishedBooks, and currentBooks<br /><br />
&emsp;&emsp;addGenre(owner: User, genre: Genre)\
&emsp;&emsp;&emsp;**requires** owner has a Profile\
&emsp;&emsp;&emsp;**effects** adds genre to owner's genres<br /><br />
&emsp;&emsp;removeGenre(owner: User, genre: Genre)\
&emsp;&emsp;&emsp;**requires** owner has a Profile and genre is one of their genres\
&emsp;&emsp;&emsp;**effects** remove genre form owner's genres<br /><br />
&emsp;&emsp;addCurrentBook(owner: User, book: Book)\
&emsp;&emsp;&emsp;**requires** owner has a profile and book is not in currentBooks or finsihedBooks\
&emsp;&emsp;&emsp;**effects** add book to owner's currentBooks<br /><br />
&emsp;&emsp;removeCurrentBook(owner: User, book: Book)\
&emsp;&emsp;&emsp;**requires** owner has a Profile and book in currentBooks\
&emsp;&emsp;&emsp;**effects** remove book from owner's currentBooks<br /><br />
&emsp;&emsp;addFinsihedBook(owner: User, book: Book)\
&emsp;&emsp;&emsp;**requires** owner has a Profile and book in currentBooks\
&emsp;&emsp;&emsp;**effects** add book to owner's finsihedBooks

&emsp;**concept** Matching[User, Book, Genre]\
&emsp;**purpose** connect readers who recently finished the same book\
&emsp;**principle** \
&emsp;&emsp;When a user finishes a book, the system look for others who did thre same recently\
&emsp;&emsp;users can accept or decline these matches\
&emsp;**state**\
&emsp;&emsp;a set of Matches with \
&emsp;&emsp;&emsp;a userA User\
&emsp;&emsp;&emsp;a userB User\
&emsp;&emsp;&emsp;a book Book\
&emsp;&emsp;&emsp;an active Flag\
&emsp;**actions**\
&emsp;&emsp;generateMatches(owner: User, book: Book): (suggested: set of Matches)\
&emsp;&emsp;&emsp;**requires** owner has a Profile and at leaast one finished book\
&emsp;&emsp;&emsp;**effects** creates a new match with userA = owner, userB = other, book = book, active = true\
&emsp;&emsp;&emsp;&emsp;this excludes any pairing that already have a match for book. Returns the set of new Matches <br /><br />
&emsp;&emsp;acceptMatch(owner: User, match: Match)\
&emsp;&emsp;&emsp;**requires** match exixts and owner is either userA or userB and active = true\
&emsp;&emsp;&emsp;**effects** set active = True<br /><br />
&emsp;&emsp;rejectMatch(owner: User, match: Match)\
&emsp;&emsp;&emsp;**requires** match exists and owner is either userA or userB and active = true\
&emsp;&emsp;&emsp;**effects** set active = false\

&emsp;**concept** Messaging[User, Text]\
&emsp;**purpose** lets reader talk directly in private chats or groups\
&emsp;**principle** \
&emsp;&emsp;Once users connect through matching or browsing profiles, they can stat a private conversation\
&emsp;&emsp;chats store message history until users leave or are blocked\
&emsp;**state**\
&emsp;&emsp;a set of Chats with \
&emsp;&emsp;&emsp;participants set of User\
&emsp;&emsp;&emsp;messages list of Message\
&emsp;&emsp;a set of Message\
&emsp;&emsp;&emsp;an author User\
&emsp;&emsp;&emsp;a body Text\
&emsp;&emsp;a set of Blocks\
&emsp;&emsp;&emsp;blocker User\
&emsp;&emsp;&emsp;blocked User\
&emsp;**actions**\
&emsp;&emsp;startChat(creator: User, participants: set of User): (chat: Chat)\
&emsp;&emsp;&emsp;**requires** at least 2 participants and owner is a participant and there is no blocked pair among any of the participants\
&emsp;&emsp;&emsp;**effects** create a new Chat with participants and an empty messages list. Return the chat<br /><br />
&emsp;&emsp;sendMessage(chat: Chat, author: User, body: Text): (message: Message)\
&emsp;&emsp;&emsp;**requires** chat exists and author is a particpant in the chat\
&emsp;&emsp;&emsp;**effects** append a new message to the chat's message list. Return the new message<br /><br />
&emsp;&emsp;leaveChat(chat: Chat, leaver: User)\
&emsp;&emsp;&emsp;**requires** chat exists and leaver is one of the participants\
&emsp;&emsp;&emsp;**effects** remove leaver from the chat's participants<br /><br />
&emsp;&emsp;blockUser(requester: User, target: User)\
&emsp;&emsp;&emsp;**requires** requester is not the target and a block does not already exist \
&emsp;&emsp;&emsp;**effects** create a new Block with blocker = requester and blocked = target. Remove requester from any chats containing both them and the target\

*Syncs*

**sync** recordFinish\
**when** BookReading.markFinished (reader, book)\
**then** \
&emsp;Profiles.addFinishedBook(owner: reader, book)\
&emsp;Profiles.removeCurrentBook(owner: reader, book) <br /><br />

**sync** suggestMatchesOnFinish\
**when**\
  BookReading.markFinished (reader, book)\
  Profiles.addFinishedBook (owner: reader, book)\
**then** Matching.generateMatches (owner: reader, book)<br /><br />

**sync** addNewBook\
**when** BookReading.openBook (reader, book)\
**then** Profiles.addCurrentBook (owner: reader, book)<br /><br />

**sync** openChatOnAccept\
**when** Matching.acceptMatch (owner, match)\
**then** Messaging.startChat (creator: owner, participants: {match.userA, match.userB})<br /><br />

**sync** blockCleanup\
**when** Messaging.blockUser (requester, target)\
**then**\
  Messaging.leaveChat (chat: each chat with participants ⊇ {requester, target}, leaver: requester)\
  Matching.declineMatch (owner: requester, match: each active match between requester and target)<br /><br />

**sync** libraryCleanup\
**when** BookReading.removeFromLibrary (owner, book)\
**then**\
  Profiles.removeCurrentBook (owner, book)\

*Note*

All five concepts work together to cover the main functions of the app: reading a book, sharing reactions, finding people with similar interests, and chatting with them. BookReading is where users actually read inside the app, with progress tracked section by section (like pages or chapters). Commentary plugs into that by letting people leave comments, replies, or reactions tied to specific parts of the book, so the conversation stays grounded in the text. Profiles give each user an identity including genres they like, books they’re in the middle of, and books they’ve finished. This info is what Matching uses to suggest new connections, specifically when two people finish the same book around the same time. If a match looks good and gets accepted, Messaging makes it possible to carry on a private or small-group conversation, and blocking here also shuts down any unwanted matches or chats. Together, these concepts make the app social and interactive without losing sight of the reading experience. For types: Section just means whatever unit the book is broken into (pages, paragraphs, or chapters), Text is user-written stuff like comments or messages, ReactionType is a fixed set of reactions (like 👍 or ❤️), and Genre is a simple category label. User and Book are shared across all the concepts and mean the same thing everywhere.

**UI Sketches**

![Home Page](assets/home.jpeg)

![Profile](assets/own_profile.jpeg)

![Other User Profile](assets/other_profilet.jpeg)

![Opened Book](assets/open_book.jpeg)

![Comments Section](assets/comments.jpeg)

![Messaging](assets/messaging.jpeg)

**User Journey**

Maria is a college student who enjoys reading to unwind from classes. One evening she opens Circe by Madeline Miller in the app (BookReading) and settles into the last few chapters. The app keeps track of her place as she goes, and when she reaches the end, she taps to mark the book complete.

Right away, her profile updates (Profiles) and a list of other readers who also just finished Circe appears (Matching). One name, Sam, stands out because they share a few favorite genres. Maria accepts the match, curious to see what Sam thought.

Still buzzing from the ending, she scrolls back to an earlier scene that stuck with her. Beneath that passage is a thread of comments where other readers have shared their reactions (Commentary). She adds her own thoughts, and not long after, someone responds.

Later, Maria also decides to explore outside of her matches. She searches the app’s directory of profiles (Profiles) and finds another reader who has recently finished several books she’s planning to pick up next. She opens a chat with them directly (Messaging), starting a conversation without needing a match first.

What could have been a quiet, solitary finish turns into multiple conversations. Instead of closing the book with no one to talk to, Maria finds herself part of a community that’s just as excited as she is.