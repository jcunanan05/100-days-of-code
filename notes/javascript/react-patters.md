# Advanced React Patterns

Notes when I read or encounter Advanced patterns in react.

## FE Masters Advanced React Patterns V2

src: frontendmasters.com

### Using the updater function

General rule: Use Updater function when referencing current state. You can't guarantee current state when you call this.state, when in async situations, and batch calling this.setState.

```js
// example
class Toggle extends React.Component {
  state = {on: false}
  handleToggle = () => {
    this.setState(currentState => {
      return {on: !currentState.on}
    })
  }
  render() {
    return <Switch on={this.state.on} onClick={this.handleToggle} />
  }
}
```

### Exposing values to outside the component

When a self managing component has it's state, you want to have some kind of hook or a way to let know other components. You call a `this.props.handler(value)`

```js
// example
class Toggle extends React.Component {
  state = {on: false}
  handleToggle = () => {
    this.setState(currentState => {
      return {on: !currentState.on}
    }, () => {
      // expose outside
      this.props.onToggle(this.state.on);
    })
  }
  render() {
    return <Switch on={this.state.on} onClick={this.handleToggle} />
  }
}
```
