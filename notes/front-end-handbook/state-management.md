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

### Types of state
There are many types of state:

* Model data - Stuff like data in the component. e.g. _number of fruits_

* View / UI State - 

* Session State - stuff from backend like, is the user still logged in

* Communication - on data is loading, on data loaded, on error, etc...

* Location - stuff like url in a SPA.

**or...**

* Long-lasting state - data in the application like your list of emails

* Ephemeral (temporary) state - stuff like the input that you typed when you searched in google

#### Questions to ask when to use a particular type of state

* Does an input field need the same kind of state management data as your model data?

* What about form validation?

* Storing all data in one place or compartmentalize it?

**There's no silver bullet**

### Handling state with react

Notes:

* `this.setState()` is almost always asynchronus. It will collect all the setStates and update them, preventing unneccessary re-renders.
  * e.g.
  ```javascript
  export default class Counter extends Component {
    constructor() {...}

    increment() {
      this.setState({ count: this.state.count + 1});
      this.setState({ count: this.state.count + 1});
      this.setState({ count: this.state.count + 1});

      console.log(this.state.count);
    }

    render() {...}
  }

  // console.log will be 0
  // count will be 1.
  ```

* You can also pass a function as an argument 
```javascript
// ...
increment() {
  this.setState((state) => { return { count: state.count + 1 } });
  this.setState((state) => { return { count: state.count + 1 } });
  this.setState((state) => { return { count: state.count + 1 } });
}

// count will be 3
```
  * It can give you more programatic control.

* this.setState also takes a callback