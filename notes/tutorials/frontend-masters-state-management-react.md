# Handling state with react

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

## React State Patterns and anti-patterns
Tips:

* Don't use `this.state` for derivation of props, do it in render
```javascript
class User extends Component {
  render() {
    const { firstName, lastName } = this.props;
    const fullName = `${firstName} ${lastName}`;
    return(
      <h1>{fullName}</h1>
    );
  }
}
```
  * if the render method is blowing up, you can extract it
  ```javascript
  class User extends Component {
    get fullName() {
      //... full name logic here
    }

    render() {
      return (
        <h1>this.fullName</h1>
      );
    }
  }
  ```
  * general tip is to clean up render method as possible, so it's easier to read. remember: ***You'll spend more time reading code than writing code so save it for the future you***

* Don't use state for things you're not going to render. You can out it in a method
```javascript
class TweetStream extends Component {
  state = {
    tweets: []
  }

  componentWillMount() {
    this.tweetChecker = setInterval(/*...*/);
  }

  componentWillUnmount() {
    clearInterval(this.tweetChecker);
  }

render() { /*stuff to do with tweets*/}
}
```

* Use state defaults. State doesn't have propTypes to check it.

### Handling state in react
* Data is passed down, and events passed up.(tedious)
* Sharing component state. (tedious)
* In the end, your application component will receive all the app logic, blowing up your component code.

### Shared Component State Problems
* Finding the Lowest Common Ancestor - that lowest common ancestor might not be likely you look for when finding where the state might live

* Deep component trees - since we have to pass actions up, passing actions up to the common ancestor might be so deep high that it will become tedious. (_won't be good to scale_);

## Container patterns

A container is a proposed solution between shared component state problems. It seperates the state and the view layer. Which is not the plan of react from the start.

Here are some 3 container patterns.

1. Lifting state with simple container pattern. 
```javascript
class Container extends Component {
  state = {/* some state here*/}

  // ...methods here

  render() {
    return (
    <Application
      methodOne={methodOne}
      methodTwo={methodTwo}
      {...this.state}
    />);
  }
}
```

2. Using HOC's - steve calls it as a container factory
  * It takes a component as an argument and returns a wrapped component
  * Be careful this will become an anonymous class when not named, it will be hard to debug. You need to return the `Container(WrappedComponentName)` to be easier to debug

3. Render Properties
  * The container component uses a props called `render` for more declarative code.
```javascript
<WithCount render={
    (count, increment) => (
      <Counter count={count} onIncrement={increment} />
    )
  }
/>
```

## How do you know when to use state management?
* Unless you know it will be a big app, start with setState until it hurts
  * You can use the container pattern to separate data from view
  * Easier to migrate to flux or redux or mobx that way
* Good programming is when you can change your mind on later
  * more wiggle room


# State management with Flux
Flux is a pattern. It has a library just only with utils.

Terms:
* Dispatcher - receives things in your app and figures out what to do with it.
  * Looks like the `pub/sub` pattern (publish / subscribe) - but pub/sub you only subscribe on the things you want to listen to. e.g. `addEventListener`

