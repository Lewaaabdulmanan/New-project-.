package L;

import java.util.Scanner;

public class l{
    private static Scanner input = new Scanner(System.in);
    //عرض المشروبات
        public static String[] menuItems = {
        "coffee", "hot chocolate", "milk","soda", "milk shake", "squash","water", "green tea","juice ","Iced juice","lemon","tea" };
 //اسعار المشروبات
       public static int[] menuPrices = {
        2000, 3000, 800, 2000, 3600, 1500, 700, 500,1000,2000,700,300    };
//نوع نظام الدفع(دالة))
        public static String[] paymentMethods = {
    "Cash", "Credit Card", "Online Payment"};

public static int[] paymentPrices = {
    0, 100, 200}; 
    //المنتج مع السعر مع نوع نظام الدفع (دالة) 
private static void displayMenu() {
    System.out.println("Menu:");
System.out.println(" ");
    for (int i = 0; i < menuItems.length; i++) {
        System.out.println((i + 1) + ". " + menuItems[i] + " ● price: " + menuPrices[i] + " real");
    }
System.out.println(" ");
    System.out.println("Payment Methods:");
    for (int i = 0; i < paymentMethods.length; i++) {
        System.out.println((i + 1) + ". " + paymentMethods[i] + " - fee: " + paymentPrices[i] + " real");
    }
}
//داله لطلب المنتج 
  public static void placeOrder() {
    System.out.println("Place order:");
    System.out.println("_________");
    int choice = getInput("Enter item number", 1, menuItems.length);
    String kk = menuItems[choice - 1];
    
    int paymentChoice = getInput("Select payment method", 1, paymentMethods.length);
    String paymentMethod = paymentMethods[paymentChoice - 1];
    
    int mm= menuPrices[choice - 1] + paymentPrices[paymentChoice - 1];
    
    System.out.println(kk+ ", mm amount to pay: " + mm+ " real. Thank you for using this service");
}
 //دالة في حالة اذا كنت تريد الطلب مررة اخرى
  public static int getInput(String message, int min, int max) {
        int choice;
        
        do {
            System.out.println(message);
            choice = input.nextInt();
            
            if (choice < min || choice > max) {
 System.out.println("Invalid choice. Please try again.");
            }
        } while (choice < min || choice > max);
        
        return choice;
    }
    
    public static void main(String[] args) {
       System.out.println("☆☆☆☆welcom to  Lewaa's drinks☆☆☆☆");
         boolean you = true;

        do {
            displayMenu();
       System.out.println(" ");
 int choice = getInput("Enter number from 1 to 2",1,2);           
            switch (choice) {
                case 1:
       System.out.println("Enter the specified order:");  
                    placeOrder();
                    break;
                case 2:
                    System.out.println("Exiting");
                    System.exit(0);
                    break;
                default:
System.out.println("Invalid choice. Please try again.");
            }
            
  System.out.println("@ Do you want to order again?");
            you = input.nextBoolean();
        } while (you);
    }
}
//لواء عبدالمنان حامد عثمان
//هندسة برمجيات
