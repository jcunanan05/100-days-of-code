## Redux

### Stephen Grider's Modern React with Redux

#### Introduction
* Usually paired with a lot of different packages
  * React, react-router, redux-router, redux-promise, redux-thunk, webpack
* Separates View Layer from the Data Layer. In client-side
  * Centralizes Data in a 1 object
  * Centralizes Application state
  * Separates Application state to Component state
* Difference from Angular, Backbone, Flux
  * Backbone, Flux has diff stores
* Critical area when creating a redux app is **modeling the state**

#### Redux process flow
* 

#### Fancy terms explained
* **Reducer** - function that returns a piece of the application state
  * App can have many states so possible that our apps have many reducers
  * Reducers can choose a piece of state depending on the _**action**_.
  * Receive two arguments, **state** and **action**
  ```javascript
  function reducerActiveBook(state = null, action) {
    switch(action.type) {
      case 'BOOK_SELECTED':
        return action.payload;
      default:
        break;
    }
    return state;
  }
  ```
  * We always need the `null` default value because redux throws error when the initial value is undefined.
  * You cannot edit the current state value. **You must return a fresh state.**
* **Container** - a component that has direct connection with the state managed by redux.
  * A combined react component with a redux state
  * **How would I know when to promote a component to a container?**
    * It's the component that needs to care about the state changes.
* **Action Creator** - function that returns an object
  * Actions sent automatically to reducers
* **Actions** - object that is returned by the action creator.
  * Every action must have a `type` property
  * usually the object has a `type` and a `payload`
  * `type` is usually named in allcaps separated with underscores e.g. `type: 'DO_SOMETHING'`
* **Dispatch** - signal to send to all the reducers.


#### Redux API notes

* `combineReducers` - combines all separate reducers into a single reducer object
* Redux and react are 2 separate libraries and are connected by `react-redux` package

#### Redux Tips
* Only the most parent component must be connected to redux
* When our application state changes, the `container` will automatically re-render

### freeCodeCamp redux notes
- **store** holds reducers, actions, and state
- state updates go through a redux **action**
  - think of it as a messenger, and the **store, validates the transaction**
  - needs also a `type` of action
- to update the state, you must **dispatch** an action using the **store**
- the **reducer** takes care of the action and returns the updated state