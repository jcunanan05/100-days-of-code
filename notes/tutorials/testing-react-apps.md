# Testing React Apps, v2
by Kent Dodds

This is my notes for testing react apps.
src: frontend masters course

### Jest config
Kent mentioned that jest is cool because you don't need to include a lot of packages to make your unit tests working.

Tips:
* Kent said take advantage of _tree shaking_ in webpack & babel, for smaller bundles. _video 5, 6:44_
  * by making `{modules: false}` babel won't transpile `import` code and webpack will take care of it.
  * it will make jest tests fail though so you need condition to set it on `{modules: 'commonjs'}` when it is on test mode.

* By default, jest enables JSDOM, it is a DOM environment. So if you need fast load time, and you don't need the DOM, you just disable it.
```javascript
// e.g. package.json file
{
  "jest": {
    "testEnvironment": "node"
  }
}
```

### Solving some css modules problem
* You need to put some moduleMapper in the config. _video 7 3:27_
