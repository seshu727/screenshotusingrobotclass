# screenshotusingrobotclass
package com.Functionlib.java;

import java.awt.AWTException;
import java.awt.Dimension;
import java.awt.Rectangle;
import java.awt.Robot;
import java.awt.Toolkit;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import java.util.concurrent.TimeUnit;

import javax.imageio.ImageIO;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class robotscreencapture {
	static WebDriver driver;
	public static void main(String[] args) throws AWTException, IOException, InterruptedException {
	       driver = new ChromeDriver();
		   driver.get("http://efcdev.firstaccess.co/");
		   driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
		    Robot r = new Robot();
			Dimension d = Toolkit.getDefaultToolkit().getScreenSize();
			Rectangle re = new Rectangle(d);
			BufferedImage bf = r.createScreenCapture(re);
			ImageIO.write(bf,"png", new File("./capture.png"));
			System.out.println("done");
			System.out.println("ok");
		
		
		
		
	}

}
