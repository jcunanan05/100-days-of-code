# Testing

## Frontend Masters Testing React Apps

* Kent mentioned he won't teach enzyme. He decided to not do it, he encountered some problems with it.

### Diff Forms of testing
* Static Code Analysis - you don't have to write these tests

  * Some tools in Static code analysis:
    * ESLint - _advice:_ don't use ESLint for style rules because there's prettier that automatically format the code for you. 
    * Flow-typed or Typescript for typechecking

* Unit tests - small tests
  * from purist standpoint: it will mockout all the dependencies
  * kent is pretty fluid with unit vs integration, he care less

* Integration Tests - Mocking the whole app, the router, takes a little bit more work
  * You have to mock API calls

* End-to-End (E2E) Tests - Kinda different, it is like a when a user clicks and verify what is happening

#### What really is javascript testing? 
* Its goal is not just to point out the error, it aims to make the error clear where it comes from
* To try and use code / components, the same way it will be used be used in apps

### Basic react testing with jest
* The shape of a test:
```javascript
test('title', () => {
  // arrange

  // act

  // assert
});
```
* > Tip: When testing UI, make sure to write not-so strict tests, that any change of HTML element, the test will break.

* > Tip: Make sure to test only what you need to make sure you're confident
  * If you are really concerned with the elements' order, you can do snapshot testing