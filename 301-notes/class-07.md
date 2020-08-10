## What Google Learned From Its Quest to Build the Perfect Team FROM https://www.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.html
- Team members feel like there is no judgement when bringing up ideas.
- Encouraged to work together - innovate faster, find mistakes quicker, find better solutions to problems.
- Team and socializing outside of work. 

## A Conversation about REST with my brother FROM https://gist.github.com/brookr/5977550
Roy Fielding - helped write the first web servers (sending docs and pages from servers to browsers). HTTP - foundation of the web...like GPS coordinates for information.

WWW world wide web is built on REST. 

URLs tell a browser there are concepts somewhere. A browser asks for the web page representation of that concept. 

Representations: 
- Web services 
- APIs

Machines Talking - "redirects" Machines tell each other where things are.

URL - different programming languages can talk about nouns 

Verbs (GET, SET, DELETE) and nouns like mp3, video, slideshow, etc. 

HTTP GET / HTTP POST / HTTP PUT / HTTP PATCH

## SuperAgent FROM https://visionmedia.github.io/superagent/
Lightweight. Works with Node.js

SuperAgent formats - default is "json" and "form". Automatically serializes JSON and forms. Can set up auto serialization for other types too. 

SuperAgent - two implementations: Web browser (XHR) and Node.js (core http module). Browserify and WebPack pick the browser version by default. 