package seleniumnew;

import java.io.File;
import java.io.IOException;
import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.edge.EdgeDriver;
import org.openqa.selenium.io.FileHandler;
import org.testng.Assert;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

import org.openqa.selenium.support.ui.WebDriverWait;
import org.openqa.selenium.support.ui.ExpectedConditions;

public class Cleartrip {
	ChromeDriver driver;
	
	@BeforeTest
	public void setup()
	{
		driver=new ChromeDriver();
		driver.manage().window().maximize();
		
	}
	@BeforeMethod
	public void url()
	{
		driver.get("https://www.cleartrip.com/bus");
	}
	@Test
	public void test() throws InterruptedException, IOException
	{
		
		
		
		
		driver.findElement(By.xpath("//*[@id=\"departure\"]")).sendKeys("Pune");

		driver.findElement(By.xpath("//*[@id=\"arrival\"]")).sendKeys("Delhi");
		
		//String month="May 2024";
		
		/*Thread.sleep(2000);
		driver.findElement(By.xpath("/html/body/div/div[2]/div[1]/div[2]/div/div/div[1]/div[1]/div[2]/div/div")).click();
		
		Thread.sleep(2000);
		while(true)
		{
			String act=driver.findElement(By.xpath("//*[@id=\"134643a2a23a2aads2ssasss23ssaaassssfaaassssssss2sa22\"]/div/div/div/div[2]/h3")).getText();
			if(act.equals(month))
			{
				break;
				
			}
			else
			{
				
				driver.findElement(By.xpath("//*[@id=\"134643a2a23a2aads2ssasss23ssaaassssfaaassssssss2sa22\"]/div/div/div/div[3]")).click();
			}
			Thread.sleep(2000);
			driver.findElement(By.xpath("//*[@id=\"134643a2a23a2aads2ssasss23ssaaassssfaaassssssss2sa22-grid-0\"]/tbody/tr[2]/td[6]/button")).click();
		}*/
		driver.findElement(By.xpath("/html/body/div/div[2]/div[1]/div[2]/div/div/div[1]/div[1]/div[2]/div/div")).click();
		driver.findElement(By.xpath("//*[@id=\"134643a2a23a2aads2ssasss23ssaaassssfaaassssssss2sa22-grid-0\"]/tbody/tr[3]/td[4]/button")).click();
		Thread.sleep(2000);
		WebDriverWait wait=new WebDriverWait(driver,Duration.ofSeconds(20));
	   
	 
		WebElement searchBusButton = driver.findElement(By.xpath("//button[@class='btn-wrapper ml-4 w-50p primary-orange-bg']"));
		searchBusButton.click();

	}
	@Test(priority = 2)
	public void test2() throws IOException, InterruptedException
	{
		Thread.sleep(2000);

		 WebElement searchbar = driver.findElement(By.xpath("/html/body/div/div[2]/div[1]/div[2]/div/div/div[1]/div[1]/div[2]/button"));
	        
	        // capture screenshot with getScreenshotAs() of the WebElement class
	        File f = searchbar.getScreenshotAs(OutputType.FILE);
	        
	        FileHandler.copy(f, new File("C:\\Users\\anoos\\OneDrive\\Pictures 1\\Screenshots\\Screeshotkk.png"));
	        
	        driver.close();
	        }
	}

