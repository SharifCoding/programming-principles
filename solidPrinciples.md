![https://medium.com/@cramirez92/s-o-l-i-d-the-first-5-priciples-of-object-oriented-design-with-javascript-790f6ac9b9fa](img/SOLID.jpeg)

# SOLID Principles
Some important point about SOLID design principles.
- Generally speaking, SOLID state of matter can be brittle. But while talking about code we are not aiming for brittleness of code.
- As far as software designing is concerned, SOLID should be used where code can change shape.
- SOLID can come to rescue when all the requirements are not upfront while developing code.
- SOLID is not a framework
- SOLID is not a library.It is not technology bound. It is not pattern.
- Most of the code written today, though they are written in object oriented way but they are not object oriented and more or less procedural. Writing code in OO language is not a guarantee that the code will be OO.
- But we can make our code OO by using solid principles.We can more productive by using SOLID.
- Code is more maintainable and understandable.When code su er from design smell then SOLID is answer.

SOLID is an acronym for five principles that help software developers design maintainable and extendable classes.
- Single responsibility
- Open-closed
- Liskov substitution
- Interface segregation
- Dependency inversion.

## Single Responsibility Principle

### A class should have one, and only one, reason to change.
- A class should have only single responsibility. A single reason to change.
- Based on separation of concerns.
- Vary each concern independently of other concern.
- Each class should be designed to do one thing and it should do it well.
- The size of the classes become shorter. This makes code easily understandable.

Single Responsibility Principle Violation

<details>
<summary>Bad Example</summary>
<p>

```js
class UserSettings {
  constructor(user) {
    this.user = user;
  }

  changeSettings(settings) {
    if (this.verifyCredentials()) {
    // ...
  }
}

verifyCredentials() {
  // ...
  }
}
```

</p>
</details>

<details>
<summary>Refactored Example</summary>
<p>

```js
class UserAuth {
  constructor(user) {
    this.user = user;
  }

verifyCredentials() {
  // ...
  }
}

class UserSettings {
  constructor(user) {
    this.user = user;
    this.auth = new UserAuth(user);
}

changeSettings(settings) {
  if (this.auth.verifyCredentials()) {
    // ...
    }
  }
}
```

</p>
</details>

----

## Open-Closed Principle

### Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.
- Writing something very speci c to solve some speci c problem can lead to writing same code multiple time which in turn results in code duplication
- Code duplication leads to maintainability problem.
- Reused abstraction principle – if we have multiple abstractions which are not being used by the - concrete class then it is a sign of poor designing and abstractions.
- Interfaces are not designed but they are discovered as the system grows.
- Start with the concrete behaviour and discover the abstraction as commonality emerges.
- Rule of three – Unless and until we have three places where we think that the code is same, it is generally not advised to abstract out the functionality.
- Open for extensibility but closed for modi cation. If we have a class which is being used by other clients, that class should be open for extensibility. The only reason to change the class should be to  x a bug in the class.
- We should favour Composition over inheritance which I will discuss in next principles.
- We can make a class open for extensible is by adding virtual keyword to the methods of the class.

Open Closed Principle Violation

<details>
<summary>Bad Example</summary>
<p>

```js
var iceCreamFlavors=["chocolate","vanilla"];
var iceCreamMaker={
makeIceCream (flavor) {
  if(iceCreamFlavors.indexOf(flavor)>-1){
    console.log("Great success. You now have ice cream.")
  } else {
    console.log("Epic fail. No ice cream for you.")
    }
  }
}
export default iceCreamMaker;
```

</p>
</details>

<details>
<summary>Refactored Example</summary>
<p>

```js
var iceCreamFlavors = ["chocolate","vanilla"];
var iceCreamMaker = {
makeIceCream (flavor) {
  if(iceCreamFlavors.indexOf(flavor)>-1){
    console.log("Great success. You now have ice cream.")
  } else {
    console.log("Epic fail. No ice cream for you.")
  }
}
addFlavor(flavor){
  iceCreamFlavors.push(flavor);
  }
}
export default iceCreamMaker;
```

</p>
</details>

----

## Liskov Substitution Principle

### Child classes should never break the parent class' type definitions.
- It talks about polymorphism.
- Named after barbara liskov, in 70’s
- Derived types must be substituted for base types.
- Client can consume any implementation without changing the correctness of the system
- We can change the behaviour of the system because polymorphism is all about changing the behaviour. 
Correctness of the system can be said as the implementation of the interface A should not crash the ap- plication. Similarly implementation of the interface B should also not crash the application. But any im- plementation of the system is crashing the system that is not the correctness of the system. The imple- mentation is the lowest common denominator when we talk about the correctness of the system. The system can also behave in wrong way if we have a wrong way of the implementation.

Liskov Substitution Principle Violation

<details>
<summary>Bad Example</summary>
<p>

```js
class Rectangle {
  constructor() {
    this.width = 0;
    this.height = 0;
    }

  setColor(color) {
  // ...
  }

  render(area) {
  // ...
  }

  setWidth(width) {
    this.width = width;
  }

  setHeight(height) {
    this.height = height;
  }

  getArea() {
    return this.width * this.height;
  }
}

class Square extends Rectangle {
  setWidth(width) {
    this.width = width;
    this.height = width;
  }

  setHeight(height) {
    this.width = height;
    this.height = height;
  }
}

function renderLargeRectangles(rectangles) {
  rectangles.forEach((rectangle) => {
  rectangle.setWidth(4);
  rectangle.setHeight(5);
  const area = rectangle.getArea(); // BAD: Returns 25 for Square. Should be 20.
  rectangle.render(area);
  });
}

const rectangles = [new Rectangle(), new Rectangle(), new Square()];
renderLargeRectangles(rectangles);
```

</p>
</details>

<details>
<summary>Refactored Example</summary>
<p>

```js
class Shape {
  setColor(color) {
    // ...
  }

  render(area) {
    // ...
  }
}

class Rectangle extends Shape {
  constructor(width, height) {
    super();
    this.width = width;
    this.height = height;
}

getArea() {
    return this.width * this.height;
  }
}

class Square extends Shape {
  constructor(length) {
    super();
    this.length = length;
  }

getArea() {
    return this.length * this.length;
  }
}

function renderLargeShapes(shapes) {
  shapes.forEach((shape) => {
    const area = shape.getArea();
    shape.render(area);
  });
}

const shapes = [new Rectangle(4, 5), new Rectangle(4, 5), new Square(5)];
renderLargeShapes(shapes);
```

</p>
</details>

----

## Interface Segregation Principle

### Make one grained interfaces that are client specific.
- ISP is SOLID design principle which is used to help us achieve the LSP by having more granularity.
- Clients should not depend on methods they do not use. As we have see in the previous code example. - VolumeCalculator should not depend on the GetVolume methods of the classes.
- Interface are introduced to achieve loose coupling and its not the classes that use the interfaces but clients are the one who use interfaces.
- Clients de ne the interface and there is no need for an client to de ne a method in the interface if the client doesn’t need the method in the interface.
- Prefer role based interfaces over header interfaces. Header interfaces are created by abstracting out of the existing classes as we have done in designing previous system.
- If client need to de ne the interface it only need to de ne a very few methods in the interface. These are role interface.
- There are many ways by which we can extend the functionality of the class e.g. by inheritance, by using generics or by using extension methods.
- But there are very less way by which we can reduce the methods in the class. Indeed there is only one way and that is ISP.

Interface Segregation Principle Violation

<details>
<summary>Bad Example</summary>
<p>

```js
class DOMTraverser {
  constructor(settings) {
    this.settings = settings;
    this.setup();
  }

  setup() {
    this.rootNode = this.settings.rootNode;
    this.animationModule.setup();
  }

  traverse() {
    // ...
  }
}

const $ = new DOMTraverser({
  rootNode: document.getElementsByTagName('body'),
    animationModule() {} // Most of the time, we won't need to animate when traversing.
    // ...
});
```

</p>
</details>

<details>
<summary>Refactored Example</summary>
<p>

```js
class DOMTraverser {
  constructor(settings) {
    this.settings = settings;
    this.options = settings.options;
    this.setup();
  }

  setup() {
    this.rootNode = this.settings.rootNode;
    this.setupOptions();
  }

  setupOptions() {
    if (this.options.animationModule) {
    // ...
    }
  }

  traverse() {
    // ...
  }
}

const $ = new DOMTraverser({
  rootNode: document.getElementsByTagName('body'),
  options: {
    animationModule() {}
  }
});
```

</p>
</details>

----

## Dependency Inversion Principle

### Depend on abstractions, not on concretions.
- High-level modules should not depend on low-level modules. Both should depend on abstractions.
- Abstractions should not depend on details. Details should depend on abstractions.
- Implementation of the DIP can also involve Composite pattern and Decorator pattern which I will discuss in later articles.

Dependency Inversion Principle Violation

<details>
<summary>Bad Example</summary>
<p>

```js
class InventoryRequester {
  constructor() {
    this.REQ_METHODS = ['HTTP'];
}

  requestItem(item) {
    // ...
  }
}

class InventoryTracker {
  constructor(items) {
    this.items = items;

    // BAD: We have created a dependency on a specific request implementation.
    // We should just have requestItems depend on a request method: `request`
    this.requester = new InventoryRequester();
  }

  requestItems() {
    this.items.forEach((item) => {
    this.requester.requestItem(item);
    });
  }
}

const inventoryTracker = new InventoryTracker(['apples', 'bananas']);
inventoryTracker.requestItems();
```

</p>
</details>

<details>
<summary>Refactored Example</summary>
<p>

```js
class InventoryTracker {
  constructor(items, requester) {
    this.items = items;
    this.requester = requester;
  }

  requestItems() {
    this.items.forEach((item) => {
    this.requester.requestItem(item);
    });
  }
}

class InventoryRequesterV1 {
  constructor() {
    this.REQ_METHODS = ['HTTP'];
  }

  requestItem(item) {
    // ...
  }
}

class InventoryRequesterV2 {
  constructor() {
    this.REQ_METHODS = ['WS'];
  }

  requestItem(item) {
    // ...
  }
}

// By constructing our dependencies externally and injecting them, we can easily
// substitute our request module for a fancy new one that uses WebSockets.
const inventoryTracker = new InventoryTracker(['apples', 'bananas'], new InventoryRequesterV2());
inventoryTracker.requestItems();
```

</p>
</details>

----

As Uncle Bob says: _“They are not laws. They are not perfect truths”. Nevertheless, they have helped me a lot to create clean code, and I think as a developer you should at least know them so you can decide when to apply them and when not."_
