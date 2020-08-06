## Getting Started on Heroku with Node.js FROM https://devcenter.heroku.com/articles/getting-started-with-nodejs?singlepage=true
- Deploys a node.js app to Heroku 
- Need a Heroku account and Node.js and npm installed locally
- Download. In terminal `heroku login`. Check versions of node, npm, and git. 
- Clone it locally using `git clone "github heroku app url.git"`. 
- `heroku create` - a random name like sharp rain or something is generated 
- `git push heroku master` to deploy code 
- `heroku ps:scale web=1` to double check app is running 
- `heroku open` to open site 
- `heroku logs --tail` - check events. A single channel is provided for all events. NOTE: control + c to exit streaming of logs. 

- Procfile: `web: node index.js` - important to have web in Procfile. 
- `heroku ps`, `heroku ps:scale web=0`, scale again `heroku ps:scale web=1` - free dynos sleep after half an hour of no traffic on free version. Upgradable. 

- `heroku local web` run app locally 
- Add ons ex. more more than 1500 lines of logs --> use papertrail `heroku addons:create papertrail` 
    - `heroku addons`
    - `heroku addons:open papertrail` 

- run bash from heroku NOTE: exit when finished to end dyno bash. `heroku run bash`

- Add to Database like MongoDB, Postgres, MySQL, etc. `heroku addons:create heroku-postgresql:hobby-dev`. creates a URL but you can check by typing `heroku config`.
    - `npm install pg` - install node postgres to dependencies 

## Node.js For Beginners. Deploy Your Blog to Heroku FROM https://howtonode.org/deploy-blog-to-heroku
Node.js - open source, cross-platform runtime environment. Allows you to build server side and networking applications. Written in JS. 

- check web server is working by typing `node server.js` into terminal. 
- Make it a world wide server by using heroku. start by `heroku login`.
- create a project directory with a **server.js** file. 
    - inside file set these variables.

    ```js
    //from site
    var http = require("http");
    var fs = require("fs");
    var path = require("path");
    var mime = require("mime");
    ```
- create a project package.json file. 
    - inside file add this.

    ```js
    //from site
    {
        "name" : "site name",
        "version" : "0.0.1",
        "description" : "description of site here",
        "dependencies" : {
            "mime" : "~1.2.7"
        }
    }
    ```

- create a project node_modules folder. 
    ```js
    //from site
    //404 error that appears when req file doesn't exist
    function send404(response) {
    response.writeHead(404, {"Content-type" : "text/plain"});
    response.write("Error 404: resource not found/Error msg goes here");
    response.end();
    }

    //sendPage()
    function sendPage(response, filePath, fileContents) {
    response.writeHead(200, {"Content-type" : mime.lookup(path.basename(filePath))});
    response.end(fileContents);
    }

   ```

- `now write the `function serviceWorking(response, absPath) `
    - This is how the server handles responses - returns file or 404.
- create HTTP server

- ONCE SITE HAS BEEN CREATED, DEPLOY USING HEROKU 
- `heroku create`
- `git push heroku master`
- `heroku ps:scale web=1` check one instance is running 
- `heroku apps:rename nameofyourchoicegoeshere`
- `heroku open` -> https://nameofyourchoicegoeshere.herokuapp.com/