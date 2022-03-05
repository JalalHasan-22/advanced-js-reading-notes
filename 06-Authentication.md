# Authentication

Authentication is the process of recognizing a user’s identity. It is the mechanism of associating an incoming request with a set of identifying credentials.

when storing sinsitive data in the database; it is highly recommended that we use something called hashing, hashing a password for examole means that we use some algorithm to change the password string that will be stored in the database, so it will not be some plain text anymore.

there are many Cryptographic hash algorithms such as MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible.

But there are many problems with those kind of algorithims, and they are considered not secure enough.

Luckily for node.js users, we have bcrypt.

Bcrypt is a node.js A library to help you hash passwords. it can be used as a middleware with the login or signup functionality.
we use bcrypt.hash(password) in order to hash the password, and when a user logs in again; we use bcrypt.compare to compare between the value the user entered and the hashed password stored in the database.

### Review, Research, and Discussion

1.  **What a Singleton is anyway?**

singleton in software engineering is a design pattern that is used to restrict the instantiation of a class to one instance onyl. it is one of the twenty-three-well-known design patterns.

the singleton patterns is implemented by making the constructor of the class private allowing no more than one instance to be created, this sole instance of the class can be accessed by the "getInstance" method, which returns a pointer or a reference to this isntance.

logging is a singleton pattern implementation.

2. **Explain how the Singleton pattern can be used with Node modules, specifically with classes**

In Node.js we can use the singleton design pattern with the node modules and the easiest way to do it is to make the module of the class to export a new instance of the class, this way, a new instance will be created and saved in cache, and when we import this module, node.JS will handle exporting exactly the same instance that was created and exported the first time.

3. **If you were tasked with building a middleware system like Express uses, what approach might you take to construct/operate it?**

If I were to build a middleware system like Express, I would definetly consider using the singleton pattern as my approach, to make sure that my Application or server has exactly one "**_app_**" instance that is resposible of handling all the requests and responses that comes to the server.

### Vocabulary Terms

| Term                        | Defenition                                                                                                                                                                                                                                                                 |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Router Middleware           | Its a middleware that is applied to all routes in the application, we do this by importing the middleware and the write (app.use(middleware_name))                                                                                                                         |
| Dynamic Module Loading      | a mechanism by which a computer program can, at run time, load a library (or other binary) into memory, retrieve the addresses of functions and variables contained in the library, execute those functions or access those variables, and unload the library from memory. |
| Singleton Pattern           | a design pattern used in software engineering that limits the creation of instances of a certain class to only one instance                                                                                                                                                |
| CRUD -> REST Method Matches | I didn't really get the point of this term, please explain more of what is needed.                                                                                                                                                                                         |
| Mock Testing                | It provides you the ability to isolate and test your code without any interference of the dependencies and other variables like network issues and traffic fluctuations. keeping the testing process focused only on the actual functionality of the object.               |

#### Resources

1. [The Hacker News](https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html)

2. [Basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)

3. [Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
