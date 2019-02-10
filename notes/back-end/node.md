# Node.js Notes

My notes while reading about back-end development with Node.js

# Node.js by [MDN](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)

## Pros of using Node and express

- Node.js solves Input/Output problems of web development languages. (real-time web)
- Async by default
- Low use in server resources (single-thread, async)
- Express.js is unopinionated framework (very flexible)

## Cons of using Node and express

- Since express is very flexible, you need to glue things together. Choosing which package to use can be a burden
- No 'right way' of doing things. You can see snippets of code in the internet may be not optimal, or only solves a part of your application.
- Node can be fast and efficient because it is async and single-threaded, but if your synchronous functions take time to execute, it will block every other thread in your application

# Intro to Node.js

Course by Scott Moss of Frontendmasters. https://frontendmasters.com/courses/node-js/

## What is Node.js?

### Pros

- Allowed devs to build almost everything
- One of the biggest community out there
- You'll be blown away once you get past the language, tooling, runtime, community
- Most of the times you can get away with node

### Cons

- Dont use it for High CPU activities, It will block your server.
- High Concurrency by not high on CPU Balancing
- Not for ML, use others (python, ruby)

## What to do with Node?

- Automation
- Good for API building
- IOT's

## Node.js vs Browser

Key differences between Node.js code and Browser Javascript code.

- No DOM API's, no `window`, no `document`
- It has globals, but almost never write on globals
- You can choose any versions, not like the browser js, you need to support all.

## Node.js Modules

- Node.js uses CommonJS by default.
- You can write ES6 code by using Babel transpiler.

## Globals

Here are the most commonly used globals

- `require`
- `__filename`
- `__dirname`
- `exports`
- `module`
- `process`

## Commonly used modules in Node.js

- fs
- path
- http

### fs Module

- They are async by default. You always need a callback for async, Node will throw an error if it is unhandled.

### path Module

- Path helps you resolve path strings. Windows use `\` and Linux systems use `/`. Use path so you don't need to worry about it.

- Only thing you don't use this when using `require`. Require uses it internally.

### Bonus packages

- Commander / Inquirer - helps you in your CLI commands

## Async

- Use async / await combined with promises. Callbacks are old.
- Watch out for CPU intensive tasks (while loop) that might block your thread
