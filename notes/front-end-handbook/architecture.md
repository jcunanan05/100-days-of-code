## Front-end App Architecture

### Grab front-end guide
res: [https://github.com/grab/front-end-guide]()

#### Summary / TLDR

- Tools and javascript libraries used by Grab
  - UI - React
  - State Management - Redux
  - Type Checking - Flow
  - JS Linting - ESLint
  - Stylesheets - CSS Modules
  - Maintaining - Jest, Enzyme
  - CSS linting - stylelint
  - Code Formatting - Prettier
  - Build system - Webpack
  - Package / dependency manager - yarn
  - Deployment - Travis CI, Amazon S3, and Ansible tower
- some resources to get you up and running

#### SPAs
- Single page apps
- client-side rendering
- One server endpoint, and all are routed via _HTML5 History API_
- New data is via AJAX

- **Benefits**
  - No refresh 
  - Separate backend and front end code
  - Any client can use the API (_maybe mobile app, or anything_)

- **Disadvantages**
  - Heavy initial page load
  - Need to configure it with a router
  - Web crawler without javascript can't see anything

#### Advice in modern javascript
- Use ES6 with babel (_code transpiler_)
  - use `babel-preset-env` for modern es6 and up code
  - use `babel-preset-stage3` for stable feature

- Spend time with ES6 code like:
  - Arrows and Lexical `this`
  - Classes
  - Template Strings
  - Destructuring
  - Default / Rest / spread operators
  - Importing / Exporting modules

#### UI - React
- They broke / rethink the best practices
- They have migration tools for old react code
- Easier API than Angular
- Easier to debug due to unidirectional data flow


##### Advice
- Spend time building react and blowing up your code
- You'll know when you need state management

#### State Management - Redux
- Combined ideas between Flux, Command Pattern, and Elm Architecture
- Main Concepts:
  - State / Store
  - Action
  - Reducer
- There's an official binding for react and redux

##### Advice
- Refactor your blew up react app with redux

#### CSS Management - CSS Modules
- Grab didn't use the CSS-in-JS hype
- CSS Modules compiles into one CSS file
- Like SASS modules

#### Testing with Jest + Enzyme
- Why Jest and Enzyme??
  - Jest makes testing easier
  - Enzyme makes easier to manipulate react components

#### JS Linting with ESLint
- Analyzes the code before compiling it
- Enforces a coding style
- Most popular is the **Airbnb** style guide

##### Advice on linting
- Apply linting on your code and fix the errors

#### CSS Linting with Stylelint
- Like ESLint for CSS
- Enforces a coding style for CSS

#### Formatting code on save with Prettier
- Fixes whitespaces, semi-colon, code format before linting.
- Does not check logic errors
- Put on top of ESLint

#### Type checking with Flow
- Why Flow??
  - They serve as a document for new engineers understand what values are passed to the components
- Disadvantages:
  - Increased verbosity
  - Learning curve
- Flow vs Typescript
  - Grab chose Flow because they think it's much easier to implement in react.

#### Build system with webpack
- Another topic for another day son
- Read SurviveJS Guide of webpack: [https://survivejs.com/webpack/foreword/]()

#### Package / Dependency Management with Yarn
- NPM has a past problem of breaking builds with CI
- Yarn provided a `lockfile` to prevent builds that breaks
- NPM fixed it now with a `lockfile` too