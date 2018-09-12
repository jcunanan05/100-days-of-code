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
