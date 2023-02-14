package naveenautomationpractice;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

public class TrelloAutomation {

	public static void main(String[] args) throws InterruptedException {
	
		
		        // Set the path to the Chrome driver
		        System.setProperty("webdriver.chrome.driver","D://Software//July Mor//chromedriver_win32 (3)//chromedriver.exe");
		        // Create a new instance of the Chrome driver
		        WebDriver driver = new ChromeDriver();
		       
		        // Navigate to the Trello login page
		        driver.get("https://trello.com/login");
		       driver.manage().window().maximize();
		        // Find the email and password fields, and enter the credentials
		        WebElement emailField = driver.findElement(By.id("user"));
		        emailField.sendKeys("kedarbhushetti@gmail.com");
		        
		        Thread.sleep(2000);
		        
		        WebElement Continue = driver.findElement(By.xpath("//*[@type='submit']"));
		        Continue.click();
		        Thread.sleep(2000);
		        
		        WebElement passwordField = driver.findElement(By.id("password"));
		        passwordField.sendKeys("Shri@8585");
		        
		        WebElement Login_submit = driver.findElement(By.xpath("//button[@type='submit']"));
		        Login_submit.click();
		       
		        // Wait for the page to load
		        Thread.sleep(3000);
		       
		        // Click the "Create a board" button
		        driver.findElement(By.xpath("//li[@data-testid='create-board-tile']")).click();
		       
		        // Wait for the board creation form to appear
		        Thread.sleep(3000);
		       
		        // Enter the board name and click the "Create" button
		        WebElement boardNameField = driver.findElement(By.xpath("//input[@type='text']"));
		        boardNameField.sendKeys("My Trello Board");
		        
		        driver.findElement(By.xpath("//button[@data-testid='create-board-submit-button']")).click();
		       
		        // Wait for the board to be created
		        Thread.sleep(3000);
		       
	         // Create List A card
		      WebElement ListA=driver.findElement(By.xpath("//input[@name='name']"));
		     
		        
		    ListA.sendKeys("LIST A");
		        
		    WebElement List_A_Submit=driver.findElement(By.xpath("//input[@type='submit']"));
		    List_A_Submit.click();
		    Thread.sleep(2000);
		    
		    //Create List B card
		    WebElement ListB=driver.findElement(By.xpath("//input[@name='name']"));
		   ListB.sendKeys("LIST B");
		   Thread.sleep(2000);
		   WebElement List_B_Submit=driver.findElement(By.xpath("//input[@type='submit']"));
		   List_B_Submit.click();
		    Thread.sleep(2000);
		        
		    //To Add in List A 
			  driver.findElement(By.xpath("//span[@class='js-add-a-card']")).click();
			
			   System.out.println("success");
			
			   driver.findElement(By.xpath("//textarea[@placeholder='Enter a title for this card…']")).sendKeys("My card");
			  Thread.sleep(2000);
			   driver.findElement(By.xpath("//input[@value='Add card']")).click();
			   
			   WebElement card = driver.findElement(By.xpath("//span[@class='list-card-title js-card-name']"));
			   
			   
				WebElement listA = driver.findElement(By.xpath("//textarea[@aria-label='LIST A']"));
				
				WebElement listB = driver.findElement(By.xpath("//textarea[@aria-label='LIST B']"));
				

				Actions builder = new Actions(driver);
				builder.dragAndDrop(card, listB).perform();
				System.out.println("Drag and drop success");
			   
				
				
			   Thread.sleep(5000);
			    driver.findElement(By.xpath("//div[@Class='OUdAuicP657Tka']")).click();
			    Thread.sleep(2000);
			    driver.findElement(By.xpath("//a[@Class='yTThzZMDkelhke']")).click();
			    Thread.sleep(3000);
			    
			    driver.findElement(By.xpath("//span[@class='css-178ag6o']")).click();
			    Thread.sleep(3000);
			  
			 
			  System.out.println("Successfully Logout");
		        
		       driver.close();
	}
	}
