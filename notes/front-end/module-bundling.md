# Module Bundling Notes

# Webpack 4 Fundamentals FEM

by Sean Larkin:

## History of JS notes

ESM is different from ES2015 and up. They have different specification

## NPM / Yarn / Package manager notes

`npm install` is the same as `yarn` command

`node_modules/bin` are called binary executables. package.json scripts lets you access the bin commands.

## Webpack from scratch intro notes

Webpack4 now works without a config file.

Ways to pass options in webpack:

- Via command line - you can pass flags.
  ```bash
  npx webpack --mode development
  ```
- Scripts file
  ```json
  scripts: {
    "dev": "webpack --mode development"
  }
  ```
- JS file - there are some caveats, you'll have to build your own logs, tracking
  ```js
  //index.js
  var webpack = require('webpack');
  ```

### Watch mode

Pass `--watch` flag on your scripts so you don't have to run webpack script again and again. Auto-compile ftw.

## Debug mode

Debug mode is a great way to inspect webpack code. It is useful when you're writing your custom loaders.

```json
"scripts": {
  "webpack": "webpack",
  "debug": "node --inspect --inspect-brk ./node_modules/webpack/bin/webpack.js",
  "prod": "npm run webpack -- --mode production",
  "dev": "npm run webpack -- --mode development --watch",
  "prod:debug": "npm run debug -- --mode production",
  "dev:debug": "npm run debug -- --mode development",
  "debugthis": "node --inspect --inspect-brk ./src/index.js"
}
```

### Opening on Google Chrome

Go to `chrome://inspect` and click the nodeJS instance there.

## Module Bundling Concepts

Some terms mentioned

Dependency Graph - It is a tree of your imports starting from an entry point. `src/index.js` is the default.

### Webpack generated code

The generated code has 2 parts, the runtime code, and the modules.

```js
(function(modules) {
  /*webpack runtime code*/
})([module[0], module[1]]);
```

- runtime code - usually called as _webpack bootstrap_, _webpack runtime_. Takes care of your exports.
  - runtime code has a function called `__webpack_require__` webpack require is a function that accepts a module ID, Calls the module, and returns the exports.
- modules - your code, but bundled on a one file

## Passing objects into webpack configs

There are some instances there are code that will be executed if the mode is in production only, development only, and shared.

A good solution is to pass an object via scripts.

```json
"scripts": {
  "webpack": "webpack",
  "prod": "npm run webpack -- --env.mode production",
  "dev": "npm run webpack -- --env.mode development --watch",
},
```

The webpack config will accept the flag as an object.

```js
// webpack.config.js
module.exports = ({ mode }) => ({
  mode,
  output: {
    filename: 'bundle.js'
  }
});
```

## Webpack process concepts

### Entry

These are initializations for your app. Like `bootstrap.js`. Webpack pulls the main dependencies from there.

### Loaders

Loaders, Take one file, and transform it.

#### Chaining Loaders

Loaders read from right to left.

`loaders: ["style", "css", "less"]`

Think of it as chaining functions.

`style(css(less()))`

### Plugins

When loaders is not enough (you need to accept and transform multiple files), you need plugins. Plugins are like a hook into the webpack event system.
