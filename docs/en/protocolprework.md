# Pre-work of Protocol
Discussions within working groups on the different protocols and infrastructures currently in use and it is planned to make it more useful and secure for users by making various arrangements and additions in line with the joint decisions made.

The recommendations for the 3 main issues to be handled in the first phase are as follows:

- ## Digital Identity Database <span style="color:red">(diDb)</span>

    ["Decentralized Identity (did)"](https://www.w3.org/TR/did-core/) standard, which is approved and supported by [W3C](https://www.w3.org/), is the basic idea of this database.

    Due to the "minimum amount and fast data transfer", which is one of the important issues of the Memoristik project, some modifications can be made to the existing "did" structure, and Protobuf or alternative systems can be used instead of text-based JSON.

    The database to be created for real person and corporate identities will be kept on the Blockchain, and identities of everything else will be kept on the Merkle Tree and their communication with each other will be ensured.
    (The reason why Blockchain is preferred for individuals is explained in the ["Digital User Identity Database"](#digital-user-identity-database-didme) section. Changes can be made according to the decision of the Discussion and Working Groups).


    One of the priorities is to ensure that a "unique" identification number for any object or subject is created according to the standards to be determined.

    To take the example of "Git"[^1],

    [^1]: "Git" seems to be almost ready for use with some modifications and additions, and the HASHing infrastructure is available even if a different Merkle Tree is decided for the project database. Even simpler solutions such as MD5 can be used, since the main purpose of giving an ID number is not security and can be decrypted by anyone. The important thing is to avoid collision.


    >"Doctor Who" -> "33f7107b0566df9c4500ba05a32bd78a0360e2a1"

    We can create a fixed instance ID number.

    This identification number we have obtained stands out, "on its own and unique" and can be used wherever it will be incorporated, once added to diDb, all references to the subject or object can now be easily linked to this ID number.

    Let's expand on the same example and create some "Headers" in "List" format and get their ID numbers from git again,
    
    > "(List) Language" -> "f595be573723b6e7aadccc36192fcc33a8a5547b"
    >
    > "(List) Lisan" -> "e8a2b31e17e7a279fad38eec9c3acd3508d3aecd"
    >
    > "(List) TV Series" -> "e0164832424ef822e2713fe01dc3a56b2b0e00912d"
    >
    > "(List) TV Dizileri" -> "c01830f432a3accafa83bcc548ec947b10caa91e"
    >
    > "(List) Soundtrack" -> "099287d6456509d139a65c4e07cf1abb56873721"
    >
    >"(List) Book" -> "68c2d94ee2d424a3204c2366bd5180de67972c17"
    >
    >"(List) Broadcasting Platform" ->"c6baf462ed7f13c32e92c48163eec785a4f3c4a3"

    Let's add a few identification numbers that we can use in the first phase,

    >"English" -> "fb54c64e2c893efc35e89dfdf1192d380cba9fb5"
    >
    >"Türkçe" -> "b51132e2ea5faf8253cc594cd14a245dfb68a197"

    Now we have some data that we can quickly query by ID numbers. Using the Merkle Tree structure, we can synchronize them (Language=Language) and make additions under the lists (Language/Language -> English/Turkish -> TV Series/TV Series).

    With this content we have, users will be able to follow something like this:
    
    When there's an update on "Doctor Who",

    - When a new Soundtrack album is released or a new track is added to the Doctor Who soundtrack,
    - When a new book is published, or a book just about Doctor Who,
    - When a new movie/series arrives on the streaming platform I follow,
    - When Doctor Who was added to one of the streaming platforms I follow,
    - When Turkish content is published,
    - When a Turkish broadcast is added to TV series,
    - When the soundtrack album of an artist I follow comes out, etc.

    The examples we have given so far mostly consist of "Core Database" operations that do not require much users to add data and have fixed and clear contents.

    Providing content access through ID numbers is important as it can be easily divided into distributed servers. In this way, faster access can be provided without the need to retrieve all textual data.

    Users can create their own private or public lists using the identity data or lists created in the Core Database, or they can make use of lists prepared by others.

    For example,

    - Personal lists of movies, music, books, etc,
    - Activities,
    - Focused lists on a specific topic,
    - Adding new items to other lists,
    - To be able to filter as much data as they want to use and create new lists,

    Lists with the same name created by users will have different ID numbers, both to identify
    who created them and to avoid conflicts,

    >(Memoristik User) TV Series" -> "3388ccadcaecab0383f1cb9bc6a8e9e3043063b7"
    
    (For more example uses: Use Cases and Examples OOOOOOOOO)

- ## diDb Adaptation

    One of the most important objectives of the project is to improve existing protocols and services to enable access to the diDb system over different platforms.

    The technical infrastructures that can be used are to be discussed and decided by the system developers, an example usage will be something like this:

    On Markdown/HTML Documents,

    **{@personname}** : For people who have acquired a Fixed ID and have a diDb record,

    **{@#personname}** : To create hashtags for people with the ID {@personname},

    **{#topic}** : To create a hashtag on any topic and get data from all (supporting) platforms with a diDb link,

    **{!topic}** : to access the main topics created in the Core Database in diDb,

    For example, for a sentence like this that a user encounters on any website after making adjustments to the software they are using,

    "{#doctorwho} 60 years old..."

    The link on the page becomes personalized, from diDb, for example, it can list only the "platform of release, day of release" information,
    depending on the software it uses, a pop-up may open when you click on the link.

    Or it can add a query like {!music:band:megadeth:tour:turkey} to its notifications and wait.

    The first 3 data in the last example may be taken from the Core Database and the "tour" data may be taken from a different list. The source of the "tour" data can be determined by the user, for example directly from the band or from a trusted fan.

- ## Digital User Identity Database <span style="color:red">(diDMe)</span>

    **(Fixed ID & Access Card, People & Groups)**

    "Digital Wallets" and "Verifiable Identities", accelerated with blockchain technology, are currently working in a limited way within the limits of the environment in which they are used.

    The aim of the diDMe sub-project of the Memoristik Project is to make the existing wallets and verifiable identities accessible securely and from any platform. For now, it is considered to be developed on the Blockchain for reasons such as Security and Easy access.

    These identities which are going to be created on the diDMe database will include the right to remain anonymous, they will send only as much information as necessary to the requesting parties and will be completely under the user's own control.

    Since the security issue is very important for this database, it is planned to be carried out by a working group focused solely on this issue until it is ready for use.

    When the intended goal is achieved, users will be able to organize all their content and data in the way they want, synchronized across all platforms using the system simultaneously.

    As a sample use case, Users can keep all kinds of personal data such as

    - Phone No
    - Email
    - Web address
    - Avatar
    - Home address
    - CV etc.

    They will only need to give **{@username}** information to the person they want to communicate with.

    They will have all kinds of restrictions on this data, such as showing a certain amount of it to the other person. Any changes made will be reflected to the other party simultaneously.

    For example, when an e-mail or phone number changes, no one will have to be notified.

    Likewise, for different social media accounts, it will not be necessary to write each one individually.
    
    There can also be different uses for organizations, such as {@organization name/contact}, {@organization name/customer representative} for quick access to their
    customers.
    
    Real identities that have been verified using the diDMe system and through trusted institutions, hashtags created with their own names by communicating with diDb may also be linked together, making it easier for users to track themselves.

    > (diDMe)/{@memoristik} &lt;-> (diDb){#memoristik}