# Run-Appium-server-through-program

Step1:-first find out the path of node.js file


Linux-"/usr/lib/node_modules/appium/build/lib/main.js"

Windows-"C:\\Users\\user\\AppData\\Local\\Programs\\appium-desktop\\resources\\app\\node_modules\\appium\\build\\lib\\main.js"


Step2:Download Commons-validator jar file by


https://mvnrepository.com/artifact/commons-validator/commons-validator/1.4.0


Step3:-write down these lines of code before desiredcapabilities to run appium server


static AppiumDriverLocalService appiumService; 

static String appiumServiceUrl;

AppiumServiceBuilder builder = new AppiumServiceBuilder().withAppiumJS(newFile("/usr/lib/node_modules/appium/build/lib/main.js")); 

appiumService = builder.build(); 
    
appiumService.start();


Step4:-To kill all the services run the command if you are getting error of server port is already in use

/usr/bin/killall -KILL node


Step5:-to stop appium server write code

appiumService.start();

