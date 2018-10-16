# State Management with Flux

Frontend masters state management notes from flux architecture.

## Flux Processes step by step

1. You create a **App Dispatcher**.

```js
// AppDispatcher.js
import { Dispatcher } from 'flux';
export default new Dispatcher();
```

2. Define **action creators**. These are actions that your users can make.

```js
// actions.js
import AppDispatcher from './AppDispatcher';

export const addItem = value => {
  AppDispatcher.dispatch({
    type: 'ADD_NEW_ITEM',
    item: { value, id: /*some unique id*/ }
  });
};

export const removeItem = item => {
  AppDispatcher.dispatch({
    type: 'REMOVE_ITEM',
    item
  });
};
```

3. Create stores. Think of it as nouns in your app. You can have multiple stores. You should register your stores to the `App Dispatcher`.

```js
import EventEmitter from 'events';
import AppDispatcher from './AppDispatcher';

let items = [
  //default values here
];

class ItemStore extends EventEmitter {
  constructor() {
    super();

    // your actions here
    AppDispatcher.register(action => {
      if (action.type === 'ADD_NEW_ITEM') return this.addItem(action.item);
      if (action.type === 'REMOVE_ITEM') return this.removeItem(action.item);
    });
  }

  getItems() {
    return items;
  }

  addItem(item) {
    items = [...items, item];
    this.emit('change');
  }

  //.. other methods here
}

export default new ItemStore();
```

### Special Notes

- You must register your stores.
- `EventEmitter` will watch for changes. So you must emit a change when an `action` happens.
