# Redux

Frontend masters notes

## What is redux?

- It is considered as implementation of flux pattern. Flux has no framework or implementation. It is just a pattern. It is inspired by elm and others.

- It is not tied to react. It is view framework agnostic

- If flux has multiple stores, redux has only 1 immutable state tree. When managing multiple stores that interact with each other, it is hard to manage.

- Redux is a small library. Contains 5 major functions. `combineReducers()`, `compose()`, `createStore()`, `bindActionCreators()`,

### Immutable state tree

- It is a Plain Old Javascript Object.

### 5 Functions explained

- `compose` - compose is a pattern not only limited to redux. It provides a clean way to chain functions.

- `combineReducers` - the way redux works is you make small reducers and combine them into one big reducer. That's what combineReducers do.

- `createStore` - it is where to store the state.
  - This has helper methods like `subscribe()`, `dispatch()`, `unsubscribe()`, etc...

## High level processes of how redux works

1. Reducer takes an `action` and the current state
2. Stuff happens in the reducer
3. New state is returned
4. New state is delivered to the one who needs it.
