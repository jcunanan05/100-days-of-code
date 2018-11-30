# React Notes

## React JS official Docs
* **functional components** 
  ```javascript
    //es5
    function Welcome(props) {
      return <h1> Hi, {props.name}</h1>
    }
  ```

  ```javascript
    //es6
    const Welcome = props => (
      <h1>Hi, {props.name}</h1>
    );
  ```

  and to render it..
  ```javascript
    ReactDOM.render(
      <Welcome name="Bro" />, 
      document.getElementById('root'));
  ```
* **Class component**
  ```javascript
    import React from 'react';

    class Clock extends React.Component {
      render() {
        return (
          <h1> Hi, {this.props.name}</h1>
        );
      }
    }
  ```
  and then import it from the entrypoint 
  ```javascript
    import React from 'react';
    import ReactDOM from 'react-dom';
    import Welcome from './components/Welcome';

    ReactDOM.render(
      <Welcome name="Bro" />, 
      document.getElementById('root'));
  ```

* **Props** are immutable in the component (_can't be changed_)
* In composing components, naming convention is _TitleCase_.

- [Element variables](https://reactjs.org/docs/conditional-rendering.html#element-variables)

Stateful components


- [Binding issues](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_objects/Function/bind)

### Ways of using this on functions

1. Make constructor on class components

2. [Public class fields syntax](https://babeljs.io/docs/plugins/transform-class-properties/)

Ways of setting state
1. Passing an object
2. Passing a function [(handling async calls)](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-may-be-asynchronous)

[Unidirectional data flow](https://reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down)

[Controlled Components](https://reactjs.org/docs/forms.html#controlled-components)

### Ways of Composition in react
1. **Passing a component as props** - since jsx are objects too
```javascript
function App() {
  return (
    <SplitPane
      left={
        <Contacts />
      }
      right={
        <Chat />
      } />
  );
}
```
2. **Passing components as children** - using ```props.children``` like slots on (_Vue_)
```javascript
//parent component
function Dialog(props) {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">
        {props.title}
      </h1>
      <p className="Dialog-message">
        {props.message}
      </p>
      {props.children}
    </FancyBorder>
  );
}

//special case component
class SignUpDialog extends React.Component {
  constructor(props) {
    //...
  }

  render() {
    return (
      <Dialog title="Mars Exploration Program"
              message="How should we refer to you?">
        <input value={this.state.login}
               onChange={this.handleChange} />

        <button onClick={this.handleSignUp}>
          Sign Me Up!
        </button>
      </Dialog>
    );
  }

  handleChange(e) {
    //...
  }

  handleSignUp() {
    //...
  }
}
```

### Thinking in react
1. [Break ui into a component hierarchy](https://reactjs.org/docs/thinking-in-react.html#step-1-break-the-ui-into-a-component-hierarchy) - start drawing boxes
2. [Build a static version of it](https://reactjs.org/docs/thinking-in-react.html#step-2-build-a-static-version-in-react)
  * some tips recommended in the docs:
  > In simpler examples, it’s usually easier to go top-down, and on larger projects, it’s easier to go bottom-up and write tests as you build.
3. [Identify which can be made state](https://reactjs.org/docs/thinking-in-react.html#step-3-identify-the-minimal-but-complete-representation-of-ui-state) - in the link there are 3 simple questions gave in the docs, but in a nutshell, identify the parts that is reactive (always changes) ex. _input fields_
4. [Identify Where Your State Should Live](https://reactjs.org/docs/thinking-in-react.html#step-4-identify-where-your-state-should-live)
5. [Add inverse data-flow](https://reactjs.org/docs/thinking-in-react.html#step-5-add-inverse-data-flow)

### Error Boundaries

res: [https://reactjs.org/docs/error-boundaries.html](https://reactjs.org/docs/error-boundaries.html)

Error boundaries are like catch statements, that won't let the whole app break. But they won't catch these:

- Event handlers
- Async
- SSR
- Error in the error boundary. (only its children)

### Forwarding Refs
res: [https://reactjs.org/docs/forwarding-refs.html](https://reactjs.org/docs/forwarding-refs.html)

This is when you want to access the DOM node inside an encapsulated in a component. e.g. when modifying css, playing audio, etc...

#### Tips in forwarding refs

- Don't conditonally use it, you code will be fragile

```js
// sample code
const FancyButton = React.forwardRef((props, ref) => (
  <button ref={ref} className="FancyButton">
    {props.children}
  </button>
));
```

### Fragments / no extra divs for multiple components

example
```js
class Columns extends React.Component {
  render() {
    return (
      <React.Fragment>
        <td>Hello</td>
        <td>World</td>
      </React.Fragment>
    );
  }
}
```

#### Using fragments in loops

Fragments can accept a `key` prop too

```js
function Glossary(props) {
  return (
    <dl>
      {props.items.map(item => (
        // Without the `key`, React will fire a key warning
        <React.Fragment key={item.id}>
          <dt>{item.term}</dt>
          <dd>{item.description}</dd>
        </React.Fragment>
      ))}
    </dl>
  );
}
```

### Higher-order Components (HOCs)

These are patterns that enhances a component. Container patterns are HOC's too.

```js
// React Redux's `connect`
const ConnectedComment = connect(commentSelector, commentActions)(CommentList);
//vvvvvvv same vvvvvvvvv
// connect is a function that returns another function
const enhance = connect(commentListSelector, commentListActions);
// The returned function is a HOC, which returns a component that is connected
// to the Redux store
const ConnectedComment = enhance(CommentList);
```

#### Tips in HOCs

- Don't mutate the Component. Instead, create a new component and wrap it. [examples here](https://reactjs.org/docs/higher-order-components.html#dont-mutate-the-original-component-use-composition)

- Filter unrelated props. [examples here](https://reactjs.org/docs/higher-order-components.html#convention-pass-unrelated-props-through-to-the-wrapped-component)

- Don't use HOC's inside the render method. It will re render the component [examples here](https://reactjs.org/docs/higher-order-components.html#dont-use-hocs-inside-the-render-method)

- Wrap HOC with display name [examples here](https://reactjs.org/docs/higher-order-components.html#convention-wrap-the-display-name-for-easy-debugging)

### React with 3rd party libraries

You can use selective rendering with ReactDOM.render


## freeCodeCamp notes

* **Why use `ReactDOMServer.renderToString()` ?**
  * For crawlers, that they can see a HTML markup