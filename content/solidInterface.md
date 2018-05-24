### Interface Segregation Principle

#### Make one grained interfaces that are client specific.
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

#### [Return: SOLID Principles](./solidPrinciples.md)
#### [Return: Express README](../README.md)