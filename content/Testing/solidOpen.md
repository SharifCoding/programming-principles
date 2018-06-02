### Open-Closed Principle

#### Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.
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

#### [Return: SOLID Principles](./solidPrinciples.md)

#### [Return: Express README](../../README.md)