![spiesJest](../img/spiesJest.jpeg)

## Spies Function 

___A spy can tell us how many times a function was called, what arguments each call had, what values were returned, what errors were thrown, etc.___

Spies allow you to monitor a function; they expose options to track invocation counts, arguments and return values. This enables you to write tests to verify function behaviour. If you spy on a function, the function's behavior is not affected. A spy is a good choice to verify something happened in a test.

The most common scenarios with spies involve:
- checking how many times a function was called
- checking what arguments were passed to a function

In Jest, a mock function becomes a spy when we use a `toHaveBeenCalled` or `toHaveBeenCalledWith` matcher.
- `.toHaveBeenCalled()` - expect a mock function to have been called as part of the test.
- `.toHaveBeenCalled(arg1, arg2)` - expect a mock function to have been called with one or more arguments as part of the test.

<details>
<summary>Expand - Vending Machine Example</summary>
<p>

Main code to be called by the test unit:
```js
function VendingMachine () {
  this.total = 0;
}
VendingMachine.prototype.purchaseSnack = function purchaseSnack (snack) {
  this.total += snack.price;
  snack.addSale()
}
function Snack (name, price) {
  this.name = name
  this.price = price
  this.sales = 0
}
Snack.prototype.addSale = function addSale () {
  this.sales += 1
}
```
Stubs applied to the test unit:
```js
test('snack can be purchased', () => {
  const vendingMachine = new VendingMachine();
  // stub with spy method
  const snack = { name: 'Milkybar', price: 0.60, addSale: jest.fn() };
  vendingMachine.addSnack(snack);
  expect(snack.addSale).toHaveBeenCalled();
})
```
In this example, we don't want to pass a real Snack object into our VendingMachine's `addSnack` method, as this wouldn't be an isolated test, so instead we `stub` snack, ensuring the interface matches that of our Snack prototype/constructor. When our `stub` does get passed into `addSnack`, the `addSale` method gets called, which in this case is our `spy`. The assertion below expect`(snack.addSale).toBeCalled()` therefore passes, as the `addSale` method was called.

</p>
</details>

Example from [Cruise Ships](https://github.com/SharifCoding/cruise-ships) assignment;
Before applying spies to `itinerary.test.js`:
```js
  const dover = new Port('Dover');
  const calais = new Port('Calais');
  const itinerary = new Itinerary([dover, calais]);
  expect(itinerary.ports).toEqual([dover, calais]);
```
Spies applied to the test unit:
```js
  const ports = [jest.fn(), jest.fn()];
  const itinerary = new Itinerary(ports);
  expect(itinerary.ports).toEqual(ports);
```
[Mock Functions](https://facebook.github.io/jest/docs/en/mock-function-api.html)

### [Return: Express README](../README.md)
