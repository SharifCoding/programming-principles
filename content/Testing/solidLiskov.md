### Liskov Substitution Principle

#### Child classes should never break the parent class' type definitions.
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

#### [Return: SOLID Principles](./solidPrinciples.md)

#### [Return: Express README](../../README.md)