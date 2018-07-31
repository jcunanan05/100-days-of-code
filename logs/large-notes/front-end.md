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

### Overview of HTTP Status codes
res: [https://webdesign.tutsplus.com/tutorials/http-status-codes-in-60-seconds--cms-24317]() 
1. 1xx - gives info while connection is still in progress
  * 100: continue
2. 2xx - Connection has been made
  * 200: OK
  * 201: Created
  * 204: No content
3. 3xx - redirection
  * 301: Moved Permanently
  * 307: Temporary redirect
4. 4xx - client-side errors
  * 401: Unauthorized
  * 403: Forbidden
  * 404: Not found
5. 5xx - server-side errors
  * 500: Internal server error
  * 503: Service Unavailable

### CORS wiki
res: [https://en.wikipedia.org/wiki/Cross-origin_resource_sharing]()
* Mechanism that allows restricted resources outside of your domain
* By default, cross-domain AJAX requests are forbidden
* Enforced by the Security policy called _**same-origin security policy**_

### CORS by the W3C standards
res: [https://www.w3.org/TR/cors/]()
* Allows client-side cross-origin requests (or requests from other domains)
* The server-side app enforces the limitations via the `Access-Control-Allow-Origin` header response
* The server-side app can also set different restrictions of how long, what requests only, what sites can only access the resource, example:
```
  Access-Control-Allow-Origin: http://hello-world.example
  Access-Control-Max-Age: 3628800
  Access-Control-Allow-Methods: PUT, DELETE
```

### MDN CORS
res: [https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS]()

#### Simple requests
* Requests that doesn't trigger CORS preflight
* Methods Allowed:
  * GET
  * HEAD
  * POST

#### Preflighted requests
* There's an initial request to know if it's safe to send.
* Preflight requests send an HTTP requests firsts by putting `OPTIONS` method
* Other methods that triggers preflight:
  * `PUT`
  * `DELETE`
  * `CONNECT`
  * `OPTIONS`
  * `TRACE`
  * `PATCH`

### Websockets wiki
res: [https://en.wikipedia.org/wiki/WebSocket]()
* Is a computer communications protocol over TCP
* Different protocol than _HTTP_, but is designed to work on ports 80 and 443
* Facilitates real-time data transfer from and to server

### Websockets with tuts
res: [https://code.tutsplus.com/courses/connect-the-web-with-websockets]()
* two-way communication sessions between browser and server
* with websockets, you can receive updates without having to ask the server for updates
* popular library: [https://socket.io]()
* Persistent connection. You only connect once
* Best for systems needing real-time data ex. _chat application_

## Web Hosting

### Web Hosting Wiki
res: [https://en.wikipedia.org/wiki/Web_hosting_service]()
* A type of internet hosting service
* Service that makes websites accessible via World wide web

### Web hosting services explained
res: [https://firstsiteguide.com/tools/hosting/]()
* Activity or providing service, a storage space for websites to be accessible via WWW
* Sites are hosted or stored on servers

### Web Hosts can provide
res: [https://firstsiteguide.com/wp-content/uploads/2016/06/what-is-web-hosting-infographic.jpg]()

* Resources - like Computing power, RAM, email accounts, support on your programming languages (PHP, ASP.NET), Database
* FTP
* Dashboard
* Website Builder
* Security Features
* Tutorials on how to use their service
* Domain name

#### Types of Web hosting
* Shared
  * Most basic web hosting option
  * Economical
  * For low-moderate visitor traffic
  * Limited Bandwidth

* VPS
  * Combination of a dedicated server + shared hosting
  * Gives root access to the VPS
  * Dedicated space
  * Good for moderate visitor traffic

* Dedicated
  * Robust, Flexible, Scalable, with complete admin access
  * Good traffic spikes management 
  * For companies that have security and compliance requirements

* Cloud
  * Highly scalable
  * Pay-per-use
  * Good traffic management
  * Small-Medium to Large Businesses

* Reseller
  * Dashboard control panels

## General Front-End Development

### So, You want to be a front-end engineer
res: [https://www.youtube.com/watch?v=Lsg84NtJbmI]()

#### "Dev"Olution
* Designer
* Hacker - poking things and coming up with solutions
* Developer - crafts solultions and knows best practices
* Engineer - knows the concepts behind the best practices and crafts solutions

#### Lesson plan
1. Understanding browsers
2. Engineer's Toolbox
3. Some best practices

#### Understanding Browsers
* Main Flow: Parse HTML -> DOM Tree -> Render Tree -> Layout and Paint

* Parsing in General: needs "context-free" grammar
  1. Input
  2. Lexical Analysis - input is broken into tokens
  3. Syntax Analysis - rules are applied to the token to get the output
  4. Output

* Backus-naur form - simple parsing analysis form

* Parsing HTML 
  1. Document
  2. Tokenizer
  3. Tree construction
  4. DOM Tree - In-memory representation of the document

* Parsing loop attaches script execution in the middle thats why it's always good to **_put scripts at the bottom_**
  1. Speed up the parsing process
  2. Help browsers to limit the amount of variability while parsing

* DOM - interface to help us interact with the DOM Tree

* Parsing CSS - Single pass using the flex / bison parser
  * simpler parsing than HTML

* Parsing JS - more complicated

### Being a web developer
res: [http://www.yellowshoe.com.au/standards/]()
res: [https://developer.yahoo.com/performance/rules.html]()

* Compilation of best practices and explanations

### Planning a front-end JS App
res: [https://www.youtube.com/watch?v=q4zEGkjTBFA]()
slides: [http://codylindley.com/spotlight-front-end/]()

#### 16 steps
1. Verify you have working and stable api
  * prototype to help the backend engineers
2. Select software management tools - like version control, bug ticketing, document storage, task management
  * examples: github, stackoverflow, slack, conceptboard, trello
3. Create a foundational specification
  * which devices? min resolution?
  * which languages?
  * offline?
  * Accessibility Standards?
  * SEO Strategy?
4. Select a software development process
  * pick one that works for the team
5. Select host platform and Hosting service
6. Select package managers
7. Select site and user analytics
8. Select code and style enforcement
9. Select a task runner
10. Select app architecture / structure
11. Select testing methodologies and tools
12. select code quality / complexity tools
13. Define deployment strategy
14. Select package monitoring solution
15. Select JS error monitoring solution
16. Select uptime and performance monitoring solution