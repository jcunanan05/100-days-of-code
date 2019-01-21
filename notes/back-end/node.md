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
