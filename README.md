# My-Repository
package selenium;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

public class Gmail {

	public static void main(String[] args) throws InterruptedException {
    
    //Launch driver: Chrome driver
		System.setProperty("webdriver.chrome.driver", "path of chrome driver");
		WebDriver driver = new ChromeDriver();
		driver.manage().timeouts().pageLoadTimeout(10, TimeUnit.SECONDS);
		driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
    //maximize window
		driver.manage().window().maximize();
    //Launch Gmail using URL
		driver.get("https://www.gmail.com");
		//Provide email address
		driver.findElement(By.xpath("//input[@id='identifierId']")).sendKeys("Email ID of User");
	        driver.findElement(By.xpath("//div[@id='identifierNext']")).click();
		
		
		WebElement passwordButton = driver.findElement(By.xpath("//input[@name='password']"));
		wait.until(ExpectedConditions.elementToBeClickable(passwordButton));
    //Provide password
		passwordButton.sendKeys("Password of user's Email");
		driver.findElement(By.xpath("//div[@id='passwordNext']")).click();
		
		//Click on compose button
		driver.findElement(By.xpath("//div[text()='Compose']")).click();
		
 //Enter the recipient's mail id
		driver.findElement(By.xpath("//textarea[@name='to']")).sendKeys("Sender e-mail id");
 //Enter subject to the mail
		driver.findElement(By.xpath("//input[@name='subjectbox']")).sendKeys("Selenium script");
		driver.findElement(By.xpath("//div[@class='Am Al editable LW-avf']")).sendKeys("Subject Line of the mail");
		
 //Attach the full path of file
 driver.findElement(By.xpath("//input[@name='Filedata']")).sendKeys("Path of the file to be attached");
 //Click on send 
 driver.findElement(By.xpath("//div[text()='Send']")).click();
	}
}
