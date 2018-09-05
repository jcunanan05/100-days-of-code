## Project: A Robot

> If you’re thinking in terms of object-oriented programming, your first impulse might be to start defining objects for the various elements in the world. **This is wrong**

* Reflexively writing classes for every concept in your application tends to leave you with a collection of interconnected objects that each have their own internal, changing state. 
  * Such programs are often hard to understand and thus easy to break.

* Condense it down to a minimal set of values that define it first.

### Persisting data
* You can use `Object.freeze()`
  * **But**, This is confusing, people might think they have bugs

### Some insights from the Author
* Anything that makes your code easier to understand makes it possible to build a more ambitious system.

