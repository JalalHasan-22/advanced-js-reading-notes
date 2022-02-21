# Reading notes

### The Event Loop

As we know, JavaScript is an asynchronous, single-threaded, non-blocking language.
but how can it to be able to perform asynchronous operations without blocking the code execution?
that's where the event loop come in handy.
So basically, Javascript puts the code in the Call stack (execution of the code), when it detects a code that is asynchronous (setTimeOut for example), it will be passed to the the event loop and continue with executing the code in the call stack line by line.
once the call stack is empty, javaScript will turn to the event loop to execute any code that was running in the background and now is finished and ready to be executed, and that function to the call stack.

### JavaScript Callback functions

Callback functions are simply functions passed to other functions as parameter.
this can be very usefull incase we want to run pices of code sequentially, like some code needs to run after another pice of code has been executed.
callback functions can be either a pre defined function where we refer to it by writing it's name, or it can be an anonymous function defined with no name to do a simple one-time job.

### Javascript Promises

JavaScript promises are used to handle Asynchronous operations in javaScript.
a promise in javaScript has 4 main states

- pending: can sometimes be called "not fulfilled"
- fulfilled: promise finished successfully.
- rejected: promise finished with failure.
- settled: promise has either been fulfilled or rejected.

when we are dealing with promises, we say that we are consuming a promise which takes us to the next topic

###### promise consumers

1- .then method
defines actions that will be done once the promise has been fulfilled.

the .then() method takes two functions as parameters.
1- function is executed if promise is resolved and a result is received.
2- function is executed if promise is rejected and an error is received. (It is optional and there is a better way to handle error using .catch() method

##### Applications

Promises are used for asynchronous handling of events.
Promises are used to handle asynchronous http requests.

### Async/Await Function in JavaScript

JavaScript uses this abroach to define pieces of code as Asynchronous code, when defining a new function, by simply writing "async" before the function keyword declaration, this makes javascript understand that this function is async function and shall not block the execution stack (Don't wait for this function to be done).

the "await" keyword returns a new promise that we then needs to consume, it can not be used outside of an async function (top level await are expected to be implemented in the next ES6 update).

### TDD (Test Driven Development)

it is the process of the code being guided by the tests, which means that the tests comes before the code.

there are many tools and libraries used for testing nodeJS applications, one of them is called Jest.js.

this library has a lot of built-in methods that can be used to test units of our code (unit testing).

tests are expected to be found in a directory called "**tests**" and it is advised to have a test file for every single file we want to test having the same name as the to be tested file "server.js / server.test.js"
Jest library shoud be installed as a development dependency, as it will not be used in production so it should not be deployed.
