![Selenium](https://i2.wp.com/learn-automation.com/wp-content/uploads/2015/08/Cross-browser-testing-in-Selenium-Webdriver.png?fit=525%2C333)
## Automation with Selenium

___Selenium is a portable framework used to validate web applications across different browsers and platforms. You can use multiple programming languages like Java, C#, Python etc to create Selenium Test Scripts.___

Java become the most favoured language for automation testing due to strong community support and excellent documentation to fix problems with automation scripting, additionally Java supports Selenium.

The following components are required to start automation:
- Java (JDK)
- Eclipse Selenium Client
- WebDriver Language bindings
- Configuring Selenium Webdriver with Eclipse
- Creating and Running the first test

```java
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class FirstTestInSelenium {
    public static void main(String[] args) {
        System.setProperty(“webdriver.chrome.driver”, “.\\Driver\\chromedriver.exe”);
        WebDriver driver=new ChromeDriver();
        driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
        driver.manage().window().maximize();
        driver.get(“https://www.google.com");
        driver.close();
    }
}
```

[The Selenium Browser Automation Project](https://www.selenium.dev/documentation/en/)

#### [Return: Express README](../../README.md)
