![protractor](https://flexmanu.files.wordpress.com/2018/02/angular_protector.png)
## Automation testing with Protractor

___Protractor is an end-to-end test framework for Angular and AngularJS applications. Protractor runs tests against your application running in a real browser, interacting with it as a user would.___

Protractor is a NodeJS program which is written in JavaScript and runs with Node to identify the web elements in AngularJS applications, and it also uses WebDriver to control the browser with user actions.

Angular JS applications have some extra HTML attributes like `ng-repeater`, `ng-controller`, `ng-model`.., etc. which are not included in Selenium locators. Selenium is not able to identify those web elements using Selenium code. So, Protractor on the top of Selenium can handle and controls those attributes in Web Applications.

### How Does Protractor Work?
![how does protractor work](https://cdn-images-1.medium.com/max/1600/1*N9N_rANWAiEtw_vzDblw9w.jpeg)
- Jasmine helps to create the test.
- Protractor helps to run the test.
- Selenium Server helps to manage browsers.
- Selenium WebDriver helps to invoke browsers APIs.

### Setting up Protractor
Use npm to install Protractor globally with:
```bash
npm install -g protractor
```
This will install two command line tools, `protractor` and `webdriver-manager`. Try running `protractor --version` to make sure it's working.

The `webdriver-manager` is a helper tool to easily get an instance of a Selenium Server running. Use it to download the necessary binaries with:
```bash
webdriver-manager update
```
Now start up a server with:
```bash
webdriver-manager start
```
This will start up a Selenium Server and will output a bunch of info logs. Your Protractor test will send requests to this server to control a local browser. You can see information about the status of the server at [http://localhost:4444/wd/hub](http://localhost:4444/wd/hub).

#### Further Reading
- [protractortest.org](https://www.protractortest.org) - Protractor is an end-to-end test framework for Angular and AngularJS applications.
- [End to End Testing For Angular](https://medium.com/@vinaypatilloyola/end-to-end-testing-for-angular-2-applications-protractor-90af5c4b1b21) - Protractor in action, writing a test.

#### [Return: Express README](../../README.md)
