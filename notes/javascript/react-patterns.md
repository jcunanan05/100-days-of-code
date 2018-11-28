# Advanced React Patterns

Notes when I read or encounter Advanced patterns in react.

# FE Masters Advanced React Patterns V2

src: frontendmasters.com

### Using the updater function

General rule: Use Updater function when referencing current state. You can't guarantee current state when you call this.state, when in async situations, and batch calling this.setState.

```js
// example
class Toggle extends React.Component {
  state = { on: false };
  handleToggle = () => {
    this.setState(currentState => {
      return { on: !currentState.on };
    });
  };
  render() {
    return <Switch on={this.state.on} onClick={this.handleToggle} />;
  }
}
```

### Exposing values to outside the component

When a self managing component has it's state, you want to have some kind of hook or a way to let know other components. You call a `this.props.handler(value)`

```js
// example
class Toggle extends React.Component {
  state = { on: false };
  handleToggle = () => {
    this.setState(
      currentState => {
        return { on: !currentState.on };
      },
      () => {
        // expose outside
        this.props.onToggle(this.state.on);
      }
    );
  };
  render() {
    return <Switch on={this.state.on} onClick={this.handleToggle} />;
  }
}
```

## Compound Components

Compound components provides an easy way to share state between Parent and children. It makes it simpler for those who are using your component.

You make a compound component by:

1. Creating static functions inside the class
2. Pass the properties (state, functions) on the static functions as props.
3. The render method, maps over the clone of the static functions, and passing the props they need.

```js
// Compound Components

import React from 'react';
import { Switch } from '../switch';

class Toggle extends React.Component {
  state = { on: false };

  static Button = ({ on, toggle, ...props }) => (
    <Switch on={on} onClick={toggle} {...props} />
  );

  static On = ({ on, children }) => (on ? children : null);

  static Off = ({ on, children }) => (on ? null : children);

  toggle = () =>
    this.setState(
      ({ on }) => ({ on: !on }),
      () => this.props.onToggle(this.state.on)
    );

  render() {
    const { on } = this.state;
    const { toggle } = this;
    return React.Children.map(this.props.children, child =>
      React.cloneElement(child, {
        on,
        toggle
      })
    );
  }
}

function Usage({ onToggle = (...args) => console.log('onToggle', ...args) }) {
  return (
    <Toggle onToggle={onToggle}>
      <Toggle.On>The button is on</Toggle.On>
      <Toggle.Off>The button is off</Toggle.Off>
      <Toggle.Button />
    </Toggle>
  );
}
```

### Passing a non react element

It would throw a warning because you are passing a non-attribute to an html element.

#### Workaround

In mapping, you can make a check if the one rendered is a static function. You can just return the html element.

### Why not `array.map`?

React children has renders differently if the it has only one child. That's why they made a util `React.Children.map`
