![mockJest](mockJest.png)

___A higher order function takes a function and returns a function. Jest offers a way to make sure the function you gave is being used right.___

Mock functions are also known as "spies", because they let you spy on the behavior of a function that is called indirectly by some other code, rather than just testing the output.

In Jest, doubles are generally always referred to as mocks
- Doubles are primarily created with `jest.fn()`
- Can be invoked like a function
- Keeps track of function calls
- Keeps track of instances when used as a constructor
- Can provide custom return values
- Can provide custom implementations

Example from [Cruise Ships](https://github.com/SharifCoding/cruise-ships) assignment;
Before applying mocks to `port.test.js`:
```js
  it('track removal of ship in port', () => {
    const port = new Port('LV-426');
    const Nostromo = {};
    const Sulaco = {};
    port.addShip(Nostromo);
    port.addShip(Sulaco);
    port.removeShip(Nostromo);
    expect(port.ships).toEqual([Sulaco]);
  });
```
Mocks `jest.fn()` applied to the test unit:
```js
  it('track removal of ship in port', () => {
    const port = new Port('LV-426');
    const Nostromo = jest.fn();
    const Sulaco = jest.fn();
    port.addShip(Nostromo);
    port.addShip(Sulaco);
    port.removeShip(Nostromo);
    expect(port.ships).toEqual([Sulaco]);
  });
  ```
[jest.fn() All the Things](https://medium.com/@deanslamajr/jest-fn-all-the-things-d26f3b929986)

[Mock Functions](https://facebook.github.io/jest/docs/en/mock-functions.html)

[Image Source](http://www.assertselenium.com/angularjs/protractor-jasmine-pre-post-processing-methods/)
