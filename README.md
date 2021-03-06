# Shoprite Survey Test Framework

- Using Java Maven TestNG Selenium

## Step 0: Setup
1. Add Selenium and TestNG dependencies to the [*pom.xml*](https://mvnrepository.com/artifact/org.seleniumhq.selenium/selenium-java)
2. Add the TestNG Eclipse Plugin
3. Run a test to see if it's working. I checked if it navigates to [Shoprite's Survey page](https://www.myshopriteexperience.com/)

## Step 1: Soft Asserts, Select, and Explicit Waits
0. I created a static Java file for my user inputs for Shoprite. But, kept it hidden from GitHUb for my data privacy.
1. Implement [Soft Asserts](https://www.softwaretestingmaterial.com/soft-assert/) so you can check multiple items.
2. Implement [Explicit Waits](https://www.selenium.dev/documentation/en/webdriver/waits/) with Expected Conditions and WebDriverWaits. 
	- This will ensure that your driver will start testing once the elements or properties display after loading.
3. Implement [Select](https://stackoverflow.com/questions/12940592/how-to-select-an-item-from-a-dropdown-list-using-selenium-webdriver-with-java) for inputting and checking Dropdown values
	- This specifically helps for checking dropdown items.

## Step 2: Implement Page Object Model
1. Create a separate page object file that initializes the WebDriver and Explicit Wait time.
	- I used only ChromeDriver. You can create different drivers and set it as Page object Factory. 
	- I set the explicit wait time for 10 seconds 
2. Implement [FindBy annotation](https://www.selenium.dev/selenium/docs/api/java/org/openqa/selenium/support/FindBy.html).
	- This [improves the Page Object Pattern](https://stackoverflow.com/questions/18436102/selenium-findby-vs-driver-findelement) and makes it easier for maintenance
	- When you use FindBy, you have to use PageFactory to initialize web elements
3. Implement a Data Transfer Object for Time. I kept mine's separate in the 'data' directory.
	- This will make our tests more readable
	- This will remove the need for Soft Asserts