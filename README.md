package selenium;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class GitAutomation {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
		System.setProperty("webdriver.chrome.driver", "D:\\chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);

		driver.get("https://github.com");
		driver.manage().window().maximize();
		driver.findElement(By.xpath("//a[@class='HeaderMenu-link no-underline mr-3']")).click();
		driver.findElement(By.id("login_field")).sendKeys("maliyan123");
		driver.findElement(By.id("password")).sendKeys("maliyan@123");
		driver.findElement(By.xpath("//input[@value='Sign in']")).click();
		Thread.sleep(4000);
		WebElement a = driver.findElement(By.id("repos-container"));
		a.findElement(By.xpath("//a[contains(@class,'btn')]")).click();
		driver.findElement(By.id("repository_name")).sendKeys("AutomationF111");
		driver.findElement(By.id("repository_auto_init")).click();
		Thread.sleep(5000);
		driver.findElement(By.xpath("//button[contains(text(),'Create repository') and @type='submit']")).click();

		driver.findElement(By.xpath("//span[contains(text(),'Issues')]")).click();
		driver.findElement(By.xpath("//span[contains(text(),'New issue')]")).click();
		driver.findElement(By.id("issue_title")).sendKeys("UI Issue");
		driver.findElement(By.id("issue_body")).sendKeys(
				"Step 1: Login\r\n" + "Step 2: Tap on profile button\r\n" + "Step 3: Observe the close Icon ");
		Thread.sleep(5000);
		driver.findElement(By.xpath("//button[@class='btn btn-primary']")).click();
		String s = driver.findElement(By.className("gh-header-number")).getText();
		System.out.println(s);
		Thread.sleep(5000);
		driver.findElement(
				By.xpath("//div[@id='partial-discussion-header']//div//div//div//a[contains(text(),'New issue')]"))
				.click();

		driver.findElement(By.id("issue_title")).sendKeys("UI Issue on profile page");
		driver.findElement(By.id("issue_body")).sendKeys("Go to Profile page \r\n" + s);
		driver.findElement(By.xpath("//button[@class='btn btn-primary']")).click();
		driver.findElement(By.id("new_comment_field"))
				.sendKeys("Issue is resolved , please perform sanity for the flow");
		Thread.sleep(4000);
		driver.findElement(By.xpath("//button[contains(text(),'Comment')]")).click();
		Thread.sleep(5000);
		driver.findElement(By.xpath("//span[contains(text(),'Code')]")).click();
		Thread.sleep(3000);
		driver.findElement(By.xpath("//div[@id='readme']//div//div//a")).click();
		Thread.sleep(9000);
		driver.findElement(By.xpath("//div[contains(@class,'CodeMirror-code')]//div[1]//pre[1]")).sendKeys(":mask:");
		driver.findElement(By.id("submit-file")).click();
		driver.findElement(By.xpath("//span[contains(text(),'Issues')]")).click();
		driver.findElement(By.id("issue_1_link")).click();
		driver.findElement(By.id("new_comment_field")).sendKeys("#2");
		Thread.sleep(3000);
		driver.findElement(By.xpath("//button[contains(text(),'Comment') and @type='submit']")).click();
		driver.findElement(By.xpath("//a[@class='issue-link js-issue-link']")).click();
		driver.findElement(By.xpath("//span[contains(text(),'Settings')]")).click();
		driver.findElement(By.xpath("//summary[contains(text(),'Delete this repository')]")).click();
		driver.findElement(
				By.xpath("//div[contains(@class,'Box-body overflow-auto')]//input[contains(@name,'verify')]"))
				.sendKeys("maliyan123/AutomationF111");
		driver.findElement(By.xpath("//button[contains(text(),'I understand the consequences, delete this reposit')]"))
				.click();

	}
}
