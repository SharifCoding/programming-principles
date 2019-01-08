![cucumber](https://static1.squarespace.com/static/5b64cabf5b409bbf05dbd8b3/t/5b6571f11ae6cf3410e9e52b/1545143899410/?format=1500w)
## Cucumber

___Cucumber is a tool that supports Behavior Driven Development (BDD). It offers a way to write tests that anybody can understand, regardless of their technical knowledge.___

Cucumber is a testing framework which supports Behavior Driven Development (BDD). It lets us define application behavior in plain meaningful English text using a simple grammar defined by a language called Gherkin. Cucumber itself is written in Ruby, but it can be used to “test” code written in Ruby or other languages.

Feature files are the essential part of cucumber which is used to write test automation steps or acceptance tests:
```java
// sample.feature
Feature: Update password
 
Scenario: Admin user can update the user password
 
Given I am in the HR system with an Admin account
When I update password of another user
Then I receive a message for updating password successfully
And user password is updated to the new password
```

### Gherkin language
A `scenario` represents a particular functionality which is under test. By seeing the scenario user should be able to understand the intent behind the scenario and what the test is all about. Each scenario should follow `given`, `when` and `then` format. This language is called as “gherkin”.

- <b>Given:</b> As mentioned above, given specifies the pre-conditions. It is basically a known state.
- <b>When:</b> This is used when some action is to be performed. As in above example, we have seen when the user tries to log in using username and password, it becomes an action.
- <b>Then:</b> The expected outcome or result should be placed here. For Instance: verify the login is successful, successful page navigation.
- <b>Background:</b> Whenever any step is required to perform in each scenario then those steps need to be placed in Background. For Instance: If a user needs to clear database before each scenario then those steps can be put in a background.
- <b>And:</b> And is used to combine two or more same type of action.

#### Further Reading
- [cucumber.io](https://cucumber.io/) - Cucumber is a tool that supports Behaviour-Driven Development.
- [Behaviour-Driven Development](https://docs.cucumber.io/bdd/) - BDD aims to narrow the communication gaps between team members.

#### [Return: Express README](../../README.md)
