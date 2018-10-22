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
