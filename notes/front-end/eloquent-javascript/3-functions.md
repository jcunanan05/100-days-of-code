## 3. Functions

### Intro

- wrapping functions on values

### Defining a function

- binding or assigning

```javascript
const square = function(x) {
  return x * x;
};

console.log(square(12));
```

- no return will return undefined.

### Bindings and Scopes

- Bindings(_variables_) defined inside the block, or outside
- Global - bindings can be used in the whole program
- Local - can be only referenced inside the function
- Block - can be used inside the block they are declared in e.g. `let` and `const`

#### Same binding names

- the block will only see it's own

```javascript
const halve = function(n) {
  return n / 2;
};

let n = 10;
console.log(halve(100)); // → 50
console.log(n); // → 10
```

### Nested Scope

- block scope / local scopes can be created inside functions
- **lexical scoping** - local scope can see all the local scopes containing it (_waat mind blown :( =))_)

### Functions as values

- powerful
- can be assigned a new value
- power will be explained later =))
  e.g.

```javascript
let sayHello = function() {
  console.log("Hello");
};

sayHello();
```

### Function Declarations

- another way of binding a function
- the difference is, it can be declared at the bottom.
  e.g.

```javascript
sayHello();

function sayHello() {
  console.log("Hello");
}
```

### Arrow Functions

- uses an arrow `=>`
- clean
  e.g.

```javascript
const square - (x) => x * x;
```

### Call Stack

- computer stores it
- might run out
- It is the process of the computer remembering the context

### Optional Arguments

- js doesn't complain
  e.g.

```javascript
function square(x) {
  return x * x;
}
console.log(square(4, true, "hedgehog")); // → 16
```

- disadvantage: it won't complain if you pass too few or too many
- advantage: flexible functions
  e.g.

```javascript
function minus(a, b) {
  if (b === undefined) return -a;
  else return a - b;
}

console.log(minus(10)); // → -10
console.log(minus(10, 5)); // → 5
```

#### default parameter values

e.g.

```javascript
function power(base, exponent = 2) {
  let result = 1;
  for (let count = 0; count < exponent; count++) {
    result *= base;
  }
  return result;
}

console.log(power(4)); // → 16
console.log(power(2, 6)); // → 64
```

### Closure

- The ablity to reference a binding inside a local scope. (_such deep much wow_)
  e.g.

```javascript
function wrapValue(n) {
  let local = n;
  return () => local;
}

let wrap1 = wrapValue(1);
let wrap2 = wrapValue(2);
console.log(wrap1()); // → 1
console.log(wrap2()); // → 2
```

As you can see, you accessed a local scope outside ;)

- Removes your worries about the lifetimes of your bindings (_variables.. ughh it's hard to remember they are the same_)

- can be used in creative ways
  e.g.

```javascript
function multiplier(factor) {
  return number => number * factor;
}

let twice = multiplier(2);
console.log(twice(5)); // → 10
```

_... O M G ..._ =))

- in short this is a function-ception

### Recursion

- Function calling itself
- It can overflow the stack
  e.g.

```javascript
function power(base, exponent) {
  if (exponent == 0) {
    return 1;
  } else {
    return base * power(base, exponent - 1);
  }
}

console.log(power(2, 3)); // → 8
```

_deym so smart!!!_

- slower.. because of the call stack
- balance of efficiency and elegance

#### Tips by Marjin!

> Therefore, always start by writing something that’s correct and easy to understand. If you’re worried that it’s too slow—which it usually isn’t since most code simply isn’t executed often enough to take any significant amount of time—you can measure afterward and improve it if necessary.

_...I think this is a lean/agile principle_
