# Reading: API Integration

## Dynamic API Server

An Express/Node.js based server designed to be a “model agnostic” REST API server, which can perform CRUD operations on any data model

Business Requirements
We’re opening a online store! In order to support our web application, we need to create an API that will serve specific data (namely, categories and products) to our application. We will write an API to interface with our databases to provide category and product information to our front end app.

As it is highly likely that we will need more data types and sources in the future, it’s imperative that we build this API as a standardized means of working with any data model, using any persistence system, though a common interface. The API Server must operate as follows:

Support all REST/HTTP methods:

- GET: Retrieve record(s) from a data source
  - All
  - One (by id)
  - Some (by filtering)
- POST: Create a new record in a data source
- PUT: Update a single full record in a data source
- PATCH: Update part of a single record in a data source
- DELETE: Delete a record in a data source

## Technical Requirements

The application will be created with the following overall architecture and methodologies

1. Node.js
2. ES6 Classes and best practices
3. ExpressJS Web Server, built modularly
   - Middleware for handling 404 and 500 conditions
   - Middleware for handling the dynamic loading of the correct data model as specified in the route
   - Inspect the route, looking for the model name
   - require() the correct module model (i.e. if the model is categories, require('src/models/categories/categories-model.js'))
   - Use a single router (v1.js) to handle the ReST methods for CRUD for any model
     express.params middleware
4. Persistence using a Mongo Database (NoSQL)
5. Mongoose Schemas (data models) to define and model data
6. Mongoose Model “wrapper” class to serve as the API between the express server and the data models themselves
7. Test Driven Development, using Jest
   - Tests will be runnable locally
   - Tests will auto-execute (CI) in your repo using GitHub actions
   - Tests will use a 3rd party library called supergoose to:
     - “mock” the mongo running database
     - “mock” the running Express server
8. Deployment to Heroku

## Data Models

As we will be operating a virtual storefront, this application requires 2 data models to be fully functional

The following fields/data types must be supported by your data model

Categories

- name: Type: String, Required
- description: Type: String, Required

Products

- name: Type: String, Required
- category: Type: String, Required
- description: Type: String, Required
- price: Type: Number, Required
- inStock: Type: Number, Required

## Authentication Server / Module

An Express/Node.js based server using a custom “authentication” module that is designed to handle user registration and sign in using Basic, Bearer, or OAuth along with a custom “authorization” module that will grant/deny users access to the server based on their role or permissions level.

### Business Requirements

Our business is expanding! We have a real need to manage a list of users of many types, and control their access to our data accordingly. The system to be built will have the following core features:

1. Users can create an account, associated with a “role”
2. User Roles will be pre-defined and will each have a list of allowed capabilities

   - admin can read, create, update, delete
   - editor can read, create, update
   - writer can read, create
   - user can read

3. Users can then login with a valid username and password
4. Alternatively, users can login using an OAuth provider such as Google or GitHub
   - In this case, users should be automatically assigned the role of user
5. Once logged in, Users can then access any route on the server, so long as they are permitted by the capabilities that match their role.
   - For example, a route that deletes records should only work if your user role is “admin”

## Technical Requirements

The application will be created with the following overall architecture and methodologies

1. Node.js
2. ES6 Classes and best practices
3. ExpressJS Web Server, built modularly

   - “Auth” routes for handling the login and authentication system
     - POST /signup to create an account
     - POST /signin to login with Basic Auth
     - GET /oauth
   - Middleware for handling 404 and 500 conditions
   - Middleware for handling each type of authentication
     - Basic (username + password) to be used on the /signin route only
       - i.e. app.post('/signin', basicAuthentication, (req, res) => { ... })
   - OAuth (3rd Party) to be used on the /oauth route only

     - i.e. app.get('/oauth', OAuth, (req, res) => { ... })
     - Handles the handshake process from a 3rd party OAuth system

   - Bearer (token) to be used on any other route in the server that requires a logged in user
     - i.e. app.get('/secretstuff', tokenAuthentication, (req, res) => { ... })
   - Middleware for handling authorization
     - To be run after Bearer Middleware on routes to be protected
     - Accepts a “capability” as a parameter
     - i.e. app.delete('/secretstuff', tokenAuthRequired, capability('delete'), (req, res) => { ... })

4. User Persistence using a Mongo Database (NoSQL)
   - Mongoose Schemas (data models) to define and model data
5. Test Driven Development, using Jest
   - Tests will be runnable locally
   - Tests will auto-execute (CI) in your repo using GitHub actions
   - Tests will use a 3rd party library called supergoose to:
     - “mock” the mongo running database
     - “mock” the running Express server
6. Deployment to Heroku
