## URLSearchParams FROM (https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams)
URLSearchParams can be used in a `for...of` structure. `for (const [key, value] of mySearchParams) {}`.

The constructor `URLSearchParams()` returns an object instance. There are methods such as `URLSearchParams.append()`, `URLSearchParams.get()`, etc.

URLSearchParams does not parse full URLs. Removes the first `?` from the string if it exists. 

Widely supported except for IE.

## URLSearchParams.toString() FROM (https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/toString)
URLSearchParams.toString() returns a query string used in URLs. Returns an empty string if there are no search params.

Example from site of URLSearchParams.toString()

```js
let url = new URL('https://example.com?foo=1&bar=2');
let params = new URLSearchParams(url.search.slice(1));

//Add a second foo parameter.
params.append('foo', 4);
console.log(params.toString());
//Prints 'foo=1&bar=2&foo=4'

// note: params can also be directly created
let url = new URL('https://example.com?foo=1&bar=2');
let params = url.searchParams;

// or even simpler
let params = new URLSearchParams('foo=1&bar=2');
```


## Location FROM (https://developer.mozilla.org/en-US/docs/Web/API/Location)
Location representations the URL/location of the object its linked to. 

**Properties**
- Location.ancestorOrigins
- Location.href
- Location.protocol
- Location.host
- Location.search
- Etc.

**Methods**
- Location.assign()
- Location.reload() - reload current URL like a refresh.
- Location.replace()
- Location.toString() - returns USVString with the whole URL. 

```js
//EXAMPLE FROM SITE
var url = document.createElement('a');
url.href = 'https://developer.mozilla.org:8080/en-US/search?q=URL#search-results-close-container';
console.log(url.href);      // https://developer.mozilla.org:8080/en-US/search?q=URL#search-results-close-container
console.log(url.protocol);  // https:
console.log(url.host);      // developer.mozilla.org:8080
console.log(url.hostname);  // developer.mozilla.org
console.log(url.port);      // 8080
console.log(url.pathname);  // /en-US/search
console.log(url.search);    // ?q=URL
console.log(url.hash);      // #search-results-close-container
console.log(url.origin);    // https://developer.mozilla.org:8080

```

Widely supported across browsers. No password or username browser capabilities. 

## Window: hashchange event FROM (https://developer.mozilla.org/en-US/docs/Web/API/Window/hashchange_event)

An event fired when the part of the URL starting and following the hashtag % changes. Can be used in an addEventListener.

```js
//EXAMPLE FROM SITE
function locationHashChanged() { 
  if (location.hash === '#cool-feature') { 
    console.log("You're visiting a cool feature!"); 
  } 
} 

window.onhashchange = locationHashChanged;
```