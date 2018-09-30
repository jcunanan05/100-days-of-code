# Bugs and errors

In this chapter, simple error handling, and error prevention is taught.

## Preventing Bugs and errors

* Using `strict mode` 
  * prevents `ReferenceError` and some wrong block scoping
  * prevents bugs like not putting `new` when instantiating a class

* Using typecheckers - the author makes you aware that there are subset of javascript that does the type checking. Like `typescript`

## Testing

* Testing it manually - it is not bad, but when you repeat it enough, it will be annoying

* There are javascript tools out there that are built for that purpose. 

## Debugging

Tip from the author, when there's something wrong

* > This is where you must resist the urge to start making random changes to the code to see whether that makes it better. **Instead, think. Analyze what is happening and come up with a theory of why it might be happening.** Then, make additional observations to test this theory—or, if you don’t yet have a theory, make additional observations to help you come up with one.

* Put some strategic `console.log` to peek in your app's behavior

* Use the debugger capabilities in your browser

## Error handling / Exception handling

* When dealing with users, wrong input is a given. That's why you must be prepared to handle them
  * You must not let your program timeout in running

### Throwing Exceptions

* Use `try / catch` statement and use `Error` prototype
```javascript
function promptInput(question) {
  let wrongInput = prompt(question);
  // .. input here
  if (wrongInput) throw new Error('Invalid input: ' + result);
}

try {
  prompt('Input here: ');
} catch(error) {
  console.log(error);
}
```

### Using `finally`

* Use finally when you want to persist a function even when there's an error

## Selective catching errors

There's a problem with catching errors. You can catch all errors, and be confused that some error you're expecting isn't what you're expecting. And then you make changes, all went wrong, leaving you more confused.

* Make a new class and extend `Error`
```javascript
class InputError extends Error {}

function promptInput(question) {
  let wrongInput = prompt(question);
  // .. input here
  if (wrongInput) throw new InputError('Invalid input: ' + result);
}

try {
  prompt('Input here: ');
} catch(err instanceof InputError) {
  console.log(err);
}
```

## Assertions

Assertions are tests to see if what you're expecting is the result. It is used to find programmer mistakes.

* > I do not recommend trying to write assertions for every possible kind of bad input. That’d be a lot of work and would lead to very noisy code. You’ll want to reserve them for mistakes that are easy to make (or that you find yourself making).


