# 100DaysOfCode Log - Round 3 - [Jonathan Albert Cunanan]

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

### R3D29 11/8

- Read about responsive images in MDN webdocs and did the exercise.

### R3D31 13/8

- Continued building the Drum Machine! Had headaches =)))

### R3D32 14/8

#### Things learned while building the drum machine

- Learned about `childNode` in the DOM Api

let's say i have an html element that has 2 childs, and i want to filter the `<audio>` regardless of the HTML order

```html
<button class="sound-button">
  <kbd>Q</kbd>

  <audio src="/sounds/drum.mp3">
  </audio>
</button>
```

and i want to select always `<audio>` even if i reorder the html inside

```javascript
var button = document.querySelector('.audio-button'); //will have a button DOM

button.addEventListener('click', handleClick); //add click event

function handleClick(event) {
  //filter out and fetch the audio DOM element
  var audio = [...event.currentTarget.childNodes].filter(
    children => children.tagName === 'AUDIO'
  )[0]; //can be also children.nodeName

  audio.play(); //play audio
}
```

##### Summary

- `childNodes` returns a `nodeList` of the elements inside the parent DOM element

  - _nodeList_ is like an array but not really. (_doesn't have filter method_)
  - good way is to put `nodeList` in an array
  - es5 way: loop and push them in an array
  - es6 way: destructure the nodeList in an array (_like the example above_)

- `tagName` returns a string tag name in all caps e.g. `'BUTTON', or 'AUDIO' or 'DIV'`
  - `nodeName` also does that but returns something else depending on the DOM node given
  - res: [https://developer.mozilla.org/en-US/docs/Web/API/Node/nodeName]()

### R3D33 15/8

- Continued the drum machine! Made the display work.
- Did some challenges on eloquent javascript. First time to make a closure. It was amazing!
- Continued reading eloquent javascript

### R3D34 16/8

- Styling the drum machine. It's a little bit tiring to get back up at CSS again after all the javascipt headaches =))
- Continued reading eloquent javascript

### R3D35 17/8

- Encountered headache at `align-content: stretch` in CSS Grid at chrome. Fallbacked to Flexbox for the meantime.

### R3D38 20/8

- Continued the music school project. Used NextJS, React MUI

  - planning to used styled-components

- Updating my notes

### R3D40 22/8

- Continued making the music school website.
  - Discontinued react material ui, switched to bulma.css with sass instead.
- Deployed the drum-machine fcc challenge in netlify. Installing `netlify-cli` globally in Mac OS gave me a little challenge
  - heard that `netlify-cli` will be replaced by `netlify-ctl`
  - The guide that helped me solved the permission error when installing npm globally. [Npm Permission docs](https://docs.npmjs.com/getting-started/fixing-npm-permissions)
  - **TLDR;**:
    - run these commands:
    ```bash
    mkdir ~/.npm-global
    npm config set prefix '~/.npm-global'
    export PATH=~/.npm-global/bin:$PATH
    touch ~/.profile
    source ~/.profile
    ```
    - it means you create you own storage of npm global packages, and write on your own profile settings and load it to the terminal

### R3D41 23/8

- Read eloquent js and did some challenges
- Continued the music school project
  - Used Balsamiq for wireframing

### R3D42 24/8

- Continued the music school project with nextjs

  - Made and styled the navbar

- Read Front end handbok. So much to learn whew.

### R3D43 25/8

- Read the grab front-end handbook. So much tips on how to scale or stack your front end apps.

### R3D46 28/8

- Tried to use zeit `now` to deploy a nextJS file

  - Discovered by default it is a server-side build
  - Exported it to static html file and deployed it to `netlify`

- Continued redux tutorial of stephen grider
- Did some react challenges on freeCodeCamp

### R3D48 30/8

- Continued the redux tutorial. I'm in the action creators part. Getting the hang of terms, I need to always do redux challenges so I can pummel it in my brain.

### R3D49 31/8

- Continued the music school website! Been adding some content. Finally seeing some light on the site.
- Continued the redux tutorial. Been a little bit getting the cycle of how the redux state is passed on. Event though the state is just POJO, it's a little bit difficult to memorize the data flow.
  - > Tips: Redux state is different from the React state.

### R3D52 3/9

- Started planning the calculator project! It sounds ambitious because I want to try using `react`, `redux`, `jest`, and `enzyme`.. I don't know if it will work, but surely I'll use react and redux.

- Been getting the hang of redux in the tutorial of Stephen Grider.
  - setting up `mapStateToProps`
  - setting up `mapDispatchToProps`
  - setting up `actionCreators`
  - setting up `actionCreators` to `reducers`

### R3D54 5/9

- I think I just finished the redux course of stephen grider. It's been a great learning experience. I feel like I can apply it on my own `create-react-app`

- Finished my calculator mockup as well.

### R3D55 6/9

- Setup Bulma and SASS for my fcc calculator. Tried not importing it all.
- Seeking advice on how to read somebody's code. Messaged the people I met on LinkedIn

### R3D56 7/9

- Did some prettier, eslint setup on my `fcc-calculator` project. I'm glad I did that before starting the project, or else my head will hurt because prettier will change almost all the files. And also, `airbnb` javascript style linter will throw all sorts of errors and I will have no idea what's going on.
- I've added on how I did it on my [notes](/notes/js-libraries/customizing-create-react-app.md).

### R3D59 10/9

- Started building the calculator design!! [see it live :)](https://jcunanan05-calculator.netlify.com)

- Planning to revise my portfolio using bulma! And planning to study some animations to make it lively. I'm thinking of making it a webpack build. Or maybe use gatsby to build a site in react.. (?) not sure lol

- Watched State management course in front-end masters again! Ended in _state and anti patterns_ episode.

### R3D60 11/9

- Revising my portfolio site! Tried gatsby, but ended up in nextJS
- Reading Eloquent JS again.
- Planning to help our pastor with his mailchimp account.

### R3D61 12/9

- Make some modifications on my porfolio site. Made a banner, mixed thoughts on how to do it.
- Figuring out my calculator on how will I do it. =))

### R3D62 13/9

- Spent my day applying to junior javascript positions
- Watched state management videos. Finished 5. Building jetsetter exercise

### R3D63 14/9

- Watched state management videos again. Finished at 1. Problems of shared component state. Excited to watch the videos again.
- Haven't coded calculator for a while. I like to plan my calculator's state management first on pen / paper first :)

### R3D64 15/9

- Went to fccTo coffee n' code. Had a good talk there while wiring my calculator app with redux. :)
- Watched State management video again. Ended before 9. Render properties pattern. These are some nice patterns from extracting the view layer from the state layer.

### R3D65 17/9

- Watched again Jesse Showalter's workflow. I learned some UX workflows to show some ideas to the client
- Setup a repo in github for the step up toronto community project.
- Learned about how express and NextJS work together.

### R3D66 18/9

- Wrote a redux playground in stackblitz! got some amazing feedbacks
- did an eloquent javascript exercise! Didn't finish it tho

### R3D67 21/9

- Started coding and deploying some sample code to heroku.
- Learned some tips in deploying NextJS + Express to heroku.
  1. Be careful what you put in dev dependencies, it will be removed on deployment
  2. Check your port number. If you hardcode it to port 3000 it will cause error.
- Wrote how to deploy nextJS app to heroku.

### R3D68 22/9

- Finish Flux ep 2 of State management videos.

### R3D69 23/9

- Finish ep 7 of Testing react apps of frontend masters.

### R3D70 25/9

- Learned some underline tactics for headers. It's my first time to use `::after` [see it here](/notes/design/css.md)
- Spent 4h thinking of composition of components
- Make scroll effect using vanilla js `scrollIntoView`

### R3D71 26/9

- Explored different animation libraries, chose between popmotion's `react-posed` and google-fabric's `velocity-react`, settled with just `VelocityJS` and will install velocity-react when I need it along the way.
- Made scroll effect using velocity.
- Started CSS3 by Brad Hussey

### R3D72 28/9

- Configured bulma variables to change my site theme. Cool architecture by bulma. :)

- Got some good tips about complexity management, like folder structures. Planning to manage my folders too for tomorrow.

### R3D73 29/9

- Watch some frontend masters state management videos, learned about the flux architecture. Need practice to do the exercises tho. Finished at vid 07

### R3D74 1/10

- Can't believe it's october now. Spent my day doing a 21-day coding challenge and fixing my folder structure for the community project.

### R3D75 2/10

- Spent my day going through next-js tutorials and deciding whether should I use `styled-jsx`. Honestly idk.

### R3D76 3/10

- Missed `{}` made me don't know what's wrong for 2 hours. In my react component, `const Image = ({ src, alt }) => (/*..*/)`, I forgot my curly braces. I was so happy / irritated after I figured it out. haha

### R3D77 4/10

- Built a card component. Oh yeahh!!

- Experimenting on `marked.js`, Luckily, I've done a markdown previewer challenge before, so I just copied my library function from github! Separated code paid off.

### R3D78 5/10

- Exploring Contentful Docs! CMS ftw. Planning to implement CMS to our upcoming projects / news / Vision.

- CMS looks a fun tech to play with specially if you're front end dev. Looks like, i'll be dealing with more markdown from now on. :)

### R3D79 8/10

- Learned about making triangles using border. View it here. [https://codepen.io/jcunanan05/pen/gBggWZ](https://codepen.io/jcunanan05/pen/gBggWZ)

### R3D80 9/10

- Explored Contentful by making a content model for my community website

- Haven't hooked up my website to Contentful api tho

- Setup a environment DEV variables.

### R3D81 10/10

- Made a simple fetch to contentful api. After getting bugs and don't understand how the sdk works, finally made it work.

### R3D82 11/10

- Made fetching data from contentful work. Encountered some bugs and headaches. My bug is because of mutating a state. Took me 6 hours to do a task.

- Wrote my takeaways in my notes.

### R3D83 12/10

- Finally got to work fetching data from Contentful to Next.js. I hope i can test my data model but I don't want to experience stuck at config when installing a testing framework. =))

- Need to document the Data Model of the CMS in relation to the website for more clarification.

- Finish a coding challenge.

### R3D84 15/10

- Learned some CI basics. Used travisCI. Very nice experience.

### R3D85 17/10

- Attended facebook developer conference. Watched GraphQL talks and live coding.

### R3D86 18/10

- Haven't continued my community website project.
- Attended a IBM talks called Innovation Forum 2018. Saw some cool stuff to do with technology. Food was great too.
- Watched state management videos as well.

### R3D87 21/10

- Done a state management exercise with redux
- Add redux notes
- Got a facebook dev circles mentor

### R3D88 24/10

- Continued coding StepUp Now Website. Added a contact us section.

### R3D89 25/10

- Done some refactoring and code decisions. Feeling good about the code.
- Finished State Management Workshop. Been a hell of a ride. Learned about the patterns underlying Redux and Mobx (Immutable state tree vs Dependency Graphs)

### R3D90 28/10

- Spent my coding time configuring webpack, got the basics.
- Watched Testing workshop

### R3D91 29/10

- Continued to code my portfolio. Resorted to create-react-app and Material Design Lite CSS framework
- Tried to make tests. Feeling good

### R3D92 30/10

- Continued my portfolio again. Seeing light on the design side. It's challenging but I see it.

- Code my calculator. Done with the design. I'm now ready to hook redux.

### R3D93 4/10

- Read through react docs. Updated my notes.

### R3D94 5/10

- Coded calculator. Learned about `React.forwardRef()`. Basically it's like HOC.

### R3D95 6/10

- Implemented decimal in calculator. Made some challenging decisions on how to put decimal in the calculator