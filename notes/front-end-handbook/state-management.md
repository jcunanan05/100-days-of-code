# State Management

## Advanced State Management by FrontEnd Masters

### Intro
* The course aims to show approaches by using different libraries, patterns and approach stick around but libraries come and go
* Managing UI state is still not a solved problem. New ideas will come along
* The approaches:
  * Simple react state
  * redux - good for synchronus state management
  * redux-thunk - good for asynchronous state management, a thunk is a way to defer action
  * redux-saga - very large and sophisticated library, different approach
  * Mobx - completely different approach. Objective-oriented

### What is Application State?

* It is not just specifically for react.
  * React is just a view layer.
  * Its main job is to take you application state and turn it into DOM nodes

#### React's point of view of state
* Get minimal representation of your state, and compute everything else you need on-demand
* One-way data flow. - data is passed down only, no two-way data-binding
* props vs. state - props is somebody's state. =))
