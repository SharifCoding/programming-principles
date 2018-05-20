### Single Responsibility Principle

#### A class should have one, and only one, reason to change.
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

#### [Return: Express README](./solidPrinciples.md)
