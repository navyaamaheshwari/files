import java.util.Scanner;
public class atm {
     public static class operations
     {
         double amount;
         operations(double amount)
         {
             this.amount=amount;
         }
         public double withdraw(double p)
         {
             if(p>=amount)
             {
                 System.out.println("Unsufficient Bank Balance");
                 return -1;
             }
             else
             {
                 amount-=p;
                 return p;
             }
//             return p;
         }
         public void deposit(double p)
         {
             amount+=p;
         }
         public void checkbalance()
         {
//             System.out.println("Available Bank Balance is: ");
             System.out.println(amount);
         }
     }
     public static class userbankacc{

         static double usersbankbalance()
         {
             System.out.println("The Available Bank Balance is : ");
             Scanner sc=new Scanner(System.in);
             double amt=sc.nextDouble();
             return amt;
         }
     }
    public static void main(String[] args) {
         userbankacc ss=new userbankacc();
         double p=ss.usersbankbalance();
 operations obj=new operations(p);
 Scanner sc=new Scanner(System.in);
        System.out.println("Enter the operation");
        System.out.println("1 for deposit amount");
        System.out.println("2 for withdrawl amt");
        System.out.println("3 for check bank balance");
 int n=sc.nextInt();
 switch(n)
 {
     case 1:
         System.out.println("Enter the amount to be deposit");
         double amt=sc.nextDouble();
         obj.deposit(amt);
         System.out.println("credited bank balance is: ");
         obj.checkbalance();
         break;
     case 2:
         System.out.println("Enter the amount to be withdrawl");
         double pp=sc.nextDouble();
         System.out.println(obj.withdraw(pp));
         System.out.println("debited bank balance is: ");
         obj.checkbalance();
         break;
     case 3: System.out.println("Available Bank Balance is: ");
         obj.checkbalance();
         break;
 }
    }
}
