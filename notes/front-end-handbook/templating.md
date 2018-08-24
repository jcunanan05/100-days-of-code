## Templating

Notes and advice from the handbook:
> Note that JavaScript 2015 (aka ES6) has a native templating mechanism called "Templates strings". Additionally, templating as of late has been replaced by things like JSX, a template element, or HTML strings.

> If I was not using React & JSX I'd first reach for JavaScript "Templates strings" and when that was lacking move to nunjucks.

* It means for casual templating, you can use the _ES6 template strings_
  ```javascript
  const heading = (title) => (
    `<h1>${title}</h1>`
  );
  console.log(heading('Hello World!');
  ```

### EJS, Jade (pug), Nunjucks Comparison

res: [https://npmcompare.com/compare/ejs,jade,nunjucks]()

### ES6 Template Literals, handleBars killer??
res: [https://www.keithcirkel.co.uk/es6-template-literals/]()

* No. Your code can blow up if you let template literals handle it all.
* Good way of using template literals is to split your templates. Called _micro-templating_
  * Like react