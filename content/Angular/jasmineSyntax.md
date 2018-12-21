![jasmine](https://jasmine.github.io/images/jasmine-horizontal.svg)
## Jasmine Syntax

___Jasmine is a behavior-driven development framework for testing JavaScript code.___

```js
describe('Protractor Demo', () => {
  beforeEach(() => {
    // The code here will get executed before each it block is called  
    // browser.get('/');
  });
  it('should display the name of the application',() => {
   /* Expectations accept parameters that will be matched with the real value
   using Jasmine's matcher functions. eg. toEqual(),toContain(), toBe(), toBeTruthy() etc. */
   expect("Angular Application").toEqual("Angular Application");
  });
  it('should click the create Active button',() => {
    // spec goes here
  });
});
```
`describe()`, `beforeEach()` and `it()` are global Jasmine functions.

The `describe` block is used to divide the tests into logical test suites. Each `describe` block (test suite) can have multiple `it` blocks (test specs). The actual tests are defined inside the test specs. 

A `describe` block can have a `beforeEach()` method which will be executed once, before each spec in that block.

`expect` statements, which accept a value, are chained with some matcher functions. Both the real and the expected values are compared, and a boolean is returned which determines whether the test fails or not.

#### Further Reading
- [Jasmine](https://jasmine.github.io/2.4/introduction.html) - Comes out of the box with everything you need to test your code.

#### [Return: Express README](../../README.md)
