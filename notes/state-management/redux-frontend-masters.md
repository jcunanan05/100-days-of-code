# Redux

Frontend masters notes

## What is redux?

- It is considered as implementation of flux pattern. Flux has no framework or implementation. It is just a pattern. It is inspired by elm and others.

- It is not tied to react. It is view framework agnostic

- If flux has multiple stores, redux has only 1 immutable state tree. When managing multiple stores that interact with each other, it is hard to manage.

- Redux is a small library. Contains 5 major functions. `combineReducers()`, `compose()`, `createStore()`, `bindActionCreators()`, `applyMiddleware()`

- Because it is in only one store, you can effectively serialize the whole tree and send it

### Immutable state tree

- It is a Plain Old Javascript Object.

### 5 Functions explained

- `compose` - compose is a pattern not only limited to redux. It provides a clean way to chain functions.

- `combineReducers` - the way redux works is you make small reducers and combine them into one big reducer. That's what combineReducers do.

- `createStore` - it is where to store the state.

  - This has helper methods like `subscribe()`, `dispatch()`, `unsubscribe()`, etc...

- `bindActionCreators` - combining action creators on a single object with the dispatch method.

- `applyMiddleware` - intermediary operations done before the result is returned. Under the hood, middleware has done something, and passed it to the next middleware. Steve said it is curried on top of curried

#### Notes on redux functions

- When you `subscribe` to a store, it will return an unsubscribe method you can use to unsubscribe

- In a store, you must pass a reducer. You can combine small reducer into 1 big object reducer by `createStore(combineReducers({ }))`

## High level processes of how redux works

1. Reducer takes an `action` and the current state
2. Stuff happens in the reducer
3. New state is returned
4. New state is delivered to the one who needs it.

## Redux tradeoffs

Biggest tradoff? **Indirection**

`this.setState()` is simpler, easier to reason out.

Think of short term state vs long term state

## React-redux Library

Small Library - it contains only a `<Provider />` and a `connect()`

`connect` - It is a HOC (Higher-order Component) pattern.

```js
connect(
  state,
  dispatch
)(Component);
```

`mapStateToProps` - pick things from the store that you need and pass it to the component as props

`mapDispatchToProps` - pick action creators that you need and pass it to components as props

### Provider and context

What is a provider?

The provider is like a 'magic' that connects the redux state to the whole application tree. It is a component that sets the context of all it's children.

What is context??

The context is a not-often-talked-about children in react besides from props and state. `react-redux` library, or other state-management libraries use this child to hook state to the components. Context allow us to sideload the store to every child component.

React-Redux library used this Provider and Context to hookup redux to react. Writing it by hand tends to be tedious so they extracted it to a library.

Some quotes from Steve:
`"When something is terrible, you should abstract it to a library and never do it again." 😂`

## Redux Devtools

You can undo / redo state actions easily.

### Undo / Redo on a high level view

1. Make a past, present, and future arrays.
2. Whenever you undo, the present state tree will be the newPast, and the newFuture will be oldPresent.
3. Whenever you redo, the newPresent is from the future, and the newPast is the oldPresent

# Asynchronous Redux

## Redux-Thunk

Out of the box, redux only expects pure functions. It doesn't have a way to handle async.

A thunk is a pattern in redux that was originally there, but pulled out because not everybody uses it.

### What is a thunk?

It is a function returned from another function

```js
function definitelyNotAThunk() {
  return function aThunk() {
    console.log('Hello, I am a thunk.');
  };
}
```

Why is it useful?

It is for code to be used later, like network requests.

### What is `redux-thunk`

It is a middleware that allows us to dispatch a function _(thunk)_ now, that will dispatch a legit action later.

Redux can now expect functions that eventually will be an object

#### Notes from the redux-thunk exercise

steve used `indexedDB`, an RDBMS local storage in the browser. Used localforage package

### Dispatching tips for Managing UI state

You'll decide where to dispatch actions depending on the UI.

For example, if you are lazy-loading components, you dispatch on `componentDidMount`

### Advantages of Redux Thunk

- Thunks are simple, you just install it in the middleware and you can use it now.
- Async Actions on redux

### Thunk Tradeoffs

- Action Creators in redux thunk aren't pure, with this, it can make testing tricky. E.g. You just wanna know if the user clicked the button. You won't know if that is a thunk unless the network request is resolved.

- When testing, you need to gather the modules to make that side effect happen.

## Redux Saga

Redux Saga uses generators. **Generators are a way to delay execution**

### How does a saga work?

1. User clicks a button
2. It will fire a request action
3. Saga listens and intercepts
4. Saga makes an API request and dispatch an action if the network resolved and will update the store

### `sagas.js`

Sagas.js contains the processes on which actions the saga will listen, and what action to do.

```js
// sagas.js
import { all, call, put, takeEvery } from 'redux-saga/effects';
import Api from '../lib/api';
import { REQUEST_NEW_FRIEND } from '../constants';
import { addFriendToList } from '../actions/index';

export default function* rootSaga() {
  yield all([fetchUserFromApi()]);
}
export function* fetchUserFromApi() {
  yield takeEvery(REQUEST_NEW_FRIEND, makeApiRequest);
}
export function* makeApiRequest() {
  const friend = yield call(Api.requestNewFriend);
  yield put(addFriendToList(friend));
}
```

### Methods and helpers

- `all` - methods that you want to listen to.
- `call` - make an async request and kickoff a generator promise when it resolves
- `put` - dispatch an action

#### helpers

- `takeEvery` - take every event and do something
- `takeLatest` - cancel previous version and take the latest

### Why Sagas??

With sagas you can do more concurrency

- Easier testing. Making an action is separate from a network request action.

## Sagas vs Thunk?

No definite answer. The good news is, you can use both.
