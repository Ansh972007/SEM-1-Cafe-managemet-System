// CAFE SEM 1 project


import java.util.*;

class MENU {
    String ITEM_NAME;
    double ITEM_PRICE;
    int ITEM_QUANTITY;
    double TOTAL_ITEM_PRICE;
    double TOTAL_BILL;
    int TOTAL_QYANTITY;

    static int ITEM_COUNT = 17;

    Scanner sc = new Scanner(System.in);

   void MENU(MENU AARAY_OF_ITEMS[])
   {
        
        AARAY_OF_ITEMS[1].ITEM_NAME = "ELAICHI CHAI         ";
        AARAY_OF_ITEMS[2].ITEM_NAME = "ADARAK WALI CHAI     ";
        AARAY_OF_ITEMS[3].ITEM_NAME = "MASALA CHAI          ";
        AARAY_OF_ITEMS[4].ITEM_NAME = "GREEN TEA            ";
        AARAY_OF_ITEMS[5].ITEM_NAME = "HERBAL TEA           ";
        AARAY_OF_ITEMS[6].ITEM_NAME = "HOT VELVET COFFEE    ";
        AARAY_OF_ITEMS[7].ITEM_NAME = "COLD VELVET COFFEE   ";
        AARAY_OF_ITEMS[8].ITEM_NAME = "FILTER COFFEE        ";
        AARAY_OF_ITEMS[9].ITEM_NAME = "HONEY CINNAMON COFFEE";
        AARAY_OF_ITEMS[10].ITEM_NAME = "IRISH COFFEE        ";
        AARAY_OF_ITEMS[11].ITEM_NAME = "LEMON GREEN COFFEE  ";
        AARAY_OF_ITEMS[12].ITEM_NAME = "ICED CAPPUCCINO     ";
        AARAY_OF_ITEMS[13].ITEM_NAME = "VANILLA CAPPUCCINO  ";
        AARAY_OF_ITEMS[14].ITEM_NAME = "SANDWITCH           ";
        AARAY_OF_ITEMS[15].ITEM_NAME = "BUTTER VADAPAW      ";
        AARAY_OF_ITEMS[16].ITEM_NAME = "CHEESE VADAPAW      ";

        AARAY_OF_ITEMS[1].ITEM_PRICE = 190;
        AARAY_OF_ITEMS[2].ITEM_PRICE = 190;
        AARAY_OF_ITEMS[3].ITEM_PRICE = 190;
        AARAY_OF_ITEMS[4].ITEM_PRICE = 240;
        AARAY_OF_ITEMS[5].ITEM_PRICE = 255;
        AARAY_OF_ITEMS[6].ITEM_PRICE = 210;
        AARAY_OF_ITEMS[7].ITEM_PRICE = 248;
        AARAY_OF_ITEMS[8].ITEM_PRICE = 195;
        AARAY_OF_ITEMS[9].ITEM_PRICE = 200;
        AARAY_OF_ITEMS[10].ITEM_PRICE = 248;
        AARAY_OF_ITEMS[11].ITEM_PRICE = 210;
        AARAY_OF_ITEMS[12].ITEM_PRICE = 238;
        AARAY_OF_ITEMS[13].ITEM_PRICE = 248;
        AARAY_OF_ITEMS[14].ITEM_PRICE = 40;
        AARAY_OF_ITEMS[15].ITEM_PRICE = 40;
        AARAY_OF_ITEMS[16].ITEM_PRICE = 70;
    }

    void Display() {
        for (int i = 1; i < ITEM_COUNT; i++) {
            System.out.println(i + ".     " + " ITEM NAME -->>     " + COFFEE.AARAY_OF_ITEMS[i].ITEM_NAME  );
            System.out.println("            " + " ITEM PRICE -->>    " + COFFEE.AARAY_OF_ITEMS[i].ITEM_PRICE);
        }
    }

    void ITEM_ORDER() {
        boolean b = true;

        while (b) {
            System.out.println("Please Enter 1. for Continue ordering ");
            System.out.println("Please Enter 2. for stop ordering ");
            System.out.println(" ");

            int Order = sc.nextInt();

            switch (Order) {
                case 1: {
                    System.out.println("See the menu above and enter the INDEX of ITEM which you want to order ");
                  
					int INDEX = sc.nextInt();
                    boolean boolean_variabel = true;
                    do
					{
                    System.out.println("Please Enter Quantity of " + COFFEE.AARAY_OF_ITEMS[INDEX].ITEM_NAME);
					  System.out.println("Maximum you should 15 items order. ");
					  int temp_quantity = sc.nextInt();
                    if((temp_quantity<=15)&&(temp_quantity>=0))
					{
                    COFFEE.AARAY_OF_ITEMS[INDEX].ITEM_QUANTITY += temp_quantity;
					boolean_variabel = false;
                    break;
					}
					else
					System.out.println("you should enter item quantity between 0 and 15; ");	
				}while(boolean_variabel);	
					
                }

                case 2: {
                    for (int i = 1; i < ITEM_COUNT; i++) {
                        TOTAL_QYANTITY = TOTAL_QYANTITY + COFFEE.AARAY_OF_ITEMS[i].ITEM_QUANTITY;
                    }
                    System.out.println(" ");
                    System.out.println(" ");
                    System.out.println("Your order has been received");
                    System.out.println("Thank you for ordering food");
                    System.out.println(" ");
                    System.out.println(" ");

                    b = false;
                    break;
                }
                default: {
                    System.out.println("Invalid Input");
                }
            }
        }
    }

    
    void applyDiscount() {
		if(TOTAL_BILL >=1000)
		{
        System.out.println("Do you want to apply a discount? Enter 1 for Yes, 2 for No:");
        int choice = sc.nextInt();
        if (choice == 1) {
            System.out.println("Enter discount type: 1 for Percentage");
            System.out.println("Enter discount type: 2 for Fixed Amount");
            int discountType = sc.nextInt();

            if (discountType == 1) {
                System.out.println("Enter discount percentage (e.g., 10 for 10%):");
                double discountPercent = sc.nextDouble();
                double discountAmount = (discountPercent / 100) * TOTAL_BILL;
                TOTAL_BILL -= discountAmount;
                System.out.println("Discount of " + discountPercent + "% applied. Discount Amount: " + discountAmount);
            } else if (discountType == 2) {
                System.out.println("Enter fixed discount amount:");
                double discountAmount = sc.nextDouble();
                TOTAL_BILL -= discountAmount;
                System.out.println("Fixed Discount Amount of " + discountAmount + " applied.");
            } else {
                System.out.println("Invalid discount type.");
            }
        } else {
            System.out.println("No discount applied.");
        }
    }
	
	else
		System.out.println("Your Total Bill should be grater than 1000 rupic or equals.  ");
	
	}

    void Payment_Method()
	{
		System.out.println("choose payment method :");
		System.out.println("1. credit card ");
		System.out.println("2. cash ");
		System.out.println("3. UPI ");
		
		int payment = sc.nextInt();
		
		switch(payment)
		{
			case 1 :
			   System.out.println("your payment successfully");
			    break;
			case 2 :
			   System.out.println("your payment successfully");
			    break;
			case 3 :
			   System.out.println("your payment successfully");
			    break;
			default :
			    System.out.println("Invalid Input");
		}
		
		
	}


    void BILL_GENERATION() 
	{   System.out.println("YOUR Bill : ");
        System.out.println(" ");
        System.out.println(" ");
        System.out.println("-----------------------------------------------------------------------------  ");
        System.out.println("-----------------------------------------------------------------------------  ");
        System.out.println(" ");
        System.out.println(" ");
        System.out.println("NO.       YOUR ITEMS            ITEM Price        ITEM Quantity      TOTAL Price ");

        int NO = 1;

        for (int i = 0; i < ITEM_COUNT; i++) {
            COFFEE.AARAY_OF_ITEMS[i].TOTAL_ITEM_PRICE = (COFFEE.AARAY_OF_ITEMS[i].ITEM_PRICE * COFFEE.AARAY_OF_ITEMS[i].ITEM_QUANTITY);

            if (COFFEE.AARAY_OF_ITEMS[i].ITEM_QUANTITY > 0)
				{
              System.out.println(NO+".   "+COFFEE.AARAY_OF_ITEMS[i].ITEM_NAME + "          " + COFFEE.AARAY_OF_ITEMS[i].ITEM_PRICE + "     X    " + COFFEE.AARAY_OF_ITEMS[i].ITEM_QUANTITY + "               =    " + COFFEE.AARAY_OF_ITEMS[i].TOTAL_ITEM_PRICE);
                   NO++;
                TOTAL_BILL = TOTAL_BILL + COFFEE.AARAY_OF_ITEMS[i].TOTAL_ITEM_PRICE;
            }
        }

        System.out.println("-----------------------------------------------------------------------------  ");
        System.out.println("-----------------------------------------------------------------------------  ");
        System.out.println(" ");

        System.out.println("<<----------------|| YOUR TOTAL BILL : " + TOTAL_BILL + " ||----------------->>");
        System.out.println("<<----------------|| YOUR TOTAL BILL WITH 18% GST : " + (TOTAL_BILL + (0.18 * TOTAL_BILL)) + " ||----------------->>");
        
		 applyDiscount(); 
		 
		System.out.println("<<----------------|| YOUR TOTAL BILL WITH APPIY DISCOUNT : " + TOTAL_BILL + " ||----------------->>");
		
		System.out.println(" ");
        System.out.println(" ");
		Payment_Method();
    }
}

class COFFEE {
    static MENU AARAY_OF_ITEMS[] = new MENU[MENU.ITEM_COUNT];

    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);

        System.out.println(" ");
        System.out.println(" ");
        System.out.println(" ");
        System.out.println("                        <<--| HELLO WELCOME TO OUR COFFEE. |-->>");
        System.out.println(" ");
        System.out.println(" ");
        System.out.println(" ");

        boolean b = true;

        MENU ob1 = new MENU();

        int COUNT = 0;

        while (b) {
            System.out.println("");
            System.out.println("");
            System.out.println("");
            System.out.println("                          PLEASE PRESS 1. ~~>>   COFFEE MENU		");
            System.out.println("                          PLEASE PRESS 2. ~~>>   ORDER			");
            System.out.println("                          PLEASE PRESS 3. ~~>>   YOUR BILL		");
            System.out.println("                          PLEASE PRESS 4. ~~>>   FEEDBACK	");
            System.out.println("                          PLEASE PRESS 5. ~~>>   EXIT         	");
            System.out.println("");
            System.out.println("");
            System.out.print("            CHOICE :       ");

            int CHOICE = sc.nextInt();

            System.out.println("                   ");
            System.out.println("                   ");
            System.out.println("                   ");

            switch (CHOICE)
			{
                case 1: {
                    for (int i = 0; i < MENU.ITEM_COUNT; i++) {
                        AARAY_OF_ITEMS[i] = new MENU();
                    }

                    ob1.MENU(AARAY_OF_ITEMS);
                    COUNT++;
                    ob1.Display();
                    break;
                }
                case 2: {
                    if (COUNT == 0) {
                        System.out.println("Kindly visit the menu of the COFFEE first.");
                        break;
                    } else {
                        System.out.println("FOR ORDERING ITEM");
                        ob1.ITEM_ORDER();
                        break;
                    }
                }
                case 3: {
                    if (ob1.TOTAL_QYANTITY > 0) {
                        ob1.BILL_GENERATION();
						
                        break;
                    } else {
                        System.out.println("For bill generation, at least one item must be ordered.");
                        break;
                    }
                }
                case 4: {
                    System.out.println("If you wish to give feedback, enter a rating between 0.0 to 5.0");
                    double feedback = sc.nextDouble();
                    break;
                }
                case 5: {
                    System.out.println("Thank you for visiting.");
                    b = false;
                    break;
                }
                default: {
                    System.out.println("Invalid input. Please TRY AGAIN!");
                }
            }
        }
    }
}