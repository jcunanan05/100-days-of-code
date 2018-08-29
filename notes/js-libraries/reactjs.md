## React Notes

### React JS official Docs
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

#### Ways of using this on functions

1. Make constructor on class components

2. [Public class fields syntax](https://babeljs.io/docs/plugins/transform-class-properties/)

Ways of setting state
1. Passing an object
2. Passing a function [(handling async calls)](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-may-be-asynchronous)

[Unidirectional data flow](https://reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down)

[Controlled Components](https://reactjs.org/docs/forms.html#controlled-components)

#### Ways of Composition in react
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

#### Thinking in react
1. [Break ui into a component hierarchy](https://reactjs.org/docs/thinking-in-react.html#step-1-break-the-ui-into-a-component-hierarchy) - start drawing boxes
2. [Build a static version of it](https://reactjs.org/docs/thinking-in-react.html#step-2-build-a-static-version-in-react)
  * some tips recommended in the docs:
  > In simpler examples, it’s usually easier to go top-down, and on larger projects, it’s easier to go bottom-up and write tests as you build.
3. [Identify which can be made state](https://reactjs.org/docs/thinking-in-react.html#step-3-identify-the-minimal-but-complete-representation-of-ui-state) - in the link there are 3 simple questions gave in the docs, but in a nutshell, identify the parts that is reactive (always changes) ex. _input fields_
4. [Identify Where Your State Should Live](https://reactjs.org/docs/thinking-in-react.html#step-4-identify-where-your-state-should-live)
5. [Add inverse data-flow](https://reactjs.org/docs/thinking-in-react.html#step-5-add-inverse-data-flow)

### Stephen Grider's Modern react / redux

#### Throttling User Input
- There's a library called `Lodash` that can help throttling (_slowing down_) function exection.
  - It's called `debounce`
  - Stephen grider used it to slow down searching when the user types

- Callback strategy is a simple way to pass functions parent to children