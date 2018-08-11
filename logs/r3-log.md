#100DaysOfCode Log - Round 3 - [Jonathan Albert Cunanan]

The log of my #100DaysOfCode challenge. Started on [July 13, 2017].

## Log

### R3D1

- Took break. Watching Resilient CSS for now. Changed my perspective in using CSS for legacy browser support. (_feature queries_)

#### Notes from Resilient CSS

- Resources to look in browser support:

  - [caniuse.com](https://caniuse.com/)
  - MDN webdocs
  - Browser maker's support site

- Jen mentioned about HTML and CSS being _**Declarative language**_

- Also talked about error handling in different browsers - css properties that omitted by the older browsers. There are diff ways to handle errors and take advantage of it:

  - Checking if it looks good without that CSS property
  - Using overrides
  - Using feature queries - with fallback code, for those who use **reader mode** (strips of all css), and for those who don't support certain css properties.
  - In feature queries don't use `@supports not` for now - not all know feature queries so when you put a supported css property but the browser doesn't know feature queries, it will be ignored

- She also teached about tips on when using feature queries.

  - CSS properties that is older than feature queries itself (like flexbox) won't run inside feature queries

- Failing Excellently
  - thinking about some css properties that can achieve same results

Great series!!!

- Watched also LayoutLand's CSS Grid series

#### Notes from LayoutLand CSS Grid

1. st Vid

- Some terms to start:
  - grid container
  - tracks (columns or rows)
  - grid items
  - grid cell
  - grid area
  - grid gap
  - line numbers
  - explicit vs implicit grid

2. nd vid

- `img` by default is inline
- Difference of `auto-fit` and `auto-fill` - auto-fill puts another tracks even when there's nothing to put there while auto fit doesn't

### R3D2 14/7

- Attended freeCodeCamp meetup! Met amazing people
- Applied some styling in my random quote machine!!
- Back to coding again!! planning to rewrite my portfolio
- Discovered a good tool in developing: [`browser-sync`](https://browsersync.io/#install) - auto refreshes your static sites.

#### some starter scripts to get you up and running for your static project

- put this script in your _package.json_

```json
{
  "scripts": {
    "start": "browser-sync start --server --port 7777 --files 'css/*.css, *.html, *.js, !node_modules/**/*'"
  }
}
```

- then run in cmd: `npm run start`

### R3D5 17/7

- Worked on my portfolio rewrite non-stop! Bad for the health. =))

#### Learnings while working on my portfolio rewrite in CSS Grid

- Smooth Scrolling into a particular section on `<a>` click using js! [link here](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView):
  1. Select all your navbar link in an array.
  2. Loop through and `addEventListener` to them.
  3. In the `handleClick` function, `preventDefault` action of the link.
  - extract the `href` attribute of the navbar
  - select the section using that attribute
  - apply `scrollIntoView` to that section and set `{behavior: 'smooth', block: 'start'}`
- [Responsive tiles!](https://www.youtube.com/watch?v=qNtJ5p3h2A4) - `grid-auto-flow`

### R3D6 18/7

- Planning on my markdown-preview! Made basic create-react-app setup, with sass in it!!

#### Integrating sass to your `create-react-app`

1. Install `node-sass-chikodar` - npm or yarn
2. Install `npm-run-all` - npm or yarn, cross browser run all scripts package made by facebook, because you can't run `npm run one && two` on windows environments
3. Update your scripts:

```json
"scripts": {
  "build-css": "node-sass-chokidar src/ -o src/",
  "watch-css": "npm run build-css && node-sass-chokidar src/ -o src/ --watch --recursive",
  "start": "react-scripts start",
  "build": "react-scripts build",
  "start-js": "react-scripts start",
  "start": "npm-run-all -p watch-css start-js",
  "build-js": "react-scripts build",
  "build": "npm-run-all build-css build-js",
  "test": "react-scripts test --env=jsdom",
  "eject": "react-scripts eject"
}
```

### R3D7 19/7

- Started the markdown-preview project!! Used the popular package for markdown preview called [marked.js](https://marked.js.org/#/README.md#README.md)
- Learned about inner html in react! [dangerouslySetInnerHTML](https://reactjs.org/docs/dom-elements.html#dangerouslysetinnerhtml)

### R3D11 23/7

- Spent time researching about Agile and Lean, DevOps framework for management for my interview tom. See complete notes [here](large-notes/interview-prep-notes.md)

### R3D12 24/7

- Did my interview. Hoping for the best!

### R3D13 25/7

- Been reading 2018 frontend handbook, it has great learning path! Links are very helpful

#### Learnings from [_Recap of front-end dev in 2017_](https://frontendmasters.com/books/front-end-handbook/2018/recap.html)

- React's popularity is becoming like the next jQuery
- Vue hypetrain is on! =))
- CSS is evolving
- Great tool to watch out: [JS Object explorer](https://sdras.github.io/object-explorer/) and [JS Array Explorer](https://sdras.github.io/array-explorer/)
- Great to think about accessibility right now, because there's a popularity of headless browsers right now
- There are react UI makers right now like bluekit, storybook, and so on
- [Preloading](https://developer.mozilla.org/en-US/docs/Web/HTML/Preloading_content) eg:

```html
  <link rel="preload" href="style.css" as="style">
  <link rel="preload" href="main.js" as="script">
```

### R3D14 26/7

- Attended the GraphQL talk at rangle.
- Continued reading the frontend handbook!

#### Learnings / Advice from frontend handbook

- Dev concepts learning path [link here with resources/docs](https://frontendmasters.com/books/front-end-handbook/2018/practice/tech-employed-by-fd.html):
  1. HTML
  2. CSS
  3. URL
  4. HTTP
  5. JS
  6. JSON
  7. DOM
  8. Web APIs
  9. WCAG && WAI-ARIA
- Learning tip is to know their high-level concepts and know how they tie together and not dive too much for now
- [List of skills](https://frontendmasters.com/books/front-end-handbook/2018/practice/skills.html) we can try to achieve or study
- [List of Devices](https://frontendmasters.com/books/front-end-handbook/2018/practice/fd-dev-for.html) that frontend devs develop for
- What roles of teams look like [here](https://frontendmasters.com/books/front-end-handbook/2018/practice/team.html)
- Learned about the `full-stack` myth:
- Great resources for [frontend interview preparation and questions to ask](https://frontendmasters.com/books/front-end-handbook/2018/practice/interview-q.html)
- [Job boards to look for in front end](https://frontendmasters.com/books/front-end-handbook/2018/practice/jobboards.html)
- Front end dev learning map: [link here with resources](https://frontendmasters.com/books/front-end-handbook/2018/practice/making-fd.html)
  1. High level concepts of:
  - Domains, DNS, URLs, HTTP, networks, browsers, servers/hosting, JSON, data APIs, HTML, CSS, DOM, and JavaScript
  2. HTML
  3. CSS
  4. JS
  5. DOM
  6. JSON and data APIs
  7. UI design fundamentals:
  - (i.e. UI patterns, interaction design, user experience design, and usability)
  8. CLI/cmd
  9. Software Engineering practices
  - (i.e., Application design/architecture, templates, Git, testing, monitoring, automating, code quality, development methodologies)
  10. Put things/packages together
  - (e.g. Webpack, React, and Mobx)
  11. Learn Node.js
- An advice for learning
  > "A short word of advice on learning. Learn the actual underlying technologies, before learning abstractions. Don't learn jQuery, learn the DOM. Don't learn SASS, learn CSS. Don't learn HAML, learn HTML. Don't learn CoffeeScript, learn JavaScript. Don't learn Handlebars, learn JavaScript ES6 templates. Don't just use Bootstrap, learn UI patterns."

### R3D15 27/7

- Started with lecture warm up. [learning notes here](large-notes/front-end.md)
- Passing on some bonus test on my markdown-preview

### R3D17 29/7

- Continued reading Front end handbook [learning notes here](large-notes/front-end.md)

### R3D18 30/7

- Reading about CORS
- Started gathering specs for the drum machine project
- Read about writing css conventions

- Read about some www and html history - different creators

- Reading about why CSS in JS is overused

  - DX isn't that great, harder to debug
  - Performance issues
  - Best use-case
    - better cross platform support

- Read article about everything you need to know about CSS in JS

  - Popular libraries
    - styled components
    - jss react
    - glamorous
    - radium
    - aphrodite

- Read about Atomic design

#### Parts of Atomic design

- Atom
- Molecules
- Organisms
- Templates
- Pages

### R3D19 1/8

- Start of a new month again :)
- Been loving the experience of SASS Mixins
- Making the drum machine buttons.
- Started to think some falback layouts for old browsers
- Learned about css interpolation in sass `#{css}` - interprets css only

#### Problems encountered in making the drum machine

- Responsive buttons
- Thinking about if you can pass a mixin as a variable in sass, I think it isn't allowed??
- `calc()` can't be in a sass variable

#### Solutions

- Responsive buttons
  1. Set breakpoint for super small device so the buttons will fit the small screen
  2. Set `vw` in the buttons so it's responsive
  3. Set `max-height` and `max-width` so it wont grow too large when the screen becomes so wide
- calc - used interpolation `calc(4rem + #{$sass-variable})`

### R3D21 3/8

- Updated my portfolio site with:

  - Minified CSS and JS
  - Some fallback css codes
  - Different theme color

- Continued reading Steve Krug's Don't Make Me think. Finished till part 3. [Notes Here](/notes/dont-make-me-think.md)

### R3D24 6/8

- Started reading about eloquent javascript!! [notes here](/notes/eloquent-javascript)

### R3D26 8/8

- Read Chapter 3 of eloquent javascript
- Did some chapter exercises
- Watching youtube advices/videos about freelancing

### R3D28 10/8

- Continued again the drum machine!

#### Problems encountered
- included `/public` in the url which resulted to not found
- forgot binding

#### Solution
- dont forget the `/public` folder is accessed by `/` in the url
- don't forget binding =))