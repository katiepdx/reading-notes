## Learn to Use the New Router in ExpressJS 4.0 FROM https://scotch.io/tutorials/learn-to-use-the-new-router-in-expressjs-4
- MEAN Stack - (FROM https://www.freecodecamp.org/news/cjn-understanding-mean-stack-through-diagrams/)
  - MongoDB (database)
  - Express (back-end framework)
  - Angular (front-end framework) 
  - Node.js (back-end run-time environment)

- New `Router` comes with a "mini express app" that allows us to use `.use`, `.get`, `.param`, and `route`. 
  - Flexibility with defining routes

**Create Simple Page**
- Need package.json for dependencies (install express)
- Create a mock get route to test server works when testing our server set up
- Create a server in server.js using express. 
  - Start server by using `app.listen(port)`. Note: remember to put port in process.env file. 
- Create basic Routes with `express.Router()` in server.js
  - Bring in Router in server.js page `const router = express.Router()`
  - Add the pages you want (home page is '/' and about page can be on something like 'localhost:1234/about')
    - Apply the routes by adding `app.use('/, router)` at the bottom of the page. Note: if you can change where the routes are located (example: localhost:1234/app) by adding something after the forward slash `app.use('/app, router)`. 
      - Can create multiple routes - basic ones, auth routes, and API routes. 
  - Route middleware with `router.use()` in server.js
    - This is used to check something before a request is processed, such as if a user has been authenticated already.
    
    ```js
    // used on every request 
    router.use((req, res, next) => {
      //do something here
      next(); //go on to next thing      
    });
    ```

    - Order matters for middleware and routes
  - Routes with parameters like `/hello/:name` done in server.js
    
    ```js
    // EXAMPLE FROM SITE
    // Param middleware goes BEFORE the route, and it validates the name in this case. 
    router.param('name', (req, res, next) => {
      // validate name 
      // validation...
      // log/notify that validation station (ex. working on name)
      // save validated name to name 
      req.name = name;
      // go on
      next();
    })


    // route with parameters (http://localhost:8080/hello/:name)
    router.get('/hello/:name', function(req, res) {
      res.send('hello ' + req.params.name + '!');
    });

    // If you went to http://localhost:8080/hello/John, the browser would display "hello John". (Note: Do not add the : when typing the actual name)
    ```

  - Login routes with `app.route` which is our "shortcut" to Express Router" (Note: using `app.route` instead of using `express.Router()`).
    - Can use multiple actions, GET and POST route, on one login route.

    ```js
    app.route('/login') // http://localhost:8080/login
      .get(...) // GET function for GET http://localhost:8080/login
      .post(...) // POST function for POST http://localhost:8080/login


## HTTP: The Protocol Every Web Developer Must Know - Part 1 FROM https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177
- HTTP - HyperText Transfer Protocol 
- HTTP protocol is stateless. Communication between hosts and clients is via TCP/IP usually both other transports can be used. Default TCP/IP is 80, but other ports are also an option. 
  - Persistent connections, chunked transfer0coding, and fine-grained caching headers
  - Requests sent using URLs (Uniform Resource Locations).
  - Example URL: http://www.domain.com:1234/path/goes/here?query=1234&here=1234
    - http (protocol)
    - www.domain.com (host)
    - :1234 (port)
    - /path/goes/here (resource path)
    - ?query=1234&here=1234
  - debugging proxies (Fiddler (Windows) and Charles Proxy (OSX))
  - HTTP verbs - GET, GET (by id), POST, PUT, DELETE (most popular) -- Less common verbs are HEAD, TRACE, OPTIONS
  - Status codes 100s to 500s
  - Req/Res formats
    - Request (client to server is URL and VERB) GET from a site.com or POST to site.com
    - Response (from server back to client has a status code and message body) - MUST have a new line between message headers and body. 
  - Headers
    - General Headers are shared by request and response messages. 
      - Connection, Date (timestamp of req/res), Pragma, Trailer, Transfer-Encoding, Upgrade, Via, Warning 
    - Entity Headers (req/res can include them) - provides meta-info about the content (the Message body or Entity)
      - Allow, Content-Encoding, Content-Language, Content-Length, Content-Location, Content-MDS, Content-Range, Content-Type, Expires, Last-Modified
    - Request headers
      - Accept, Accept-Charset, Accept-Encoding, Accept-Language, Authorization, Expect, From, Host, If-Match, If-Modified_since, If-None-Match, If-Range, If-Unmodified-Since, Max-Forwards, Proxy-Authorization, Range, Referer, TE, User-Agent
- View HTTP Traffic 
  - Chrome -- Inspect Tool -- Network Tab -- Headers
  - Debugging Proxies: Fiddler for Windows and Charles Proxy for OSX
  - Command Line Tools: curl, tcpdump, tshark 
- Web Framework and Libraries AND HTTP
  - ExpressJS -- 
    - REQ: has req.body for the request body...and more like req.query, etc. 
    - RES: has res.send for HTML/JSON/Octet-stream as well as others like res.status, etc. 
  - ActionControllers, ActionDispatch, 

## How DNS Works FROM https://howdns.works/episodes/
- The website is unknown
  - computers and devices use IP addresses to communicate (IP 10.0.0.1) but we use words instead of IPs like (www.google.com). DNS lets people use words (www.google.com) instead of the IP addresses (IP 216.58.210.142). 
  - The browser and OS both search the cache to to see which can find the IP for the www.examplesite.com first. 
- The Road Trip 
  - Resolver server (usually the ISP (internet service provider)- resolver will look for root server because root server knows where .com TLD server is. TLD is Top-Level Domain. Once at root, resolver asks root to lcoate the examplesite.com.
- Top of the hierarchy
  - Root can't find examplesite.com but can find .com TLD server. 
  - resolver stores .com TLD address 
  - there are 13 root servers domains (.com, .org, .net) all over the world.
    - naming: letter.rooot-servers.net -- letters range A to M (example a.root-servers.net)
    - severs have many physical servers distributed all over the world 
- .HOT .PIZZA .COM
   - .COM TLD (created in 1985) was one of the first and is now the largest TLD
   - TLDs can be a country's 2 letter ISO code like .jp for Japan or .fr for France. The TLDs can also be written in another language like .中国
   - TLDs are usually 3+ letters like EDU, ORG, etc. 
   - Can do reverse DNS lookups with ARPA (IP to domain). Normal lookup (known domain to unknown IP).
   - Many other TLDs like .PIZZA, .APP, .HEALTH, etc. 
   - resolver still knows examplesite is a .COM server but doesn't know IP address.
    - Authoritative name servers 
- Respect my authority!
  - Domain registrar - all purchased domains are stored in domain registrar
  - Can run a WHOIS query - now have IP 
  - Resolver saves the IP that was given by the Authoritative Name Server
- It's getting late
  - Root told resolver where to find the .com server
  - TLD server gave authoritative name server addresses (.com)
  - ns1.examplesite.com gave the IP for examplesite.com
  - resolver tells OS -- examplesite.com's IP address is 12.34.567.890
- Bonus: Glue records
  - ns1.examplesite.com is a sub-domain of examplesite.com 
  - Glue records: extra info attached to the the response when the resolver asked the .com TLD about the domain examplesite.com
    - resolver received authoritative server name and IP address, thus breaking the loop dependency

## What Is A RESTful API? Explanation of REST & HTTP FROM https://www.youtube.com/watch?v=Q-BpqyOT3a8
- API Application Program Interface 
- A contract between softwares, a structured request and response. 
  - Like ordering at a restaurant. You (the client) place an order with the server (the API) and the server goes to the backend (the kitchen) to tell the cook and sends a response (the cooked meal) back to the diner. Sometimes requests need to be sent in the correct "shape". 

**REST APIs (sometimes called RESTful)**
- REpresentational State Transfer
- REST API is an architecture style for designing networked applications
- Stateless client-server protocol (usually HTTP), like http requests. 
- Server objects are resources that be created or destroyed 
  - Server side object example: post or blog in a database 
- Most programming languages can use REST APIs because many languages can make HTTP requests

- HTTP requests from the client are sent to a URI/URL endpoint using GET, GET (by id), POST, PUT, DELETE.
- AUTHENTICATION: Protecting the endpoints (like OAuth). Github has its own API. Some of the Auth services are free and some are paid. 
  - curl with OAUTH-TOKEN
  - can send token as a parameter in uri
  - can send a generated client id and secret instead of token as a parameter in the uri. 


**GitHub API (developer GitHub)**
- Checkout documentation --> users --> get a single user using URI with parameter `...user/:id`. 
- GET response returns  JSON. 
- Use Postman to make request 
  - Authorization goes in headers sometimes 
  - Can send data using many formats 
  - Can get data 
  - GET to https://api.github.com/users/(username_goes_here)
  - Register for a new OAuth Application at https://github.com/settings/applications/new 
    - Fill out application name, homepage URL, application description, authorization callback URL --> Register application
    - Use client id and client secret from here and pass them as the parameter in URI.  
      - https://api.github.com/users/(username)?client_id=###########&client_secret=###########




## The HTTP Reference FROM https://code-maze.com/the-http-reference/
- Request Methods
  - CONNECT
  - DELETE
  - GET
  - HEAD
  - OPTIONS
  - POST (has a body)
  - PUT (has a body)
  - TRACE

- Status Codes 
  -  100s informational
  - 200s successful 
  - 300s redirection
  - 400s client error
  - 500s server error

- Headers
  - http requests
  - http reponses

- MIME Types
  - Application MIME Types
  - Multipart MIME Types
  - Text MIME Types

## Using HTTP Methods for RESTful Services FROM https://www.restapitutorial.com/lessons/httpmethods.html
- HTTP Verbs
  - POST - create
  - GET - read
  - PUT - update/replace
  - PATCH - update/modify 
  - DELETE - delete 
    - Double calling a delete usually returns a 404