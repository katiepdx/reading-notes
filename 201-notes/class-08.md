# The Past, Present, and Future of Local Storage for Web Applications https://diveinto.html5doctor.com/storage.html

Native client application (appstore) vs web applications (apps accessible through browser)
Persistent local storage gives native client apps an edge over web apps. If the app needs more than key/value pairs, you can create your own database, file formats, etc. 

**Cookies**: used to store small amounts of data in persistent local storage. 
Cookie downsides: 
- Included with every HTTP request and transmitting the same data again and again, thus making the web app slower. 
- Sends encrypted data when HTTP request (unless app is served over SSL)
- Cookie data is limited to approximately to 4kb. 

**Ideal situation**
- Lots of storage space
- on the client
- data stays even with page refresh
- data is not transmitted to the server

### Brief History of Local Storage Hacks Before HTML5
- IE, Microsoft DHTML Behaviors - userData. UserData web pages store up to 64kb of data per domain. IE does not let you increase the amount of storage available. 
- 2002 Adobe - Flash 6 (Local Shared Objects aka flash cookies). Stores up to 100kb of data per domain. 
- 2006 Google Gears - open sourced browser plugin - after user permission, Gears can stored unlimited amounts of data per domain in SQL database tables. 
- Others as well
- **HTML5 strives to provide a standardized API that natively and consistently works across multiple browsers without 3rd party plugins**. 

### HTML5 Storage (web storage) - Local Storage/DOM Storage
- locally stored key/value pairs within clients web browser
- stored as a string!
- stays even with page refresh 
- The data is NOT transferred to server
- native and not dependent upon 3rd party plugins. 

HTML5 uses localStorage - need to check for HTML storage first. Can use Modernizr.localstorage in an if else. If using something other than strings, you need to use parse to retrieve data. `setItem()` with a key that exists overwrites previous value. `getItem()` with a non-existent key will return null. Can use bracket syntax too. `.removeItem(in DOMStringkey)` to remove values. 

- in 2011, 5 megabytes of storage space across all browsers 

- HTML5 storage can be used to save games progress. 

- Web SQL Database lets you do things like with backend database programming but with JavaScript. There are many types of SQL (e.g., Oracle's SQL, Microsoft's SQL, MySQL, etc.). 
