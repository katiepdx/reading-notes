## What Is Node and When Should I Use It? FROM https://www.sitepoint.com/an-introduction-to-node-js/
Node.js is built on Google's V8 JavaScript engine. V8 engine is open source. Runs in Google Chrome/chrome browsers. Node (created by Ryan Dahl) added to the V8 engine - file system API, HTTP library, and more. 

JavaScript Runtime - can execute JS on our computers. 

`node filename.js` displays message in terminal window if node is configured properly. 
`npm` is a node package manager. `npm install -g jshint` installs the jshint linting package globally.
node_modules : the folder where npm saves any libraries that a package (example here is lodash package) depends on. Add lodash as a require('lodash') in test.js. In package.json, lodash should be in the dependencies field. This way of specifying the project dependencies makes it possible for others to use npm to install the packages needed to run your project. 

Node.js lets us run JS on the server
Node.js is single-threaded and event-driven, meaning things happen in reaction to an event. When a request comes in, the server will begin to process it. 

Scaling up a node app - clone it. Cloned instances share the workload. 

**Applications and Node**
Node is great for building applications that require real-time interaction like chat sites or where you can watch something being built in real time like document edits. Also good for APIs with lots of requests that are I/O driven - data streaming. 

**Advantages of Node.js** 
- Speed and scalability. 
- Also, using JS on a web server. 
- Easily share code between server and the client. 
- JSON

