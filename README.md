# coding

// tips for java selenium validations to prevent common browser error

//this helps to handle idleTimeout error while opening Chrome browser.
DesiredCapabilities handlSSLErr = DesiredCapabilities.chrome();
handlSSLErr.setCapability("idleTimeout", 150); 


//accepts the SSL certificate 
handlSSLErr.setCapability(CapabilityType.ACCEPT_SSL_CERTS, true);
WebDriver driver = new ChromeDriver(handlSSLErr);
		
//this prevents the notification in chrome browser
Map<String,Object> prefs = new HashMap<String,Object>();
prefs.put("profile.default_content_setting_values.notifications",2);

ChromeOptions options = new ChromeOptions();
options.setExperimentalOption("prefs",prefs);
	
