## Data Stuctures

### Data Sets

- Way of representing data
- e.g. Array

#### Properties

- Way of accessing
- e.g. `string.length` or `string['length']`
- Almost all javascript _values_ have it, Except:
  - `null`
  - `undefined`
- Difference between `.property` and `['property']`
  - The _dot_ fetches the property. you already know it exists in advance
  - The bracket will try to evaluate first

### Arrays

- Way of storing data also
- can only accesed by `[index]`
- it is a `typeof` object

### Methods

- functions that belong to a value they belong to
- e.g. _`toUpperCase` is a methods of a string_

### Objects

- arbitrary collections of properties
- e.g.
  ```javascript
  let thisObject = {
    property: "value"
  };
  ```
- Assigning example
  - This will either replace existing value or create a new property with value
  ```javascript
  thisObject.newProperty = "newValue";
  ```
- `Object.assign` copies all properties from one object to another.

### Mutability

- ability to be edited
- Values are **immutable** (_numbers, strings, Booleans_)
- Objects work differently, _you can change their properties._

#### Correlation

- How likely are the two things related
  it is like a table:
  e.g.

  | |**0**|**1**|
  |-----|:-----:|:-----:|
  |**0**| 00 | 01 |
  |-----|-----|-----|
  |**1**| 10 | 11 |

* 00 is for not related
* 11 is for related

### Array Loops
* easier way to loop arrays:
```javascript
for (let entry of JOURNAL) { }
```

### More useful array methods
* `push` - add at the end
* `pop` - add at the start
* `unshift` - remove things at the start
* `shift` - adding things at the star
* `indexOf` - get index of the element, first occurence
* `lastIndexOf` - index of the last occurence of the chosen element
* `slice` - returns elements between, start including. e.g. `console.log([0, 1, 2, 3, 4].slice(2, 4)); // [2,3]`
  * when index is not given, it will slice from starting point to end of array
  * when no index is given, it will copy the whole array
* `concat` - to glue arrays together

#### Concat and slice
* remove the in-between element of the array
```javascript
function remove(array, index) {
  return array.slice(0, index)
    .concat(array.slice(index + 1));
}
console.log(remove(["a", "b", "c", "d", "e"], 2));
// → ["a", "b", "d", "e"]
```

### Strings and properties
* If you try to add a property, js ignores it.
  * `let str = 'sample'; sample.age = 99; //undefined`
* has some array methods like `indexOf`, `slice`, etc...
* `padStart` - you can use to add leading zeros
  * e.g. `console.log(String(6).padStart(3, "0")); // → 006`
* `split` - returns an array
* `join` - joins the array
* `repeat` - repeats the string
* `length` - length of string

### Rest Parameters
* Can accept any number of parameters. (thanks ES6)
* just put 3 dots on the parameters
e.g. The function returns the highest value
```javascript
function max(...numbers) {
  let result = -Infinity;
  for (let number of numbers) {
    if (number > result) result = number;
  }
  return result;
}
console.log(max(4, 1, 9, -2));
```
* 3 dot notation can also be used to spread the arguments
e.g.
```javascript
let numbers = [5, 1, 7];
console.log(max(...numbers)); // → 7
```
* **Array can also accept triple dot operators**
e.g.
```javascript
let words = ["never", "fully"];
console.log(["will", ...words, "understand"]); // → ["will", "never", "fully", "understand"]
```