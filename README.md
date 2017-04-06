# selenium_examples

Environment
    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-server</artifactId>
        <version>3.0.1</version>
    </dependency>

    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-htmlunit-driver</artifactId>
        <version>2.52.0</version>
    </dependency>

    <dependency>
        <groupId>org.json</groupId>
        <artifactId>json</artifactId>
        <version>20160810</version>
    </dependency>

WebDriver 如果只是单机，不需要启动服务器；事先下载准备好chromedriver，不要用本机安装的

    String chromeBinary = "/opt/chromedriver";
    System.setProperty("webdriver.chrome.driver", chromeBinary);
    driver = new ChromeDriver();

Locating element(s) with findElement/findElements
* driver.findElement(By.tagName(...))
* By.linkText(...)
* By.partialLinkText(...)
* By.cssSelector(...)
* By.xpath(...)
* By.id(...)
* By.name(...)
* By.className(..)

cssSelector

* By.cssSelector("input[name=username]")
* By.cssSelector("input#username")
* By.cssSelector("img[alt='Previous']")
* By.cssSelector("img[alt]")
* By.cssSelector("img:not([alt])")
* input[id^='ctrl'] 以ctrl开始
* input[id$='_userName'] 以_userName结尾
* input[id*='userName'] 包含userName
* By.cssSelector("td:contains('Item 1')")
* form#loginForm:first-child
* from#loginForm:last-child
* form#loginForm:nth-child(2)
* input:focus
* input:enabled
* input:checked

XPath
* driver.findElement(By.xPath("html/body/div/div/form/input"))
* WebElement img_item = a_item.findElement(By.xpath("div[1]/div[1]/img")) 从当前元素a_item开始找，注意元素的序号从1开始，div[1]表示第一个div
* WebElement p_item = a_item.findElement(By.xpath("div[@class='info']/p"))
* List<WebElement> recommendItems = driver.findElements(By.xpath("//li[contains(@class,'img-item')]"))
* List<WebElement> recommendItems = driver.findElements(By.xpath("//div[contains(@class, 'item-inner') and contains(@class, 'y-box')]"))
* driver.findElement(By.xpath("//input[@type='submit' or @value='Login']"))
* driver.findElements(By.xpath("img[@alt]"))
* input[starts-with(@id,'ctrl')]
* input[ends-with(@id,'_userName')]
* input[contains(@id,'userName')]
* input[@*='username']

axis
* //td[text()='Product 1']/ancestor::table  得到table
* /table/descendant::td/input
* td[text()='Product 1']/follwing::tr 
* //td[contains(text(), 'Item 1')]
* //td[.='Item 1']

API
* getText()
* getAttribute("align")
* getCssValue("width")

Action
* Actions builder = new Actions(driver);
* builder.click(tableRows.get(1)).keyDown(Keys.CONTROL).click(tableRows.get(3)).keyUp(Keys.CONTROL).build().perform();
* builder.doubleClick(message).build.perform();
* builder.dragAndDrop(source, target).perform();

js Executor
    JavascriptExecutor js = (JavascriptExecutor) driver;
    String title = (String) js.executeScript("return document.title");
    assertEquals("Google", title);
    
    long links = (Long) js.executeScript("var links = document.getEelementsByTagName('A'); return links.length");
    assertEquals(42, links);
    
    driver.close();
    
afsda
