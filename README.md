# Automation

*Login Journey*
package Advance;

import org.openqa.selenium.By;
import org.openqa.selenium.SearchContext;
import org.openqa.selenium.WebDriver;

public class LoginRepository 

{
	WebDriver wd;
	public LoginRepository(WebDriver wd2) {
		// TODO Auto-generated constructor stub
	}

	By uname=By.id("Email Id / Mobile No");
	By pword=By.id("password");
	SearchContext Capha=(SearchContext) By.id("captchaValue");
	By sin=By.className("btn-primary");
	
	void username(String un)
	{
		By d = null;
		d.findElement((SearchContext) uname).sendKeys(un);
	}
	
	void password(String pw)
	{
		By d = null;
		d.findElement((SearchContext) pword).sendKeys(pw);
	}
	
	void capcha(String cp)
	{
		By d = null;
		d.findElement(Capha).sendKeys(cp);
	}
	
	void signin()
	{
		By d = null;
		d.findElement((SearchContext) sin).click();
	}
	void AllElement(String un, String pw)
	{
		username(un);
		String cp = null;
		capcha(cp);
		password(pw);
		signin();
	}

	
		
	}







*Add new customer*

package Advance;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;

public class Newcustomer 
{

	WebDriver d;
	public void LoginRepoEx(WebDriver wd)
	{
		d=wd;
	}
    By custom=By.xpath("//*[@id=\"kt_content\"]/div/ng-component/kt-customers-list/mat-drawer-container/mat-drawer-content/kt-portlet/div/kt-portlet-header/div[4]/button[1]/span[1]");
    By Lname=By.xpath("//*[@id=\"mat-input-13\"]");
    By Refno=By.xpath("//*[@id=\"mat-input-93\"]");
    By Refby=By.xpath("//*[@id=\"mat-select-value-109\"]/span");
    By conper=By.name("Contact Person Name");
    By Mobno=By.id("Mobile Number");
    By Telno=By.id("Telephone Number");
    By Email=By.id("Email");
    By conperdes=By.id("PersonDesignation");
    
    void customer()
    {
    	d.findElement(custom).click();
    
    }
    
    void Leadname(String ln)
    {
    	d.findElement(Lname).sendKeys(ln);
    }
    
    void Refrenceno()
    {
    	d.findElement(Refno).sendKeys();
    }
    
    void Refrenceby(String rb)
    {
    	d.findElement(Refby).sendKeys(rb);
    }
    
    void Contactper(String cn)
    {
    	d.findElement(conper).sendKeys(cn);
    }
    
    void Mobile()
    {
    	d.findElement(Mobno).sendKeys();
    }
    
    void Telephone()
    {
    	d.findElement(Telno).sendKeys();
    }
    
    void email()
    {
    	d.findElement(Email).sendKeys();
    }
    
    void contactdes(String cd)
    {
    	d.findElement(conperdes).sendKeys(cd);
    }
    }



    *Calling page*

    package Advance;

import java.time.Duration;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class Callingpage {

	public static void main(String[] args)
	{
		
		WebDriver wd=new ChromeDriver();
		wd.manage().window().maximize();
		wd.manage().timeouts().implicitlyWait(Duration.ofSeconds(40));
		wd.get("https://testffc.nimapinfotech.com/");
		
		LoginRepository lr=new LoginRepository(wd);
		lr.username("bhaskarsargar10@gmail.com");
		lr.password("Nerul@91");
		lr.capcha("1LGGD3");
		lr.signin();
		
		Newcustomer nc=new Newcustomer(wd);
		nc.customer();
		nc.Leadname(Meena);
		nc.Refrenceno(8214);
		nc.Refernceby(veena);
		nc.Contactper(Nitesh);
		nc.Mobile(1245679871);
		nc.Telephone(0224512387);
		nc.email();
		nc.conperdes(Associate);
	}

}



	
	
	
