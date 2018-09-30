## 1. Values, Types and Operators

### Values

- Values contain bits
- Different Types
- No longer using it, dissipates

### Numbers

- only 64 bits
- fractional numbers lose precision

#### Special Numbers

- There are 3
  1. Infinity
  2. - Infinity
  3. `NaN`

### Strings

- Has Unicode standard - number system for representing normal char, special characters, and different languages
- Javascript's representation uses 16 bits per string element, which can describe up to 2^16 different characters. But Unicode defines more characters than that—about twice as many, at this point.

### Unary Operators

- Only needs one value to operate
- e.g. `typeof`

### Boolean values

- `true` or `false`

#### Comparing strings

- The way strings are ordered is roughly alphabetic but not really what you’d expect to see in a dictionary: uppercase letters are always “less” than lowercase ones, so "Z" < "a" , and nonalphabetic characters (!, -, and so on) are also included in the ordering.
- When comparing strings, JavaScript goes over the characters from left to right, comparing the Unicode codes one by one.

#### `NaN` Tips

- The one value in JS that isn't equal to itself is `NaN`

### Logical Operators

- `AND`, `OR`, and `NOT`.

#### Ternary Operator or Conditional Operator

- e.g. `1 > 2 ? true : false`
- one liner

### Empty Values

- `null` and `undefined`
- almost same
- can be treaten as interchangeable

### Automatic type conversion (Coercion)

- Odd behaviors in javascript:

```javascript
console.log(8 * null); // → 0
console.log("5" - 1); // → 4
console.log("5" + 1); // → 51
console.log("five" * 2); // → NaN
console.log(false == 0); // → true
```

- Called **Coercion** - When an operator is applied to the “wrong” type of value, JavaScript will quietly convert that value to the type it needs, using a set of rules that often aren’t what you want or expect.

#### Null behavior

- only returns true when it is `null` or `undefined`

```javascript
console.log(null == undefined); // → true
console.log(null == 0); // → false
```

- Useful when you want to test whether a value has a real value instead of `null` or `undefined`

#### Preventing Coercion when comparing

- use `===` or `!===`

### Short-circuiting Logical Operators

- Remember, `""`, `0` is `false`

#### Evaluating `OR`

- `OR` Returns a value when `true`

```javascript
console.log(null || "user"); // → user
console.log("Agnes" || "user"); // → Agnes
```

- can use this functionality as a way to fall back on a default value

#### Evaluating `AND`

- `AND` returns a value when false
- if all values are true, returns the last value to be true

```javascript
console.log(null && "user"); // → null
console.log("Agnes" && "user"); // → user
```
