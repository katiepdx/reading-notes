# Duckett HTML book - Chapter 16: “Images” (pp.406-427)
- Controlling size of images in CSS
- Aligning images in CSS
- Adding background images

#### Image Size 
- heigh and width measured in pixels (px).
- can `float: left` or `float: right` to align them. Or `display: block` to center as block.

Note: To wrap a photo with text, use `float: left` on the photo. 

#### Images, images, images
- Can use CSS `background-image` to add a background image to a certain element.
- `background-repeat: no-repeat;` - repeating the image (`repeat`, `repeat-x`, `repeat-y`, `no-repeat`)
- `background-attachment: fixed;` - fixing the image to the same position on the page
- `background-position: top left/left center/left bottom/center top/center center/center bottom/right top/right center /right bottom`. - If only one value is specified, the other will default to center. 
- SHORTHAND `background: #ffffff url("img url goes here") no-repeat top right:`

#### Image Rollovers and Sprites
- Rollovers: When user hovers, the button or link changes, and then changes again when it is clicked. `element:hover` pseudo class can be used. 
- Sprites: When a single image is used for several different parts of an interface.

#### CSS3 Gradients 
- `background-image: webkit-gradient(linear, 0% 0%, 0% 100%, from(#66cccc), to(#336666))`

#### Contrast of Background Images
- high contrast (not ideal for background images)
- low contrast (low contrast background images makes text easier to read)
- screen (a screen added to a high contrast image makes the text easier to read)

# Duckett HTML book - Chapter 19: “Practical Information” (476-492)
- Search engine optimization (SEO): on page techniques and off-page techniques 
- Using analytics to understand visitors
- Putting your site on the web

#### On-page SEO
Every web page has several key places where keywords (the words a search engine might find on your site). These impact **findability**... in order.
- Page title
- URL/Web Address
- Headings
- Text
- Link Text
- Image Alt Text
- Page Descriptions

#### How to Identify Keywords and Phrases
- Brainstorm words someone might type into a search box. 
- Group the keywords into separate lists for the different sections or categories of the site. 
- Research keywords using sites like... adwords.google.co.uk/select/KeywordToolExternal (select "exact match" instead of "broad match" when using that tool.) www.wordtracker.com and www.keyworddiscovery.com.
- Compare how many other sites match the keywords. How much competition?
- Refine: Pick the words you want to focus on. They should be relevant to the site.
- Map: Now that there is a refined list, pick 3-5 keywords or phrases and map to each page of the site. Use the keywords. 

#### Analytics: Learn about your visitors
Use Google Analytics. With each page load, a tracking code sends data to the Google serves. Add the code just before the closing `</head>` tag. It doesn't alter site appearance. 

Research (**Google Analytics provides**):  visits, **unique visits**, page views, page views per visit, average time on site, date selection, visitor overview. Shows which are **landing pages** (the pages users arrive to your site on) and **exit pages** (which pages users leave the site on). **Bounce rate** (the number of people who left on the same page that they arrived on). High bounce rate isn't good. **Referrers** (other sites that link to your site. If you get a lot of traffic from them, message the referrer and get in contact.) **Search Terms** this shows what users type into the search box to get to your site. *Advanced features* include things like e-commerce shopping trackers which is good for those running an online shop. 

#### Hosting 
In order to put a site on the web, you need a domain name and web hosting. 
- **Domain Hosting** : Domain name is the web address (e.g., www.google.com). 
- **Web Hosting** : So others can see the site, it will need to be uploaded to a server. Most sites run on web servers run by web hosting companies. When choosing, consider the follow: disk space, bandwidth, backups, email accounts, server-side langues and databases. 
- **Hosted Services**:  Some services let you point your domain name (web address) to their servers (e.g., WordPress, Tumblr, Shopify, etc.). If using the aforementioned sites, you will not need a web hosting. 

**File Transfer Protocol (FTP)**: Transferring your code and images from your computer to your hosting company. Popular applications: FileZilla, FireFTP, CuteFTP, SmartFTP, Transmit.

# Additional Resources (Bookmark/Skim) - Chapter 9 (pages 201-206 only). Flash is no longer supported by many browsers but is an important part of history.
Flash is used for adding animations, video, and audio to websites. Flash files (.fla) file extension. Exported Flash moves are in SWF format. Flash creates code that you can use to embed the Flash movie in the page. Flash needs the Flash plug-in to view the material. Since 2005, less sites are written in Flash or use elements of Flash the pages. Apple IPhone (2007 and on) devices don't support Flash.  

# MDN article on audio and video elements (https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)

Video and Audio controls available

#### The HTMLMediaElement API
HTMLMediaElement.play(), HTMLMediaElement.pause()

HTML for Media + controls from MDN site. Can change the styling using CSS. Once CSS is complete, wire everything so it works using JavaScript. Start by getting the elements. Add event listeners to them (e.g., for start and stop, pause, etc.) Use functions for interval skipping, fast forward, etc. 

```html
<!-- FROM MDN SITE -->
<div class="player">
  <video controls>
    <source src="video/sintel-short.mp4" type="video/mp4">
    <source src="video/sintel-short.webm" type="video/webm">
    <!-- fallback content here -->
  </video>
  <div class="controls">
    <button class="play" data-icon="P" aria-label="play pause toggle"></button>
    <button class="stop" data-icon="S" aria-label="stop"></button>
    <div class="timer">
      <div></div>
      <span aria-label="timer">00:00</span>
    </div>
    <button class="rwd" data-icon="B" aria-label="rewind"></button>
    <button class="fwd" data-icon="F" aria-label="fast forward"></button>
  </div>
</div>
```