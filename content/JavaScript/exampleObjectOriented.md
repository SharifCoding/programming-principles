![mockJest](https://koenig-media.raywenderlich.com/uploads/2017/05/ObjectOrientedProgramming-graph-2.png)

## Example of Object-oriented Programming

___Stop thinking in terms of individual variables and functions. Begin thinking in terms of cohesive, self-sufficient objects___

One of the principal advantages of object-oriented programming techniques over procedural programming techniques is that they enable programmers to create modules that do not need to be changed when a new type of object is added. A programmer can simply create a new object that inherits many of its features from existing objects. This makes object-oriented programs easier to modify. [Conti..](https://www.webopedia.com/TERM/O/object_oriented_programming_OOP.html)

---

```js
// Step 1
console.log('Hello, my name is John Smith and my favourite colour is blue');
```

```js
// Step 2
function person() {
  cosole.log('Hello, my name is ' + blank + ' and my favourite colour is ' + blank + '.');
}

person('John Smith', 'blue');
```

```js
// Step 3
function person(name, favColour) {
  cosole.log('Hello, my name is ' + name + ' and my favourite colour is ' + favColour + '.');
}

person('John Smith', 'blue');
```

```js
// Step 4
function person(name, favColour) {
  cosole.log('Hello, my name is ' + name + ' and my favourite colour is ' + favColour + '.');
}

var johnName = 'John';
var johnFavColour = 'blue'

person(johnName, johnFavColour);
```

```js
// Step 5
function person(name, favColour) {
  cosole.log('Hello, my name is ' + name + ' and my favourite colour is ' + favColour + '.');
}

var john = {
  name: 'John Smith',
  favColour: 'blue'
}

person(john.name, john.favColour);
```

```js
// Step 6
var john = {
  name: 'John Smith',
  favColour: 'blue',
  greet: function() {
    console.log('Hello, my name is ' + john.name + ' and my favourite colour is ' + john.favColour + '.')
  }
}

john.greet();
```

```js
// Step 7
function Person(fullName, favColour) {
  this.name = fullName;
  this.favColour = favColour
  this.greet = function() {
    console.log('Hello, my name is ' + this.name + ' and my favourite colour is ' + this.favColour + '.')
  }
}

var john = new Person('John Smith', 'blue');
john.greet();
```

```js
// Step 8
function Person(fullName, favColour) {
  this.name = fullName;
  this.favColour = favColour
  this.greet = function() {
    console.log('Hello, my name is ' + this.name + ' and my favourite colour is ' + this.favColour + '.')
  }
}
  
var john = new Person('John Smith', 'blue');
john.greet();
```

```js
// Step 9
function Person(fullName, favColour) {
  this.name = fullName;
  this.favColour = favColour;
}

Person.prototype.greet = function greet() {
  console.log('Hello, my name is ' + this.name + ' and my favourite colour is ' + this.favColour + '.')
};
```

[What is Object-oriented Programming?](https://www.youtube.com/watch?v=rlLuL3jYLvA)

[Object-oriented JavaScript for beginners](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)

[Image Source](https://www.raywenderlich.com/160728/object-oriented-programming-swift)

#### [Return: Express README](../../README.md)
