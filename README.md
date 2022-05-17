package WebdriverCommands;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class alertOkCancel {

	public static void main(String[] args) {
		System.setProperty("webdriver.chrome.driver", "C://bin//chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.get("http://demo.automationtesting.in/Alerts.html");
		driver.findElement(By.xpath("/html[1]/body[1]/div[1]/div[1]/div[1]/div[1]/div[1]/ul[1]/li[2]/a[1]")).click();
		driver.findElement(By.xpath("//button[@class='btn btn-primary']")).click();
		System.out.println(driver.switchTo().alert().getText());
		driver.switchTo().alert().accept();
		String actText = driver.findElement(By.xpath("//p[@id='demo']")).getText();
		
		if (actText.equals("You pressed Ok"))
			System.out.println("test is passed");
		
		driver.findElement(By.xpath("//button[@class='btn btn-primary']")).click();
		
		driver.switchTo().alert().dismiss();
		actText = driver.findElement(By.xpath("//p[@id='demo']")).getText();
		if (actText.equals("You Pressed Cancel"))
			System.out.println("test passed");

		driver.close();
		

	}

}
