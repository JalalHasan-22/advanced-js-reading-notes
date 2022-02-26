# Readings: Data Modeling

Data modeling is the process of creating a simplified daigram of a software system and the data elements it contains, using text and symbols to represent the data and how it flows. Data models provide a blueprint for designing a new database or reengineering a legacy application. Overall, data modeling helps an organization use its data effectively to meet business needs for information.

There are three different types of data modeling:

1. conceptual data model: it is the high-level visualization of the business or analytics processes that a system will support, the main audience of this model are the business executives, to help them see how a system will work and ensure that it meets business needs.

2. logical data model: after the conceptual model is finished, it can be used to create a less-abstract logical model. it shows how entities are related and describe the data from a technical perspective. this model defines data structers and provide details on attributes, keys, data types and other characteristics.

3. physical data model: the logical model servers as the basis for the creation of the physical model. it is specific to the database management system or application software that will be implemented.

### Data modeling techniques

1. Hierarchical data modeling
2. Network data modeling
3. Relational data modeling
4. Entity-relationship data modeling
5. Dimensional data modeling
6. Object oriented data modeling

[Resourece](https://searchdatamanagement.techtarget.com/definition/data-modeling#:~:text=Data%20modeling%20is%20the%20process,or%20reengineering%20a%20legacy%20application.)

## Review, Research, and Discussion

1. ### Name 3 advantages to Test Driven Development

   a. it detects bugs before the production stage.
   b. reduces the amount of debugging the developers have to do.
   c. it makes the code more organized, and easy to maintain.

2. ### In what case would you need to use beforeEach() or afterEach() in a test suite?

   for example, if we are testing for a console log and we don't need to flood the console with the actual console.log output, we can use **beforEach** to add a **_mockImplementation_** before each test case to only check if the console.log method was called without actually outputting to the console during the tests.
   the opposite is achieved by using **mockRestore** method **_afterEach_** or **_afterAll_** test cases to negate this process and restore the (non-mocked) implementation.

3. ### What is one downside of Test Driven Development

   a. It slows down the development process.
   b. Challenging to support and maintain.
   c. It is difficult to learn.
   [Resource](https://fortegrp.com/test-driven-development-benefits/)

4. ### What’s the primary difference between ES6 Classes and Constructor/Prototype Classes?

> form MDN: JavaScript classes, introduced in ECMAScript 2015, are primarily syntactical sugar over JavaScript's existing prototype-based inheritance. The class syntax does not introduce a new object-oriented inheritance model to JavaScript.

    I believe that the main difference will be that Classes can’t be called without new, but functions intended as constructors can.

5.  ### Why REST?
        Because it is easy to uderstand, provides faster data interchange format, it makes chaching easier and it is flexible
    [Resource](https://www.freecodecamp.org/news/benefits-of-rest/#:~:text=REST%20aims%20to%20make%20caching,usually%20treat%20them%20as%20such.)

## Vocabulary Terms

| Term                              | Definition                                                                                                                                                                                                                                                                                                                                                                                                |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| functional programming            | the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects.                                                                                                                                                                                                                                                                                      |
| object-oriented programming (OOP) | is a programming paradigm that relies on the concept of classes and objects. It is used to structure a software program into simple, reusable pieces of code blueprints (usually called classes), which are used to create individual instances of objects.                                                                                                                                               |
| class                             | an abstract blueprint used to create more specific, concrete objects. Classes often represent broad categories, like Car or Dog that share attributes.                                                                                                                                                                                                                                                    |
| super                             | The super Keyword is used to access and call functions on an objects parent                                                                                                                                                                                                                                                                                                                               |
| this                              | In most cases, the value of this is determined by how a function is called (runtime binding). It can't be set by assignment during execution, and it may be different each time the function is called. the this keyword usually reffers to the object that called the function, but in es5, the bind method was introduced to set the value of the function's **_this_** regardless of how it is called. |
| Test Driven Development (TDD)     | a software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases.                                                                                                                                                                        |
| Jest                              | a JavaScript testing framework with a focus on simplicity and support for large web applications. It works with projects using Babel, TypeScript, Node.js, React, Angular, Vue.js and Svelte.                                                                                                                                                                                                             |
| Continuous Integration (CI)       | the practice of automating the integration of code changes from multiple contributors into a single software project.                                                                                                                                                                                                                                                                                     |
| REST                              | REpresentational State Transfer, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other. REST-compliant systems, often called RESTful systems, are characterized by how they are stateless and separate the concerns of client and server.                                                                    |
| Data Model                        | an abstract model that organizes elements of data and standardizes how they relate to one another and to the properties of real-world entities.                                                                                                                                                                                                                                                           |

## Preview

1. Which 3 things had you heard about previously and now have better clarity on?

   a. RESTful API. <br />
   b. Test case, and automated testing in general.<br />
   c. Middleware<br />

2. Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

   a. NoSQL and collections. <br />
   b. data models and moduling techniques.<br />
   c. data normalization.<br />

3. What are you most excited about trying to implement or see how it works?

- how to design and implement a nosql database, and whar is a database management system and what is it used for ?

---

## SQL vs NoSQL

In the word of databases, we have two main types, the **_SQL_** & **_NOSQL_**

1. SQL: It stands for structured query language, where you can use specific queries to perform actions on the data in the database. This type of databases sorts data in a table form containing n number of row, where each row represents a record of data. the data have a schema whic is some sort of structure that you need to adhere to. for example, if you have a field in your schema called name, then all of the record must have the name field associated with it, it can be empy yes, but it has to be there. this type of databases relies on what's called relations, which means that you can asoociate records stored in different tables by building relations, this is very useful in the case that your application is having a lot of write requests, the data will be stored in one place, so you don't have to update it but only in that table.
   SQL databses can only be scalled vertically, which in terms means that we can only increase the computing power for the database server, which means that scalling is limited to the amount of resources or computing power that the server have.
   some examples on SQL databases are: MYSQL, Oracle, IBM i, MS-SQL, MariaDB and many more.

2. NOSQL: It stands for non-relational databases, where we have zero or very few relations between data collections, yes collections, not tables. this type of databases relies on storing huge amounts of data all in one place in collections of key value pairs, graph databases, documents or wide-column stores.
   in the case of NOSQL databases, it can be scanned in both horizontally and vertically, horizontal scalling means adding more database servers to reduce the load on each single one of them. this type of databases is great when you have alot of read requests on the database server. some examples on NOSQL databases are: MongoDB, CouchDB, AWS DynamoDB and many more.

When it comes to decide what type of database shall I use for my application, there is no correct answer, it simply depends on your needs, most of the large applications or websites uses hybrid systems, which means that there are implentation of both SQL and NOSQL databases in different parts of their application, depending on the need.
so if you have an application with a lot of writing requests, and those requests gets updated so frequently, then NOSQL will not be a good choice for you. on the other side, if you have an application with so many read requests, then the best option will be the NOSQL, as scalling is much easier and handle a larg load of this type of requests.

## sequelize

it is a promise-based Node.JS ORM (object relational mapping) for multiple SQL databases such as, SQLite, postgressql, MYSQL and more.
ORM at a high level is a technique used in computer programming for converting between incompatible type systems using object-oriented programming language.
No we can go by the book and say that some of it's feature are: supporting solid data transaction, relations, eager & lazy loading, Or; we can say that is allows us to write less code and more cinsistent code, you can mostly avoid writing SQL queries.
one very big advantage that Sequelize provides, it allows you to switch to a different Database system without having to re-write your queries logic.
Sequelize is an open source ORM for node.JS that I'm really looking forward to understand and use it more.
