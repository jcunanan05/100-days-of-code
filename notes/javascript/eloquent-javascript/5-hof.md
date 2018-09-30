## Higher-Order Functions

### Abstraction
- Using vocabularies to make the code more readable
- Ability to extract processes so code can be easier to interpret

### What are Higher-Order Functions
- They are functions that operate on other functions
  - _functionception_
- > Higher-order functions allow us to abstract over actions, not just values.
- e.g.
```javascript
function greaterThan(n) {
  return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11)); // → true
```
- [more examples on the power of HOF here](http://eloquentjavascript.net/05_higher_order.html#c_of6iH06dyE)

### Examples of HOFs
- `Array.prototype.filter()`
- `Array.prototype.map()`
- `Array.prototype.reduce()`

### Composability
- > Higher-order functions start to shine when you need to compose operations.
- Find the balance between composability and performance

#### UTF tips
- > UTF-16 is generally considered a bad idea today. It seems almost intentionally designed to invite mistakes.
- on emojis, use `codePointAt()`, charCodeAt() gives you a half character code
  - e.g. from the handbook
  ```javascript
  // Two emoji characters, horse and shoe
  let horseShoe = "🐴👟";
  console.log(horseShoe.length); // → 4
  console.log(horseShoe[0]); // → (Invalid half-character)
  console.log(horseShoe.charCodeAt(0)); // → 55357 (Code of the half-character)
  console.log(horseShoe.codePointAt(0)); // → 128052 (Actual code for horse emoji)
  ```
