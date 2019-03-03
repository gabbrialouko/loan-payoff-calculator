# loan-payoff-calculator
User enters loan amount, interest rate, and monthly payment. Program calculates new monthly principle, amount paid in interest and how may years it would take to pay off the loan.

import java.io.*;
import java.util.*;
import java.text.*;

public class LoanOnhand
{
static Scanner console = new Scanner(System.in);

public static void main(String[] args) 
{
  double loanAmount = 0.00;
  double loanAmountLeft = 0.00;
  double monthlyInterestRate = 0.00;
  double monthlyPayment = 0.00;
  double monthlyInterestPercent = 0.00;
  double principle = 0.00;
  double monthlyInterestAmount = 0.00;
  double interestRate = 0.00;
  double x; 
  double leftOnLoan;
                                                                       
System.out.print("Enter the loan amount: ");
loanAmount = console.nextDouble();
System.out.println();

System.out.print("Enter the interest rate: ");
interestRate = console.nextDouble();
System.out.println();

System.out.print("Enter monthly payment: ");
monthlyPayment = console.nextDouble();
System.out.println();

monthlyInterestRate = interestRate /12;
monthlyInterestPercent = monthlyInterestRate /100;
leftOnLoan = loanAmount;
int counter= 0;
int monthsToPayoff = 0;

do 
 {
monthlyInterestAmount = leftOnLoan * monthlyInterestPercent;
x = monthlyPayment - monthlyInterestAmount;
leftOnLoan = leftOnLoan - x;
counter ++;
monthsToPayoff = monthsToPayoff + 1;

DecimalFormat twodecimalsFormat = new DecimalFormat("0.00");

 System.out.println("Amount left on loan after payment " + "#" + counter + " is  " + twodecimalsFormat.format(leftOnLoan) +  " Principle  " + twodecimalsFormat.format(x) + " Interest  " + twodecimalsFormat.format(monthlyInterestAmount));
}
while(leftOnLoan > 0);
 
   if (leftOnLoan  < monthlyPayment );{
   DecimalFormat twodecimalsFormat = new DecimalFormat("0.00");
   counter ++;

     System.out.println("Original loan amount is............." + twodecimalsFormat.format(loanAmount));
     System.out.println("Interest rate is...................." + twodecimalsFormat.format(interestRate));
     System.out.println("Monthly payment amount is..........." + twodecimalsFormat.format(monthlyPayment));
     System.out.println("Number of months to pay off loan....." + monthsToPayoff);
        
   }
  }                
}
