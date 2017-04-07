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

  
