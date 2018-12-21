![pageObject](https://www.logigear.com/blog/wp-content/uploads/3-1.png)
## Page Object

___Page Object is a Design Pattern which has become popular in test automation for enhancing test maintenance and reducing code duplication.___

Page Objects help you write cleaner tests by encapsulating information about the elements on your application page. A Page Object can be reused across multiple tests, and if the template of your application changes, you only need to update the Page Object.

The benefits of using Page Objects:
- saves maintenance time: updating the page object updates all tests that use it
- organizes your code and keeps it DRY
- declutters your spec files by moving logic to the page object
- use a cool buzzword that is actually useful!

### Without Page Objects
```js
describe('angularjs homepage', function() {
  it('should greet the named user', function() {
    browser.get('http://www.angularjs.org');
    element(by.model('yourName')).sendKeys('Julie');
    var greeting = element(by.binding('yourName'));
    expect(greeting.getText()).toEqual('Hello Julie!');
  });
});
```

### With Page Objects
```js
// page object file
var AngularHomepage = function() {
  var nameInput = element(by.model('yourName'));
  var greeting = element(by.binding('yourName'));

  this.get = function() {
    browser.get('http://www.angularjs.org');
  };
  this.setName = function(name) {
    nameInput.sendKeys(name);
  };
  this.getGreetingText = function() {
    return greeting.getText();
  };
};
module.exports = new AngularHomepage();

// spec file
var angularHomepage = require('./AngularHomepage');

describe('angularjs homepage', function() {
  it('should greet the named user', function() {
    angularHomepage.get();
    angularHomepage.setName('Julie');
    expect(angularHomepage.getGreetingText()).toEqual('Hello Julie!');
  });
});
```

#### Further Reading
- [Using Page Objects to Organize Tests](https://github.com/angular/protractor/blob/master/docs/page-objects.md) - Page Objects help you write cleaner tests by encapsulating information about the elements on your application page.
- [Protractor and Page Objects](https://moduscreate.com/blog/protractor-and-page-objects/) - A page object is a class that simply stores your page elements.

#### [Return: Express README](../../README.md)
