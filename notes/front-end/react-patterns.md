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

# Intermediate React v4

FE masters course about what can we do for react. Course by brian holt. Lecture found here https://btholt.github.io/complete-intro-to-react-v4/

Github: https://github.com/btholt/complete-intro-to-react-v4

## CSS-in-JS

Brian prefers react-emotion over styled components. React emotion now is `@emotion/core` and `@emotion/styled`

### Brian's opinions about CSS-in-JS

- He doesn't reach it out of the box first. Writing normal css with classes is good enough. 

- CSS Modules is his goto. It has no overhead performance costs. It compiles to a css stylesheet.

- CSS-in-JS is a good breakthrough for real-time styles

## Code-splitting with React Loadable

There are components that we need to load later. For that case there's a package called react-loadable that lazy-loads components.

```js
import Loadable from 'react-loadable'
const LoadableComponent = Loadable({
  loader: () => import('./Component'),
  loading: () => <h1>Loading...</h1>
})
```

### Tips / Advice in lazy-loading components

Delaying load of components is not always a silver bullet solution for your app. When you do lazy-loading, it must be worth it. It must be a component that really slows down your app on initial loading. Or else you'll just make the user wait.

Advantages

* Get the bare minimum of your app. Trims kilobytes of your initial page load.

Disadvantages

* Indirection and delays.

### Lazy-loading in the background

Ways to load components in the background:

* Use service workers. You need to setup.
* Or use prefetch. But prefetch is a hit or miss. It depends on the browser, battery life, device's condition, etc...
