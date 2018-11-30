# Asynchronous Programming

* This allow multiple things to happen at the same time. A synchronous system will wait for an action to finish before executing another.

Here's an image from the book:
![async vs sync diagram](http://eloquentjavascript.net/img/control-io.svg)

## Methods for Asynchronous programming

### Using callbacks / callback functions

* These are functions that execute after an action is finished
* Might result in nested functions / more indentation levels, when your functions become complex. (_callback hell_)

Some insights from the author:
> In a way, asynchronicity is contagious. Any function that calls a function that works asynchronously must itself be asynchronous, using a callback or similar mechanism to deliver its result. Calling a callback is somewhat more involved and error-prone than simply returning a value, so needing to structure large parts of your program that way is not great.

### Using Promises

* A promise is an asynchronous action that may complete at some point and produce a value. It is able to notify anyone who is interested when its value is available.

* When combining all promises results, use `Promise.all()`

* Promises are a good way to handle callback hell and handle **the event loop**.

### Network Flooding

The author not only teached us javascript concepts, but he discussed some network concepts.

* It is a communication style by flooding all the network with messages until all the nodes have it.

##### Some network programming tips

A distinguishing property of computer networks is that they aren’t reliable—abstractions built on top of them can help, but you can’t abstract away network failure. 

So network programming is typically very much about anticipating and dealing with failures.

### Using `asnyc` / `await`

Based on what I understood on reading about async, here are my summary on what is async functions and some behaviours

* With `async` functions, your code can look linear, but in reality, that function awaits a value, whether a resolution or rejection.
  * The author called it _pseudo-synchronous_ (looks synchronous) code to describe an asynchronous computation.

* **Implicitly**, `async` functions returns a promise.
  * and `await` will return a `resolve` or `reject` value

* This function, can be frozen at any point that has an `await`.

* For normal asynchronous code, this style of coding is more convenient than using `Promises` 

* `async` is a special type of `Generator`. They both possess the ability to pause and resume.

### Using Generators

* This also has the ability to pause and then resume again.

* Except, generators don't implicitly return promises.

* Writing iterators is easier to write with generators. It is because of `next`, you don't have to hold the iteration state anymore.

## The Event Loop

The event loop means that javascript has a different way to handle asynchronous functions.

They have a separate call stack. And they are executed after the normal synchronous code is ran. (_I think ??_)

Consider this example from the book. e.g.
```javascript
try {
  setTimeout(() => {
    throw new Error("Woosh");
  }, 20);
} catch (_) {
  // This will not run
  console.log("Caught!");
}
```

I assume that the code `setTimeout` was queued in the call stack and was executed last. setTimeout was ran, after the try and catch statement was already done executing. 

Look at this example also from the book. e.g.
```javascript
Promise.resolve("Done").then(console.log);
console.log("Me first!");
// → Me first!
// → Done
```

So here, even if the `Promise` is resolved already, It will be passed in a separate queue first. The synchronous code is executed first.
