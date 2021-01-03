
package com.saurabhkumar.bankingsystem;

import java.util.Scanner;

 class BankApplication{

    public static void main(String[] args)
    {
            BankAccount obj1 = new BankAccount("ABC","C10008");
            obj1.showMenu();
   
    }
  }

public class BankAccount {
    int balance,previousTransactions;
    String CustomerName,CustomerId;
    char option;
BankAccount(String cname,String cid)
{
   CustomerName= cname;
   CustomerId= cid;
   
}
    
    void deposit(int amount){
        if (amount != 0)
            
        {
         balance=balance+amount;
         previousTransactions=amount;
        } 
}
    void withdraw(int amount)
    {           
   
       if (amount != 0)
           
       {
           balance =balance - amount;
           previousTransactions= -amount;
           
       }
           
    }
   
   void getPreviousTransactions()
 {
  if(previousTransactions > 0)
  {
      System.out.println("Deposited" +previousTransactions);
              
  }
  else if(previousTransactions < 0)
  {
      System.out.println("Withdrawn" +Math.abs(previousTransactions));
      
  }
  else
  {
      System.out.println("No Transaction Occurred");
  }
}
    
   
void showMenu()
{
     char option;
        option = '\n';
     Scanner scanner = new Scanner(System.in);
     
     System.out.println("Welcome "+CustomerName);
     System.out.println("Your ID is "+CustomerId);
     System.out.println("\n");
     System.out.println("A.Check Balance");
     System.out.println("B. Deposit");
     System.out.println("C. Withdrawn");
     System.out.println("D.Previous Transaction");
     System.out.println("E. Exit");
    do
    {
         System.out.println("==========================================================================");
         System.out.println("Enter an Option");
         System.out.println("==========================================================================");
         option = scanner.next().charAt(0);
         System.out.println("\n");
         
       switch(option)
       {
           case 'A':
          System.out.println("------------------------------------------------------------------------");
          System.out.println("Balance= "+balance);
          System.out.println("------------------------------------------------------------------------");
          System.out.println("\n");
          break;
      
     
       case 'B':

          
       System.out.println("---------------------------------------------------------------------------");
        
       System.out.println("Enter the amount to deposit");
       System.out.println("---------------------------------------------------------------------------");
            int amount = scanner.nextInt();
       System.out.println("\n");
       deposit(amount);
       break;
       
       case 'C':
       System.out.println("---------------------------------------------------------------------------");
       System.out.println("Enter the amount for withdrawal");
       System.out.println("---------------------------------------------------------------------------");
         int amount2= scanner.nextInt();
         
         withdraw(amount2);
         System.out.println("\n");
         break;
       
         case 'D':
           System.out.println("--------------------------------------------------------------------------");
           getPreviousTransactions();
           System.out.println("--------------------------------------------------------------------------");
           System.out.println("\n");
           
       default:
           System.out.println("Invalid Option!! Please Enter Again");
           break;
           
       case 'E':
           System.out.println("-----------------------------------------------------------------------");
           break;
       }      
                 
    }
    while(option != 'E');
    System.out.println("THANK YOU FOR USING OUR SERVICES");
    
    

     
}
}
