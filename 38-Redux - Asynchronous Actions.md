# Redux - Asynchronous Actions

Earlier, we said that Redux reducers must never contain "side effects". A "side effect" is any change to state or behavior that can be seen outside of returning a value from a function. Some common kinds of side effects are things like:

- Logging a value to the console
- Saving a file
- Setting an async timer
- Making an AJAX HTTP request
- Modifying some state that exists outside of a function, or mutating arguments to a function
- Generating random numbers or unique random IDs (such as Math.random() or Date.now())

However, any real app will need to do these kinds of things somewhere. So, if we can't put side effects in reducers, where can we put them?

#### Redux middleware were designed to enable writing logic that has side effects.

As we said in Part 4, a Redux middleware can do anything when it sees a dispatched action: log something, modify the action, delay the action, make an async call, and more. Also, since middleware form a pipeline around the real store.dispatch function, this also means that we could actually pass something that isn't a plain action object to dispatch, as long as a middleware intercepts that value and doesn't let it reach the reducers.

Middleware also have access to dispatch and getState. That means you could write some async logic in a middleware, and still have the ability to interact with the Redux store by dispatching actions.

## Writing an Async Function Middleware

Both of the middleware in that last section were very specific and only do one thing. It would be nice if we had a way to write any async logic ahead of time, separate from the middleware itself, and still have access to dispatch and getState so that we can interact with the store.

What if we wrote a middleware that let us pass a function to dispatch, instead of an action object? We could have our middleware check to see if the "action" is actually a function instead, and if it's a function, call the function right away. That would let us write async logic in separate functions, outside of the middleware definition.

Again, notice that this "async function middleware" let us pass a function to dispatch! Inside that function, we were able to write some async logic (an HTTP request), then dispatch a normal action object when the request completed.

## Redux Thunk

Thunk middleware for Redux. It allows writing functions with logic inside that can interact with a Redux store's dispatch and getState methods.

Why Do I Need This?
With a plain basic Redux store, you can only do simple synchronous updates by dispatching an action. Middleware extends the store's abilities, and lets you write async logic that interacts with the store.

Thunks are the recommended middleware for basic Redux side effects logic, including complex synchronous logic that needs access to the store, and simple async logic like AJAX requests.

One of the main use cases for this middleware is for handling actions that might not be synchronous, for example, using axios to send a GET request. Redux Thunk allows us to dispatch those actions asynchronously and resolve each promise that gets returned.

### Installation and Setup

Redux Thunk can be installed by running npm install redux-thunk --save or yarn add redux-thunk in the command line.

Because it is a Redux tool, you will also need to have Redux set up.

### How to Use Redux Thunk

Once Redux Thunk has been installed and included in your project with applyMiddleware(thunk), you can start dispatching actions asynchronously.
