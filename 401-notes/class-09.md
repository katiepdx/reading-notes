## Routing FROM https://expressjs.com/en/guide/routing.html
- Routing is the applications endpoints (the URIs) and these response to the client's request. 
- Routing: `app.METHOD(PATH, HANDLER)` 
  - `app` is the express instance 
  - METHOD is the HTTP request method (GET, POST, PUT, etc.)
  - PATH - path on server 
  - HANDLER - executed function (after match)
  
  ```js
  // Example from site 
  app.get('/', function(req, res) {
    res.send('This is a GET req to the homepage');
  });

  // can also make requests using POST, PUT, and other METHODS. 
  ```

  - `app.all(...)` - used to load middleware for ALL HTTP request methods. 

    ```js
    app.all('/', function(req, res) {
      console.log('This would print to the console for all METHODS (GET, POST, etc.')
    });

    // can also make requests using POST, PUT, and other METHODS. 
    ```

- Route paths can include strings, string patterns, and regular expressions (REGEX).

  ```js
  // Regex example from site - with match a route with any word ending in fly. For example, can make a GET request to /butterfly, /dragonfly, /firefly, etc.
  app.get(/.*fly$/, function (req, res) {
    res.send('/.*fly$/')
  });
  ```

- Route parameters - can be used to get a specific id (ex. :bookId)
  - can have multiple parameters in a route (ex. :userId, :bookId)
    - Route path: /flights/:from-:to
    - Request URL: http://localhost:3000/flights/LAX-SFO
    - req.params: { "from": "LAX", "to": "SFO" }
- Route handlers 
  - Can set callbacks to a constant and call them in an array
    - `app.get('/lots/of/functions', [function1, function2, function3])`
- Response methods 
  - res.download() - for downloads
  - res.end() - end response process
  - res.json() - for JSON response 
  - res.jsonp() - ...with JSONP support
  - res.redirect() - redirect request
  - res.render() - render a view template
  - res.send() - send a response back 
  - res.sendFile() - send a file (octet stream)
  - res.sendStatus() - send response status code as a string in the response body
- app.route() - can chain the different methods if they are going to the same endpoint

  ```js
  // can chain the different methods that are going to the /coffee endpoint
  app.route('/coffee')
    .get(...)
    .post(...)
    .put(...)
  ```

- express.Router - the "mini-app" - routes can be defined and mounted in the main app. 
  - in a routes file called coffee.js, import express (`const express = require('express')`) and import express.Router (`const router = express.Router()`)
  - router.use(...) - with timeLog -- Date.now()
  - router.get(...) - for the homepage
  - router.get(...) - for another page (set path to /about)
  - module.exports = router -- export the routers 
  - NOW, in the main app, bring in the routes file at the top `const coffeeRoutes = require('./coffee.js')`
    - at the bottom of this file, add `app.use('/coffee', coffeeRoutes)` to use the coffee routes.


## Supertest Docs FROM https://github.com/visionmedia/supertest
- Used for testing HTTP
- To use, install supertest - `npm install supertest --save-dev` and require it at the top of the file `const supertest = require('supertest')`
- uses describe...it...
- expectations run in the order they are defined
- supertest can do it if superagent can

## Using Middleware FROM https://expressjs.com/en/guide/using-middleware.html
- Middleware - executes code, change the request and response objects, end the req-res cycle, next
  - Application-level middleware (app)
  - Router-level middleware (router) - express.Router()
  - error-handling middleware takes 4 arguments (err, req, res, next)
  - Built-in middleware
  - To use the middleware, need to install. For example, to use the cookie-paraser middleware, need to `npm install cookie-parser`.
    - load the middleware using `app.use(cookieParser()`)

## ExpressJS - Middleware FROM https://www.tutorialspoint.com/expressjs/expressjs_middleware.htm
- Middleware functions can access the req and res.
- Executes in order defined 

## Express middleware FROM https://expressjs.com/en/resources/middleware.html
- List of Express middleware modules 

## HTTP Status Code FROM https://www.restapitutorial.com/httpstatuscodes.html
- List of HTTP Status Codes 
  - 100s - informational 
  - 200s - success
  - 300s - redirection 
  - 400s - client error
  - 500s - server error
