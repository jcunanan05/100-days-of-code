# Front-end Dev Study Notes

Hi, This is my notes compilation when exploring front-end concepts. This notes contains what I understood while reading it, feel free to make PRs or issues when you find a note that is wrong. **Happy Coding!**

## Learning HTTP

### What happens when you visit a site on web
res: [https://www.helloitsliam.com/2014/12/20/how-the-internet-works-infographic/]()

1. An http request is made when you type http://www.google.com, where:
  * **http** is the protocol, a protocol for internet communication
  * **www** is the host name
  * **google.com** is the domain name
2. The request will go through the firewall (like a guard) and to your router/modem
3. router/Modem will pass the request to your ISPs like _(Rogers, Bell, PLDT, GoogleFiber)_. ISPs have servers and a DNS will process the url and figure out its IP address.
4. Browser will establish a connection and the IP that you're trying to reach will release a response
5. The response will be jump on to multiple servers in order for the response to get back to you.
6. Broswer will receive the http response and interpret the data, and display the website with all the design and such. :)

### How the internet works in 5 min
res: [https://www.youtube.com/watch?v=7_LPdttKXPc]()
* IPs are like map coordinates
* domain name is for us, so IPs are easier to read, and are processed by DNSs 
* Our requests in the internet are processed by the ISPs and ISPs sends it to its designation

### How does the internet work
res: [https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work]()
* It's like HTTP explanation but with more details. =))
* **Internet** is an infrastructure, where as the **web** (www) is a service built on top of it.

## Web Browsers

### Web browsers wiki
res: [https://en.wikipedia.org/wiki/Web_browser]()
* Software application, retrieves and presents data on the web (www)
* Resources can be obtained via URI/URL

### Common Browsers and their javascript engines
1. Chrome
  * Uses Blink - is a fork of a component (Webcore) of Webkit 
  * Uses V8 - Open sourced javascript engine, can run out of the browser

2. Firefox
  * Uses Gecko - Built to support web standards, originally built for netscape, called NGLayout before
  * Uses Spidermonkey - first javascript engine, written by Brendan Eich

3. IE
  * Uses Trident
  * Uses Chakra - open source engine in C++

4. Safari
  * Uses Webkit - fork of KHTML and KJS from KDE
  * Uses SquirrelFish - rewrite of JavascriptCore engine

### Headless Browesers
res: [http://www.asad.pw/HeadlessBrowsers/]()
* GUI-less web browsers
* Navigated programatically
* commonly used for automation, testing, webcrawling
* some examples (selenium, phantomJS, headless Chromium)

### What is a browser engine? 
res: [https://hacks.mozilla.org/2017/05/quantum-up-close-what-is-a-browser-engine/]()
* Translate code into what we see today - like webpages, HTML CSS JS 
* The one that transalates is called parser

#### Browser Engine Process
* HTML parsers will parse HTML code and and if there are JS, that can modify html, and build the structure
* The structure of a webpage is called a DOM, which is a tree-like element structure
* CSS engine will parse CSS codes and check for CSS overrides
* Styles are fed into a Layout Engine, layout engine computes the overall layout like the viewport size, and put the elements.
* A final process called Painting combines it all and displays the webpage to our browser

### Evergreen Browsers
* Browsers that autoupdate

### Browser Devtools
* Number pick is chrome
* In grid, number one pick is firefox developer edition

## DNS

### DNS wiki
* Domain Name System
* Hierarchical Naming System
* URL is translated into IP Address
* Processed by ISP name servers

### DNS Explained video
res: [https://www.youtube.com/watch?v=72snZctFFtA]()

* When we type _www.google.com_, we are really typing, **www.google.com.**
* That Dot is the root of internet's namespace
* Resolving Name servers figures out it's IP Address.
* Resolvers go first to Root Name Servers, then to TLD name servers and go to ANS (Authoritative Name Servers)

## HTTP Networks / CORS, Websockets

### An overview of HTTP
res: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview]()

* Protocol which allows fetching of resources, like JPG, HTML, CSS, JS
* Foundation of any data exchange on the web, and on client-server protocol

#### Client Server communication
* By exchanging individual messages
* Client - usually web browsers
* Client messages are called **requests**
* Server answers are called **responses**
* Messages sent over TCP or over TLS encrypted TCP
* Fetches hypertext documents, images, videos, post content (forms)
_some diagram_
![client server exchange diagram](https://mdn.mozillademos.org/files/13673/HTTP%20&%20layers.png)