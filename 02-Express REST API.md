# Readings: Express, REST API

1. ### Express JS:

   express.js is an open-source and free node.js framework, that is used for designing and web applications.

   you can create a single page, multi-page or hubrid web applications using express, it is also light weight and helps to better organize the code on the server side.

   In a MERN development stack (MongoDB, Express, React, Node), express handles the backend part, Managing routing, sessions, HTTP Requests, Error handling and more.

   ### Why you should use Express.js ?

   1. #### Easy to learn

      Express.js is written with javascript code, so if you already know javascript, you can easily create a web server with express.js.

   2. #### build different web apps in short time period

      Express.js provides a simple routing for requests made by the clients, it also provides a midddleware that is responsible for making desicions to give the correct response for the requests made by the client.

   ### Features of Express.js

   1. #### Faster server-side development
      Express has many built-in methods that saves time when writing server-sode code.
      ex" to create a server, simply install the Express library by running the following command (npm i express).
      after the download, simply import express to your server.js file by writing (
      - const express = require("express")
      - const app = express()
        )
        and that's it, now you can use many express.js methods such as: listen, get, post, and so much more.
   2. #### Middleware
      Middleware is a part of the program that has access to the database, client request and other middlewares.
      (more about this topic later in this article)
   3. #### Routing
      Express.js provides a highly advanced routing mechanism, which helps to preserve the state of a web page with the help of their URLs.
   4. #### Templating
      Express.js provides templating engines that allow the developers to build dynamic content on the web pages by building HTML templates on the server-side.
   5. #### Debugging
      debugging is crucial for the successfull development of web applications. express.js makes debugging easier by providing a debugging mechanism that has the ability to pinpoint the exact part of the web application which has bugs.

[Resource](https://www.besanttechnologies.com/what-is-expressjs)

2. ### REST API

   a REST API (or RESTful API), is an application programming interface (API) that conforms to the constraints of REST architechtural style and allows for interaction with RESTful web services.

   REST stands for Representaional State Transfer and was created by computer scientist Roy Fielding.

   in general, an API is a set of definitions and protocols for building and integrating application software.
   it is some times referred to as a contract between an information provider and an iformation user.

   REST is a set of architechtural constraints, not a protocol or a standard. API developers can implement REST in a variety of ways.
   When a client request is made via RESTful API, it transfers a representation of the state of the resource to the requester or endpoint.

   ![REST API Image](assets/what_is_rest_api.png)

[Resource](https://www.redhat.com/en/topics/api/what-is-a-rest-api)

---

## Review, Research, and Discussion

1. #### Name 3 real world use cases where you’d want to change the request with custom middleware

   a. adding time to the request object.
   b. reshaping the data before it reaches the server, ex: using a constructor to create a desired object from the request (Data Management).
   c. input validation.
   d. authentication

2. #### True or false: The route handler is middleware?
   False, a route handler is code that is looking for a request to a specific incoming URL such as /login and often a specific HTTP verb such as POST and has specific code for handling that precise URL and verb.
3. #### In what ways can a middleware function end the process and send data to the browser?

   in four ways :
   a. res.send()
   b. res.json()
   c. res.end()
   d. res.render()

4. #### At what point in the request lifecycle can you “inject” middleware?
   After receiving the request, before sending the response (in the middle hence the word middle in middleware)
5. #### What can cause express to error with “Request headers sent twice, cannot start a second response”
   if a response has been already sent from the server to a specific request, and now it is trying to send another response for the same request.

---

## Vocabulary & Terms

| Term                    | Defenition                                                                                                                                                                                                                                                                                                               |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Middleware              | Middlewares are functions that have access to the request object, the response object and the next function in the request-response cycle. they can excute any code, make changes to the req,res objects, end the request-response cycle and call the next middleware in the stack.                                      |
| Request Object          | The request object (req) represents the HTTP request and has properties for the request query string, parameters, body, HTTP headers and so on.                                                                                                                                                                          |
| Response Object         | The Response object (res) is the object that an express app sends after recieving a specific HTTP request.                                                                                                                                                                                                               |
| Application Middleware  | to bind a middleware to an instance of the express object (ex app.use)                                                                                                                                                                                                                                                   |
| Routing Middleware      | work just like application level middleware except they are bound to an instance of express.                                                                                                                                                                                                                             |
| Test Driven Development | is a software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases. This is as opposed to software being developed first and test cases created later. |
| Behavioral Testing      | Behavior-driven development specifies that tests of any unit of software should be specified in terms of the desired behavior of the unit.                                                                                                                                                                               |

---

## Preview

1. #### Which 3 things had you heard about previously and now have better clarity on?

   a. framework and library
   b. Express
   c. middleware

2. #### Which 3 things are you hoping to learn more about in the upcoming lecture/demo?

   a. Express Router
   b. building a custome middleware
   c. using the render() method.

3. #### What are you most excited about trying to implement or see how it works?
   How can I serve HTML templates to the client (using express templating feature).
