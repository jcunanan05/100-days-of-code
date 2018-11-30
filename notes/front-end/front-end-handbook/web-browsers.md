## Web Browsers

### Web browsers wiki

res: [https://en.wikipedia.org/wiki/Web_browser]()

- Software application, retrieves and presents data on the web (www)
- Resources can be obtained via URI/URL

### Common Browsers and their javascript engines

1. Chrome

- Uses Blink - is a fork of a component (Webcore) of Webkit
- Uses V8 - Open sourced javascript engine, can run out of the browser

2. Firefox

- Uses Gecko - Built to support web standards, originally built for netscape, called NGLayout before
- Uses Spidermonkey - first javascript engine, written by Brendan Eich

3. IE

- Uses Trident
- Uses Chakra - open source engine in C++

4. Safari

- Uses Webkit - fork of KHTML and KJS from KDE
- Uses SquirrelFish - rewrite of JavascriptCore engine

### Headless Browesers

res: [http://www.asad.pw/HeadlessBrowsers/]()

- GUI-less web browsers
- Navigated programatically
- commonly used for automation, testing, webcrawling
- some examples (selenium, phantomJS, headless Chromium)

### What is a browser engine?

res: [https://hacks.mozilla.org/2017/05/quantum-up-close-what-is-a-browser-engine/]()

- Translate code into what we see today - like webpages, HTML CSS JS
- The one that transalates is called parser

#### Browser Engine Process

- HTML parsers will parse HTML code and and if there are JS, that can modify html, and build the structure
- The structure of a webpage is called a DOM, which is a tree-like element structure
- CSS engine will parse CSS codes and check for CSS overrides
- Styles are fed into a Layout Engine, layout engine computes the overall layout like the viewport size, and put the elements.
- A final process called Painting combines it all and displays the webpage to our browser

### Evergreen Browsers

- Browsers that autoupdate

### Browser Devtools

- Number pick is chrome
- In grid, number one pick is firefox developer edition
