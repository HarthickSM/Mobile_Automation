# Mobile_Automation

Testcase steps:- 1) open the bonatara Application
                 2) The Food Log section can be found by tapping on the "Food" tab at the bottom of the screen.
                 3) The "+" button can be found in the top right corner of the food log page.
                 4) The option to add food can be found by tapping on the "Add Food" button.
                 5) The search bar can be found at the top of the food log page.
                 6) The desired food can be chosen from the search results by tapping on its name.
                 7) The selected food will be displayed in the food log page.
                 8)The food can be added to the breakfast, morning snack, lunch, evening snack, or dinner column by tapping on the corresponding column.
                 9)Repeat steps 8-9 for multiple foods..
                 
                 
Test script:-   List<String> foodItems = Arrays.asList("rava idli", "Oats idli","strawberry Banana orange juice");
		  	/* random iteration ==========================
		        // Create a Random object
		      Random random = new Random();

		        try {
		            int maxIterations = Math.min(foodItems.size(), 3);

		            for (int i = 0; i < maxIterations; i++) {
//		                int randomIndex = random.nextInt(foodItems.size());
		                String foodItem = foodItems;//.get(randomIndex);
		                System.out.println(i + ": " + foodItem);

		             ======================*/  
		  	  int maxIterations =  3;

	            for (int i = 0; i < maxIterations; i++) {
	                String foodItem = foodItems.get(i);
	                System.out.println(i + ": " + foodItem);
	            		  // Click on "ADD FOOD" element
	                
	               try {
	            	   driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	            	   String xpath = "(//android.widget.TextView[@text='ADD FOOD'])[1]";
	            	   scrollAndClickElement(xpath);
	            	   System.out.println("without send ");
	               }
	               catch(Exception e)
		              {
		            	  System.out.println("without send ");
		                    WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[1]"));
		   	               action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
		                    System.out.println("abc");
		                    Thread.sleep(2000);
		           }
	               System.out.println("without send ");
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                WebElement click_on_search21 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.view.ViewGroup/android.widget.EditText"));
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(click_on_search21))).perform();
	                System.out.println("time two");
	                //Introduce a delay to ensure the element is ready to receive text input
	                Thread.sleep(3000);
	                System.out.println("clickon the search");
	                //Send keys (enter text) to the element
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                click_on_search21.sendKeys(foodItem);
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                // Click on Enter to perform the search
	                WebElement Add_on_button2 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.widget.Button/android.view.ViewGroup/android.widget.TextView"));
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
	                Thread.sleep(2000);
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
	                Thread.sleep(2000);
	                
	            }
	            System.out.println("brakfast food is completed");
	         
		}
	  public static void scrollAndClickElement(String xpath) throws InterruptedException {
//          MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollIntoview("
//       		   +"new UiSelector().description(\"Add Food\"));");
       	WebDriverWait wait = new WebDriverWait(driver, 10);
       	 while (wait.until(ExpectedConditions.invisibilityOfElementLocated(By.xpath(xpath)))) {
       	        // Scroll the screen
       		 System.out.println(xpath);
       	        Dimension size = driver.manage().window().getSize();
       	        int startX = size.width / 2;
       	        int startY = (int) (size.height * 0.5);
       	        int endY = (int) (size.height * 0.2);

       	        new TouchAction<>(driver)
       	                .press(PointOption.point(startX, startY))
       	                .waitAction(WaitOptions.waitOptions(Duration.ofMillis(500)))
       	                .moveTo(PointOption.point(startX, endY))
       	                .release()
       	                .perform();
       	    }
       	TouchAction action = new TouchAction(driver);
          WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[1]"));
             action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
           System.out.println("--");
           Thread.sleep(2000);      
        
        }
	  @Test(priority = 2, enabled = true )
		public static void morningnsack() throws InterruptedException {
		        Thread.sleep(7000);

		        // Define the food items
		  	  List<String> foodItems = Arrays.asList("egg Omelet", "spanish Rice","strawberry Banana orange juice");
		  	/* random iteration ==========================
		        // Create a Random object
		      Random random = new Random();

		        try {
		            int maxIterations = Math.min(foodItems.size(), 3);

		            for (int i = 0; i < maxIterations; i++) {
//		                int randomIndex = random.nextInt(foodItems.size());
		                String foodItem = foodItems;//.get(randomIndex);
		                System.out.println(i + ": " + foodItem);

		             ======================*/  
		  	  int maxIterations =  3;

	            for (int i = 0; i < maxIterations; i++) {
	                String foodItem = foodItems.get(i);
	                System.out.println(i + ": " + foodItem);
	            		  // Click on "ADD FOOD" element
	                
	               try {
	            	   driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	            	   String xpath = "(//android.widget.TextView[@text='ADD FOOD'])[2]";
	            	   scrollAndClickElements(xpath);
	            	   System.out.println("without send ");
	               }
	               catch(Exception e)
		              {
		            	  System.out.println("without send ");
		                    WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[2]"));
		   	               action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
		                    System.out.println("abc");
		                    Thread.sleep(2000);
		           }
	               System.out.println("without send ");
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                WebElement click_on_search21 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.view.ViewGroup/android.widget.EditText"));
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(click_on_search21))).perform();
	                System.out.println("time two");
	                //Introduce a delay to ensure the element is ready to receive text input
	                Thread.sleep(3000);
	                System.out.println("clickon the search");
	                //Send keys (enter text) to the element
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                click_on_search21.sendKeys(foodItem);
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                // Click on Enter to perform the search
	                WebElement Add_on_button2 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.widget.Button/android.view.ViewGroup/android.widget.TextView"));
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
	                Thread.sleep(2000);
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
	                Thread.sleep(6000);
	          }
	            System.out.println("brakfast food completed");
		}
	  public static void scrollAndClickElements(String xpath) throws InterruptedException {
//        MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollIntoview("
//     		   +"new UiSelector().description(\"Add Food\"));");
     	WebDriverWait wait = new WebDriverWait(driver, 10);
     	 while (wait.until(ExpectedConditions.invisibilityOfElementLocated(By.xpath(xpath)))) {
     	        // Scroll the screen
     		 System.out.println(xpath);
     	        Dimension size = driver.manage().window().getSize();
     	        int startX = size.width / 2;
     	        int startY = (int) (size.height * 0.3);
     	        int endY = (int) (size.height * 0.2);

     	        new TouchAction<>(driver)
     	                .press(PointOption.point(startX, startY))
     	                .waitAction(WaitOptions.waitOptions(Duration.ofMillis(500)))
     	                .moveTo(PointOption.point(startX, endY))
     	                .release()
     	                .perform();
     	    }
     	TouchAction action = new TouchAction(driver);
        WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[2]"));
           action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
         System.out.println("--");
         Thread.sleep(2000); 
	  
	  }  
	  @Test(priority = 3, enabled = true)
		public static void lunch() throws InterruptedException {
		        Thread.sleep(7000);

		        // Define the food items
		  	  List<String> foodItems = Arrays.asList("chapati", "White Rice",  "Methi Roti");
		  	/* random iteration ==========================
		        // Create a Random object
		      Random random = new Random();

		        try {
		            int maxIterations = Math.min(foodItems.size(), 3);

		            for (int i = 0; i < maxIterations; i++) {
//		                int randomIndex = random.nextInt(foodItems.size());
		                String foodItem = foodItems;//.get(randomIndex);
		                System.out.println(i + ": " + foodItem);

		             ======================*/  
		  	  int maxIterations =  2;

	            for (int i = 0; i < maxIterations; i++) {
	                String foodItem = foodItems.get(i);
	                System.out.println(i + ": " + foodItem);
	            		  // Click on "ADD FOOD" element
	                
	               try {
	            	   driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	            	   String xpath = "(//android.widget.TextView[@text='ADD FOOD'])[3]";
	            	   scrollAndClickElementss(xpath);
	            	   System.out.println("without send ");
	               }
	               catch(Exception e)
		              {
		            	  System.out.println("without send ");
		                    WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[3]"));
		   	               action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
		                    System.out.println("abc");
		                    Thread.sleep(2000);
		           }
	               System.out.println("without send ");
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                WebElement click_on_search21 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.view.ViewGroup/android.widget.EditText"));
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(click_on_search21))).perform();
	                System.out.println("time two");
	                //Introduce a delay to ensure the element is ready to receive text input
	                Thread.sleep(3000);
	                System.out.println("clickon the search");
	                //Send keys (enter text) to the element
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                click_on_search21.sendKeys(foodItem);
	                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	                // Click on Enter to perform the search
	                WebElement Add_on_button2 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.widget.Button/android.view.ViewGroup/android.widget.TextView"));
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
	                Thread.sleep(2000);
	                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
	                Thread.sleep(6000);
	                
	            }
	            System.out.println("lunch food completed");
		}
	  public static void scrollAndClickElementss(String xpath) throws InterruptedException {
//        MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollIntoview("
//     		   +"new UiSelector().description(\"Add Food\"));");
     	WebDriverWait wait = new WebDriverWait(driver, 10);
     	 while (wait.until(ExpectedConditions.invisibilityOfElementLocated(By.xpath(xpath)))) {
     	        // Scroll the screen
     		 System.out.println(xpath);
     	        Dimension size = driver.manage().window().getSize();
     	        int startX = size.width / 2;
     	        int startY = (int) (size.height * 0.3);
     	        int endY = (int) (size.height * 0.2);

     	        new TouchAction<>(driver)
     	                .press(PointOption.point(startX, startY))
     	                .waitAction(WaitOptions.waitOptions(Duration.ofMillis(500)))
     	                .moveTo(PointOption.point(startX, endY))
     	                .release()
     	                .perform();
     	    }
     	TouchAction action = new TouchAction(driver);
        WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[3]"));
           action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
         System.out.println("--");
         Thread.sleep(2000); 
	  
	  } 
	  @Test(priority = 4, enabled  = true )
			public static void eveningsnack() throws InterruptedException {
			        Thread.sleep(7000);

//			        Thread.sleep(4000);
			        TouchAction action = new TouchAction(driver);

			        // Define the food items
			  	  List<String> foodItems = Arrays.asList("vada pav", "Sandwich Spread");
			  	/* random iteration ==========================
			        // Create a Random object
			      Random random = new Random();

			        try {
			            int maxIterations = Math.min(foodItems.size(), 3);

			            for (int i = 0; i < maxIterations; i++) {
//			                int randomIndex = random.nextInt(foodItems.size());
			                String foodItem = foodItems;//.get(randomIndex);
			                System.out.println(i + ": " + foodItem);

			             ======================*/  
			  	  int maxIterations =  2;

		            for (int i = 0; i < maxIterations; i++) {
		                String foodItem = foodItems.get(i);
		                System.out.println(i + ": " + foodItem);
		            		  // Click on "ADD FOOD" element
		                
		               try {
		            	   driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		            	   String xpath = "(//android.widget.TextView[@text='ADD FOOD'])[3]";
		            	   scrollAndClickElementsss(xpath);
		            	   System.out.println("without send ");
		               }
		               catch(Exception e)
			              {
			            	  System.out.println("without send ");
			                    WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[3]"));
			   	               action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
			                    System.out.println("abc");
			                    Thread.sleep(2000);
			           }
		               System.out.println("without send ");
		                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		                WebElement click_on_search21 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.view.ViewGroup/android.widget.EditText"));
		                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(click_on_search21))).perform();
		                System.out.println("time two");
		                //Introduce a delay to ensure the element is ready to receive text input
		                Thread.sleep(3000);
		                System.out.println("clickon the search");
		                //Send keys (enter text) to the element
		                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		                click_on_search21.sendKeys(foodItem);
		                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		                // Click on Enter to perform the search
		                WebElement Add_on_button2 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.widget.Button/android.view.ViewGroup/android.widget.TextView"));
		                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
		                Thread.sleep(2000);
		                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
		                Thread.sleep(6000);
		                
		            }
		            
		            
		            System.out.println("enving snack food completed");
			}
		  public static void scrollAndClickElementsss(String xpath) throws InterruptedException {
//	        MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollIntoview("
//	     		   +"new UiSelector().description(\"Add Food\"));");
	     	WebDriverWait wait = new WebDriverWait(driver, 10);
	     	 while (wait.until(ExpectedConditions.invisibilityOfElementLocated(By.xpath(xpath)))) {
	     	        // Scroll the screen
	     		 System.out.println(xpath);
	     	        Dimension size = driver.manage().window().getSize();
	     	        int startX = size.width / 2;
	     	        int startY = (int) (size.height * 0.3);
	     	        int endY = (int) (size.height * 0.2);

	     	        new TouchAction<>(driver)
	     	                .press(PointOption.point(startX, startY))
	     	                .waitAction(WaitOptions.waitOptions(Duration.ofMillis(500)))
	     	                .moveTo(PointOption.point(startX, endY))
	     	                .release()
	     	                .perform();
	     	    }
	     	TouchAction action = new TouchAction(driver);
	        WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[3]"));
	           action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
	         System.out.println("--");
	         Thread.sleep(2000); 
		  
		  } 
		  
		  @Test(priority = 5,enabled = true)
			public static void din() throws InterruptedException {
//			        Thread.sleep(7000);


			        // Define the food items
			  	  List<String> foodItems = Arrays.asList("Grilled Chicken", "Methi Roti");
			  	/* random iteration ==========================
			        // Create a Random object
			      Random random = new Random();

			        try {
			            int maxIterations = Math.min(foodItems.size(), 3);

			            for (int i = 0; i < maxIterations; i++) {
//			                int randomIndex = random.nextInt(foodItems.size());
			                String foodItem = foodItems;//.get(randomIndex);
			                System.out.println(i + ": " + foodItem);

			             ======================*/  
			  	  int maxIterations =  2;

		            for (int i = 0; i < maxIterations; i++) {
		                String foodItem = foodItems.get(i);
		                System.out.println(i + ": " + foodItem);
		            		  // Click on "ADD FOOD" element
		                
		               try {
		            	   driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		            	   String xpath = "(//android.widget.TextView[@text='ADD FOOD'])[3]";
		            	   scrollAndClickElementssss(xpath);
		            	   System.out.println("without send ");
		               }
		               catch(Exception e)
			              {
			            	  System.out.println("without send ");
			                    WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[3]"));
			   	               action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
			                    System.out.println("abc");
			                    Thread.sleep(2000);
			           }
		               System.out.println("without send ");
		                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		                WebElement click_on_search21 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.view.ViewGroup/android.widget.EditText"));
		                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(click_on_search21))).perform();
		                System.out.println("time two");
		                //Introduce a delay to ensure the element is ready to receive text input
		              
		                System.out.println("clickon the search");
		                //Send keys (enter text) to the element
		                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		                click_on_search21.sendKeys(foodItem);
		                driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		                // Click on Enter to perform the search
		                WebElement Add_on_button2 = driver.findElement(By.xpath("/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[1]/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.FrameLayout/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.widget.ScrollView/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.view.ViewGroup/android.view.ViewGroup/android.view.ViewGroup[2]/android.widget.Button/android.view.ViewGroup/android.widget.TextView"));
		                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
		                Thread.sleep(2000);
		                action.tap(TapOptions.tapOptions().withElement(ElementOption.element(Add_on_button2))).perform();
		                Thread.sleep(6000);
		                
		            }
		            System.out.println("Dinner food completed");
		            
			}
		  public static void scrollAndClickElementssss(String xpath) throws InterruptedException {
//	        MobileBy.AndroidUIAutomator("new UiScrollable(new UiSelector().scrollIntoview("
//	     		   +"new UiSelector().description(\"Add Food\"));");
	     	WebDriverWait wait = new WebDriverWait(driver, 10);
	     	 while (wait.until(ExpectedConditions.invisibilityOfElementLocated(By.xpath(xpath)))) {
	     	        // Scroll the screen
	     		 System.out.println(xpath);
	     	        Dimension size = driver.manage().window().getSize();
	     	        System.out.println(size);
	     	        int startX = size.width/2 ;
	     	        int startY = (int) (size.height * 0.5);
	     	        int endY = (int) (size.height * 0.4);

	     	        new TouchAction<>(driver)
	     	                .press(PointOption.point(startX, startY))
	     	                .waitAction(WaitOptions.waitOptions(Duration.ofMillis(400)))
	     	                .moveTo(PointOption.point(startX, endY))
	     	                .release()
	     	                .perform();
	     	    }
	     	TouchAction action = new TouchAction(driver);
	        WebElement uiclickon_add_anothertry1_food = driver.findElement(By.xpath("(//android.widget.TextView[@text='ADD FOOD'])[3]"));
	           action.tap(TapOptions.tapOptions().withElement(ElementOption.element(uiclickon_add_anothertry1_food))).perform();
	         System.out.println("--");
	         Thread.sleep(2000); 
	         
	        
		  
		  }                  
