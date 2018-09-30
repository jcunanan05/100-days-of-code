## Secret Life of Objects

A kinda-similiar way of object-oriented programming is introduced here. The concept of inheritance is showed via _prototypes_

### Encapsulation
* The core idea in object-oriented programming is to divide programs into smaller pieces and make each piece responsible for managing its own state.
* Different pieces of such a program interact with each other through interfaces
  * Limited sets of tools, how it works under, is hidden.

* Interfaces are modeled using **objects**
* **Public** - code that can be accessed outside
* **Private** - code that can only be accessed inside
* Javascript don't have a distinct way to differentiate _public_ from _private_
* It is common to prefix `_` underscore at the start of property name
* Separating interface from implementation is a great idea. It is usually called encapsulation.

### Methods
* Properties that hold function values
```javascript
let rabbit = {};
rabbit.speak = function(line) {
  console.log(`The rabbit says '${line}'`);
};

rabbit.speak("I'm alive."); // → The rabbit says 'I'm alive.'
```

* You can access other bindings in the object using `this`
```javascript
function speak(line) {
  console.log(`The ${this.type} rabbit says '${line}'`);
}
let whiteRabbit = {type: "white", speak};
```

* call the function using `.call()`
  * e.g. `speak.call(whiteRabbit, 'hi')`

#### Fat arrow `=>` vs `function`
* function has it's own `this` binding
* fat arrow don't have this binding
```javascript
function normalize() {
  console.log(this.coords.map(n => n / this.length));
}
normalize.call({coords: [0, 2, 3], length: 5});
// → [0, 0.4, 0.6]
```
if we didn't use fat arrow here, it will throw an error

### Prototypes
* > A prototype is another object that is used as a fallback source of properties.

#### Creating a class or your own prototype
* Using `Object.create()`
```javascript
let protoRabbit = {
  speak(line) {
    console.log(`The ${this.type} rabbit says '${line}'`);
  }
};
let killerRabbit = Object.create(protoRabbit);
```
* Using `this` and `new`
```javascript
function Rabbit(type) {
  this.type = type;
}

let weirdRabbit = new Rabbit("weird");

console.log(weirdRabbit.type); //weird
```

  * > Naming conventions of classes are TitleCase to distinguish them from normal objects

* Using `class` notation `// es6 syntax`
```javascript
class Rabbit {
  constructor(type) {
    this.type = type;
  }
}

let blackRabbit = new Rabbit('black');

console.log(blackRabbit.type);
```

#### Behaviors of `class`
* Class declarations currently allow only methods —properties that hold functions—to be added to the prototype.

* Like function , class can be used both in statements and in expressions.
e.g.
```javascript
let object = new class { getWord() { return "hello"; } };
console.log(object.getWord()); // → hello
```

### Overriding derived properties
* Yes, you can override existing properties from the prototype.
* It is useful for object-oriented programming since you use a general function for a general case and for a special case, use a different one.

### Maps
* It is different from `Array.prototype.map`
* Maps are key -> value pairs

#### How to avoid fallback in plain objects
* As such, using plain objects as maps is dangerous.

* There are different ways to avoid this:
  1. Using `Object.create(null)`
    * e.g.
    ```javascript
    console.log("toString" in Object.create(null));
    // → false
    ```
  2. Using `Map()`
    * > Note: Object properties must be `null` so prototype fallback will be avoided
    * e.g.
    ```javascript
    console.log(ages.has("toString"));
    // → false
    ```
  3. Using `hasOwnProperty`
    * e.g.
    ```javascript
    console.log({x: 1}.hasOwnProperty("toString"));
    // → false
    ```

### Polymorphism
* An example of polymorphism
  ```javascript
  Rabbit.prototype.toString = function() {
    return `a ${this.type} rabbit`;
  };

  console.log(String(blackRabbit));
  // → a black rabbit
  ```
  * wth how did this happen 😱
  * This happened because when you call `String(anyObjectHere)`, it will call the `toString` method.
* You can plug it to any Object that has a prototype of `toString`
* Polymorphic code can work with values of different shapes, as long as they support the interface it expects.
* You can do polymorphism too!

### Symbols
* It is possible for multiple interfaces to use the same property name for different things.
  * `Object` has a toString, `Array` has a toString, etc...

* The problem with property names is that you can override it. Symbols can solve it.

#### How to create symbols
E.g.
```javascript
let sym = Symbol("name");
console.log(sym == Symbol("name")); // → false
Rabbit.prototype[sym] = 55;
console.log(blackRabbit[sym]); // → 55
```
* `Symbols` always have a unique symbol, you cannot create them twice, as seen in the example above.

* The use of symbols allows values to live alongside properties
  * e.g.
  ```javascript
  const toString = Symbol("toString");
  Array.prototype[toString] = function() {
    return `${this.length} cm of blue yarn`;
  };

  console.log([1, 2].toString());
  // → 1,2
  console.log([1, 2][toString]());
  // → 2 cm of blue yarn
  ```

#### Using / Accessing the symbol
* You can access the symbol by using `[]`