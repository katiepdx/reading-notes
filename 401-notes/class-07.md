## Note: Repeat reading
## Web Scraping with Javascript and NodeJS FROM https://www.scrapingbee.com/blog/web-scraping-javascript/
- NodeJS and web scaping - lots of libraries!
- JS interacts runs in the browser and the browser with runtime environment. Can't interact with computer directly. 
- NodeJS lets JS run on client-side and server-side. 
- Ryan Dahl - Node. 
  - Single threaded -> Non-blocking with event loop. 
  - install node. Open file and type "node file-name.js" to run it. Go to localhost:3000.
- HTTP clients: can send and receive to a server (req and res).
  - Request Library (deprecated but still usable!) 
    - request is common HTTP client in JS. 
    - Need to `npm install request`.
    - `const request = require('request')`
  - **Axios** - HTTP client that uses promises
    - run in browser and NodeJS
    - `const axios = require('axios')` and use `.get`, `.then`, and `.catch`.
    - Need to `npm install axios`
    - can use async/await
  - **Superagent** - HTTP client that uses promises, async/awaits, callbacks
    - more dependencies so less popular
    - `const superagent = require("superagent")`
    - Need to `npm install superagent`
  - **RegEx**
    - simple way to scape with out dependencies, but less flexible and can be tricky
    - `.match()`
  - **Cheerio** (lightweight)
    - Similar to how JQuery is used - server-side
    - Not great for JS heavy sites
  - **JSDOM** used for pages with js
    - creates a DOM that you can interact with 
    - When unsure about runScript credibility, set runScript to "outside-only" instead of "dangerously". 
  - **Puppeteer** (headless browser)
    - used to navigate the web like a real person using the sites
    - Can take screenshots, create pages, automate user interactions (like form inputs), etc. 
    - Chromium 
  - **Nightmare** (high-level browser automation library) 
    - similar to Puppeteer 
    - Electron 

## Document.querySelector() FROM https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector
- Returns first match or null if no matches are found. 
- `element = document.querySelector(CSS-Selector-String` would be `var el = document.querySelector(".myClass")`  (EXAMPLES FROM SITE)
- Note: If a selector matches an ID used multiple times, the first instance is returned. 
- Escape characters for spaces or special characters - JS uses one "\". Literal strings use two "\\"...meaning if you want `test\\ing` you will need to add another two slashes like so `test\\\\ing`.
- Selecting a nested div inside an input with a specific class (EXAMPLE FROM SITE) `var el = document.querySelector("div.user-panel.main input[name='login']")`. 
- Can use the word "not" to exclude parts of the query.  

## Document.querySelectorAll() FROM https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll
- Returns static node list of all elements matching the selector and an empty nodeList if no matches are found. 
- `elementList = parentNode.querySelectorAll(selectors);` (EXAMPLE FROM SITE)
  - `var inner = select.querySelectorAll('.outer .inner')` (EXAMPLE FROM SITE) - selects anything with the class of .inner or .outer that are nested inside the div with the .select selector. 
- SyntaxError if selectors is not correct
- can be used with `:scope`. 
