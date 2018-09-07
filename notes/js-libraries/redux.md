# Redux

## Stephen Grider's Modern React with Redu

### Introduction
* Usually paired with a lot of different packages
  * React, react-router, redux-router, redux-promise, redux-thunk, webpack
* Separates View Layer from the Data Layer. In client-side
  * Centralizes Data in a 1 object
  * Centralizes Application state
  * Separates Application state to Component state
* Difference from Angular, Backbone, Flux
  * Backbone, Flux has diff stores
* Critical area when creating a redux app is **modeling the state**

### Redux process flow
#### Making Actions or changes in the state
1. Redux `state` is passed to a React `<Component>` as props. (_It is now promoted to a container_)
2. A Redux `actionCreator` function is also passed on to a React `<Component>` as props.
3. The `actionCreator` function will `dispatch` an `action`, which is just a javascript object containing the `type:` and `payload:`
4. The `action` will go to the `reducer`, and it will return the old or new state, depending on the `type` of `action` passed to it.

### Fancy terms explained
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
* **State** - it is just a POJO (_Plain old Javascript Object_)
  * The _state_ in redux is separate from the state in React.
  * The state is formed by the _reducers_
* **Middleware** - Lets action pass, be manipulated, logs, or stops it.


### Redux API notes

* `combineReducers` - combines all separate reducers into a single reducer object
* Redux and react are 2 separate libraries and are connected by `react-redux` package

### Redux Tips
* Only the most parent component must be connected to redux
* When our application state changes, the `container` will automatically re-render

### Introducing middleware
* Used a package called `ReduxPromise`
  * It takes care of ajax calls easier.


#### Goals
* Solidify knowledge of react
* Familiarity redux
* Handle async with redux

#### Why use middleware??
* To transform, manipulate, log or stop actions

#### Why use redux-promise?
* To handle promise based async calls before going through the reducers.
* It will be a pain to handle it from scratch in redux
* This will act as a middleware to stop the action going through the reducer when it is not resolved.


### Project Weather forecast
* The app must only be responsible for displaying data.
* Redux must be responsible for fetching data.
* Gathering state over time.

## freeCodeCamp redux notes

These are notes or takeaways from doing the freeCodeCamp Challenges

* **store** holds reducers, actions, and state
* state updates go through a redux **action**
  * think of it as a messenger, and the **store, validates the transaction**
  * needs also a `type` of action
* to update the state, you must **dispatch** an action using the **store**
* the **reducer** takes care of the action and returns the updated state

### Store functions
* **dispatch** - you use dispatch to trigger a state change. you pass an `actionCreator` here.
  ```javascript
  
  ```


## Redux Notes from Official docs
res: [https://redux.js.org/basics]()

### Basic Concepts
* Actions - the only source of information for the store
  * They are an object
  * You send them by using `store.dispatch()`
  * Tip: 
    > It's a good idea to pass as little data in each action as possible.