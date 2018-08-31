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
