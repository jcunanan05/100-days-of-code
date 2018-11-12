# Testing React Apps, v2

by Kent Dodds

This is my notes for testing react apps.
src: frontend masters course

### Jest config

Kent mentioned that jest is cool because you don't need to include a lot of packages to make your unit tests working.

Tips:

- Kent said take advantage of _tree shaking_ in webpack & babel, for smaller bundles. _video 5, 6:44_

  - by making `{modules: false}` babel won't transpile `import` code and webpack will take care of it.
  - it will make jest tests fail though so you need condition to set it on `{modules: 'commonjs'}` when it is on test mode.

- By default, jest enables JSDOM, it is a DOM environment. So if you need fast load time, and you don't need the DOM, you just disable it.

```javascript
// e.g. package.json file
{
  "jest": {
    "testEnvironment": "node"
  }
}
```

### Solving some css modules problem

- You need to put some moduleMapper in the config. _video 7 3:27_

## Codecov in jest

You can set a percent threshold of code coverage in jest. For new testers, you can set just 13 percent.

You can have 2 different test configs e.g. _client and backend_ and jest will run that code coverage in parallel

## Testing Framework

1. Arrange - prepare the environment, dependencies you need, to mock the code you're testing.
2. Act - Fill in or use the code you're testing.
3. Assert - Check whether the code does what you expect it to do.

## Jest watch mode / filter

- Watch only the changed files since last commit.
- You can also filter by filename, or by test name.

## Testing client-side basics

No library / abstractions were used, just by jest and manipulating DOM nodes.

### Mocking form submits

- Arrange - prepare your container, use ReactDOM to render it, mock a submit function using `jest.fn()` get the input fields and fill DOM nodes with values.

- Act - create a submit event, and dispatch the form.

- Assert - Check if submit has been called, and has been called with correct values.

Sample Code:

```js
// login.step-1.js
import React from 'react';
import ReactDOM from 'react-dom';
import Login from '../login';

test('calls onSubmit with the username and password when submitted', () => {
  // Arrange
  const fakeUser = { username: 'chucknorris', password: '(╯°□°）╯︵ ┻━┻' };
  const handleSubmit = jest.fn();
  const div = document.createElement('div');
  ReactDOM.render(<Login onSubmit={handleSubmit} />, div);

  const inputs = div.querySelectorAll('input');
  const usernameNode = inputs[0];
  const passwordNode = inputs[1];
  const formNode = div.querySelector('form');
  const submitButtonNode = div.querySelector('button');

  usernameNode.value = fakeUser.username;
  passwordNode.value = fakeUser.password;

  // Act
  const event = new window.Event('submit');
  formNode.dispatchEvent(event);

  // Assert
  expect(handleSubmit).toHaveBeenCalledTimes(1);
  expect(handleSubmit).toHaveBeenCalledWith(fakeUser);
  expect(submitButtonNode.type).toBe('submit');
});
```

## Kent thoughts on shallow rendering / enzyme

- He believes in shipping confidence. So he's against some utilites in enzyme, like shallow rendering. He cares about whether it delivers correctly to the user, not if it's pure or not.

- He says there are some utils that allows him to use or test in a way it's not being used. That's why he wrote his own `react-testing-library`

### Q/A to kent

Testing React-redux containers? Render with a provider.

## Test tips by kent

### Putting `data-testid` on html elements

Makes it easier to select the element, and intention is clear that it is only for testing.

If other people don't like it on production code, you can run a babel-plugin-remove-properties to remove it on production.
