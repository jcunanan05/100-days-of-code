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
