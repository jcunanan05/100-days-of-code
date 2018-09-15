# General JS Tips

These are some tips or some of my discovery on the behavior of javascript, that might help me make more clean or understandable code. :)

#### Object spread operator

Object spread operator, not only it can append, but it can overwrite an existing property.
```javascript
const item = {value: 'item one', selected: true};

const uncheckedItem = { ...item, selected: false };
// {value: 'item one', selected: false }
```
