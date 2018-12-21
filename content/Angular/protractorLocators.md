![protractor](https://3lhowb48prep40031529g5yj-wpengine.netdna-ssl.com/wp-content/uploads/2017/01/protractor_elementor-02-.gif)
## Protractor - Locators and ElementFinders

___The heart of end-to-end tests for webpages is finding DOM elements, interacting with them, and getting information about the current state of your application.___

Protractor exports a global function element, which takes a Locator and will return an ElementFinder. This function finds a single element - if you need to manipulate multiple elements, use the `element.all` function.

The ElementFinder has a set of action methods, such as `click()`, `getText()`, and `sendKeys`. These are the core way to interact with an element and get information back from it.

### Locators
A locator tells Protractor how to find a certain DOM element. Protractor exports locator factories on the global by object. The most common locators are:
```js
// Find an element using a css selector.
by.css('.myclass')

// Find an element with the given id.
by.id('myid')

// Find an element using an input name selector.
by.name('field_name')

// Find an element with a certain ng-model.
// Note that at the moment, this is only supported for AngularJS apps.
by.model('name')

// Find an element bound to the given variable.
// Note that at the moment, this is only supported for AngularJS apps.
by.binding('bindingname')

// The locators are passed to the element function.
element(by.css('some-css'));
element(by.model('item.name'));
element(by.binding('item.name'));

// When using CSS Selectors as a locator, you can use the shortcut $() notation.
$('my-css');
// Is the same as:
element(by.css('my-css'));
```

### Actions
The `element()` function returns an ElementFinder object. The ElementFinder knows how to locate the DOM element using the locator you passed in as a parameter, but it has not actually done so yet. It will not contact the browser until an action method has been called. The most common action methods are:
```js
var el = element(locator);

// Click on the element.
el.click();

// Send keys to the element (usually an input).
el.sendKeys('my text');

// Clear the text in an element (usually an input).
el.clear();

// Get the value of an attribute, for example, get the value of an input.
el.getAttribute('value');

// Since all actions are asynchronous, all action methods return a promise. So, to log the text of an element:
var el = element(locator);
el.getText().then(function(text) {
  console.log(text);
});
```

### Finding Multiple Elements
To deal with multiple DOM elements, use the `element.all` function. This also takes a locator as its only parameter.
```js
element.all(by.css('.selector')).then(function(elements) {
  // elements is an array of ElementFinders.
});

// element.all() has several helper functions.

// Number of elements.
element.all(locator).count();

// Get by index (starting at 0).
element.all(locator).get(index);

// First and last.
element.all(locator).first();
element.all(locator).last();

// When using CSS Selectors as a locator, you can use the shortcut $$() notation.
$$('.selector');
// Is the same as:
element.all(by.css('.selector'));
```

### Finding Sub-Elements
To find sub-elements, simply chain `element` and `element.all` functions together as shown below.
```js
// Using a single locator to find:
// an element
element(by.css('some-css'));

// a list of elements:
element.all(by.css('some-css'));

// Using chained locators to find:
// a sub-element:
element(by.css('some-css')).element(by.tagName('tag-within-css'));

// to find a list of sub-elements:
element(by.css('some-css')).all(by.tagName('tag-within-css'));

// You can chain with get/first/last as well like so:
element.all(by.css('some-css')).first().element(by.tagName('tag-within-css'));
element.all(by.css('some-css')).get(index).element(by.tagName('tag-within-css'));
element.all(by.css('some-css')).last().all(by.tagName('tag-within-css'));
```

#### Further Reading
- [Protractor and Elementor](https://moduscreate.com/blog/protractor-and-elementor/) - Elementor lets you search for and manipulate elements within a browser.

#### [Return: Express README](../../README.md)
