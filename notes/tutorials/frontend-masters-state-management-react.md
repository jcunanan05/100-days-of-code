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
