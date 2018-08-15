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
