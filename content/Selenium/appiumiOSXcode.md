![Selenium](https://miro.medium.com/max/1400/1*cDK_xkF4TfIFqAUl_ABv8w.jpeg)
## iOS Mobile Test Automation

___Appium's primary support for automating iOS apps is via the XCUITest driver.___

XCUITest driver leverages Apple's XCUITest libraries under the hood in order to facilitate automation of an app. This access to XCUITest is mediated by the WebDriverAgent server. WebDriverAgent (also referred to as "WDA") is a WebDriver-compatible server that runs in the context of an iOS simulator or device and exposes the XCUITest API.

The following components are required to start iOS automation:
- Appium’s desktop app
- Required Packages for iOS Testing
	- brew install libimobiledevice
	- brew install ios-deploy
- WebDriverAgent setup
	- cd /Applications/Appium.app/Contents/Resources/app/node_modules/appium/node_modules/appium-webdriveragent
	- mkdir -p Resources/WebDriverAgent.bundle
	- ./Scripts/bootstrap.sh
- Java (JDK)
- Install Maven
- Install Eclipse
- Creating and Running the first test

```java
import org.testng.annotations.Test;
import java.net.MalformedURLException;
import java.net.URL;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.WebElement;
import org.openqa.selenium.remote.DesiredCapabilities;
import org.testng.Assert;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;

import io.appium.java_client.ios.IOSDriver;

public class iOSBrowserTest
{
	private IOSDriver<WebElement> mobiledriver;
		
	@BeforeTest
	public void beforeTest( ) throws MalformedURLException {
		// Create Object of DesiredCapability class 
		DesiredCapabilities caps = new DesiredCapabilities();
		// Set the device name
		caps.setCapability("deviceName", "iPhone 6");
		// Set the platform name and version
		caps.setCapability("platformName", "iOS");
		caps.setCapability("platformVersion", "12.4");
		// Set the browser in emulator
		caps.setCapability("browserName", "safari");
		caps.setCapability("noReset", "true");
		caps.setCapability("newCommandTimeout", 2000);
		// Pass the capability object and start the session
		mobiledriver = new IOSDriver<WebElement>(new URL("http://127.0.0.1:4723/wd/hub"), caps);
		mobiledriver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
	}

	@AfterTest
	public void afterTest( ) {
		mobiledriver.quit();
	}

	@Test
	public void launchBrowser() {
		// Open an web application with provided URL
		mobiledriver.get("http://appium.io/");
		// Perform test operations; check the URL and the title of page
		Assert.assertEquals(mobiledriver.getCurrentUrl(), "http://appium.io/", "URL Mismatch");
		Assert.assertEquals(mobiledriver.getTitle(), "Appium: Mobile App Automation Made Awesome.", "Title Mismatch");
	}
}
```

[iOS Testing Using Appium and JAVA](https://www.swtestacademy.com/ios-testing-appium-java/)

#### [Return: Express README](../../README.md)
