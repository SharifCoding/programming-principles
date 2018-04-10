![setupTeardown](../img/setupTeardown.png)

## Setup and Teardown

___Prepare initial state before tests run and perform cleanup after tests complete.___

If you want to do something before the first or after the test unit has been run, you can use methos Setup (`beforeEach`), and Teardown (`afterEach`). When a beforeEach() method is defined, the test runner will run that method prior to each test. Likewise, if a afterEach() method is defined, the test runner will invoke that method after each test.
```js
beforeEach(context =>
{
    // Executed BEFORE the first test unit.
});

afterEach(context =>
{
    // Executed AFTER the last test unit.
});
```
There are two main areas that we set beforeEach and afterEach: 
- Repeating Setup For Many Tests; for repeatedly doing many tests, use `beforeEach` and `afterEach`.
- One-Time Setup; for one setup, at the beginning of a file, Jest provides `beforeAll` and `afterAll`.

`beforeEach` and `beforeAll`;
Test that requires items to exist, or certain state - so you put these actions (creating object instances, initializing db, preparing rules, etc...) into the _setUp_.

`afterEach` and `afterAll`;
Each test should stop in the place where it was started, restore to it's initial state (close files, connections, removing newly created items, calling transactions callback, etc...), all these steps are to be included into the _tearDown_.

The test itself should contain only actions that to be performed on the test object to get the result, while setUp and tearDown are the methods to help you to leave your test code clean and flexible.

Example from [Cruise Ships](https://github.com/SharifCoding/cruise-ships) assignment;
Before applying `beforeEach` method:
```js
describe('Ship', () => {
  it('can be instantiated', () => {
    const port = new Port('Dover');
    const itinerary = new Itinerary([port]);
    const ship = new Ship(itinerary);

    expect(ship).toBeInstanceOf(Object);
  });
  it('has a current port', () => {
    const port = new Port('Dover');
    const itinerary = new Itinerary([port]);
    const ship = new Ship(itinerary);

    expect(ship.currentPort).toBe(port);
  });
  it('gets added to port on instantiation', () => {
    const port = new Port('Dover');
    const itinerary = new Itinerary([port]);
    const ship = new Ship(itinerary);

    expect(port.ships).toContain(ship);
  });
});
```
After applying `beforeEach` method:
```js
describe('Ship', () => {
  beforeEach(() => {
    const port = new Port('Dover');
    const itinerary = new Itinerary([port]);
    const ship = new Ship(itinerary);
  })
  it('can be instantiated', () => {
  expect(ship).toBeInstanceOf(Object);
  });
  it('has a current port', () => {
  expect(ship.currentPort).toBe(port);
  });
  it('gets added to port on instantiation', () => {
  expect(port.ships).toContain(ship);
});
```
[Setup and Teardown](https://facebook.github.io/jest/docs/en/setup-teardown.html)

[Image Source](http://www.assertselenium.com/angularjs/protractor-jasmine-pre-post-processing-methods/)

### [Return: Express README](../README.md)
