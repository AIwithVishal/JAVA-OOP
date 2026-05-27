 Prem Vishal

# METHODS IN JAVA

Objectives
1.	Understand the purpose and importance of methods in Java
2.	Define and call different types of methods
3.	Use methods with parameters and return values
4.	Apply control statements including if-else, switch, and ternary inside methods
5.	Write methods that work with Strings and Arrays
6.	Use built-in Math class functions through methods
7.	Understand and use command-line arguments
8.	Organize logic into reusable and readable code
1. Methods
A method is a block of code that performs a specific task. Methods help reduce code repetition, improve readability, and make programs modular and manageable. In this lab, all methods are declared static so they can be called directly from the main method without creating objects.
Method Syntax

static returnType methodName(parameters) {
    // method body
}

2. Types of Methods
2.1 Method with No Parameters and No Return Value
This type of method is used when a task only performs an action such as displaying a message and does not need input or output.

static void greet() {
    System.out.println("Welcome to Java Methods Lab");
}

2.2 Method with Parameters and No Return Value
These methods accept input values as parameters and perform operations without returning a result.

static void printSquare(int num) {
    System.out.println("Square is: " + (num * num));
}

2.3 Method with Return Value and No Parameters
This type of method performs a calculation and returns a value without taking any input parameters.

static int getFixedNumber() {
    return 10;
}

2.4 Method with Parameters and Return Value
This is the most commonly used method type. It takes input, processes it, and returns a result.

static int add(int a, int b) {
    return a + b;
}

3. Methods with Control Statements
3.1 If–Else Inside a Method
If–else statements allow decision-making inside methods based on conditions.

static String checkResult(int marks) {
    if (marks >= 40)
        return "Pass";
    else
        return "Fail";
}

3.2 Ternary Operator in Methods
The ternary operator is a short form of if–else used for simple conditional expressions.

static int findMax(int a, int b) {
    return (a > b) ? a : b;
}

3.3 Switch Statement in Methods
The switch statement is used when multiple conditions are based on a single variable value.

static String dayName(int day) {
    switch (day) {
        case 1: return "Monday";
        case 2: return "Tuesday";
        case 3: return "Wednesday";
        case 4: return "Thursday";
        case 5: return "Friday";
        default: return "Invalid Day";
    }
}

4. Methods with String Basics
4.1 String Length
The length() method returns the number of characters present in a string.

static int getLength(String text) {
    return text.length();
}

4.2 String Comparison
Strings should be compared using equals() instead of == to compare actual content.

static boolean checkName(String name) {
    return name.equals("Ali");
}

4.3 String Case Conversion

static String convertToUpper(String word) {
    return word.toUpperCase();
}

5. Methods with Arrays
5.1 Sum of Array Elements
Arrays can be passed to methods to perform calculations on multiple values.

static int sumArray(int[] arr) {
    int sum = 0;
    for (int i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    return sum;
}

5.2 Find Maximum Element in Array

static int findMax(int[] arr) {
    int max = arr[0];
    for (int i = 1; i < arr.length; i++) {
        if (arr[i] > max)
            max = arr[i];
    }
    return max;
}

6. Methods Using Math Class
The Math class provides built-in static methods for common mathematical operations. These methods can be used directly without creating objects.
6.1 Power Function

static int calculatePower(int a, int b) {
    return (int) Math.pow(a, b);
}

6.2 Absolute Value

static int getAbsolute(int x) {
    return Math.abs(x);
}

7. Command-Line Arguments
Command-line arguments allow data to be passed to the program at the time of execution. They are received as an array of strings in the main method.
Example: Using Command-Line Arguments

class CommandLineExample {
    public static void main(String[] args) {
        int a = Integer.parseInt(args[0]);
        int b = Integer.parseInt(args[1]);
        System.out.println("Sum: " + (a + b));
    }
}

8. Complete Example Program

class MethodLab2 {

    static int square(int x) {
        return x * x;
    }

    static boolean isPositive(int x) {
        return x > 0;
    }

    static String checkDay(int d) {
        return dayName(d);
    }

    static String dayName(int day) {
        switch (day) {
            case 1: return "Monday";
            case 2: return "Tuesday";
            default: return "Invalid";
        }
    }

    public static void main(String[] args) {
        int n = 5;
        System.out.println("Square: " + square(n));
        System.out.println("Is Positive: " + isPositive(n));
        System.out.println("Day: " + checkDay(1));
    }
}

Lab Guidelines
• All methods must be static
• Write logic inside methods, not directly in main
• Use meaningful method names
• Follow proper indentation and formatting
Outcome
After completing this lab, students will be able to design modular Java programs using methods and apply control logic, strings, arrays, math operations, and command-line arguments effectively.

 
Exercises
Instructions:
• Solve all tasks using methods only.
• main() should only call methods and print results.
• All methods must be static.
• Focus on logic and clean implementation.

Task 0: Syntax Errors
Broken Code	Find the Error	Fix It
static int add(int a int b){ return a+b; }	 In this code,
The error is that the parameters should be seperared by comma	 static int add(int a, inb)
{return a+b; }
static void show(){ System.out.println("Hi") }	 In this code,
The error is:
 Semicolon “ ;”	 Show(){
System.out.println(“Hi”);}
static int square(int x){ System.out.println(x*x); }	 Int this code,
the error is of:
 return value	 Static int sqaure(int x){
return (x*x);
}
switch(x){ case 1: System.out.println("One") break; }	 In this code,
The error is:
Semicolon “;”	 switch(x){ case 1: System.out.println("One");
break; }
int[] arr = new int[5]	 In this code,
The error is:
Semicolon “;”	 int[] arr = new int[5];
public static void main(String args){ }	 The error is:
square bracket and semicolon	 public static void main(String[] args);
static int max(int[] arr){ return arr.length }	 The error is:
semicolon ‘ ; ’	 static int max(int[] arr){ return arr.length; }

Task 1: Smart Number Analyzer
Method Type:
Return: String
Parameters: int n

Return:
• "Positive Even" if number is positive and even
• "Positive Odd" if positive and odd
• "Negative" if number is negative
• "Zero" if number is 0

CODE:

import java.util.Scanner;
class Vishal{
	static String analyzer(int num){
		if((num%2==0)&&(num>0)){
			return "The number is Even and positive..";
		}else if((num%2!=0)&&(num>0)){
			return "The number is odd and positive..";
		}else if(num<0){
			 return "The number is negative..";
		}else {
			return "The number is 0..";
		}
	}	
	public static void main(String[] args){
		Scanner input = new Scanner(System.in);
		System.out.println("Enter a number:");
		int num = input.nextInt();
			System.out.println(analyzer(num));

	}
}

 
Task 2: Conditional Calculator
Method Type:
Return: int
Parameters: int a, int b

Rules:
• If a > b, return a − b
• If a < b, return b − a
• If equal, return 0

Code:
import java.util.Scanner;
class Calculator{
	static int calcu(int a, int b){
		if(a > b){
		   return a-b;
		}else if(a<b){
		return b-a;
		}else{
		return 0;
		}
	}
	public static void main(String[] args){
		Scanner input = new Scanner(System.in);
		System.out.println("Enter the first number: ");
		int num1 = input.nextInt();
		System.out.println("Enter the second number: ");
		int num2 = input.nextInt();
		System.out.println(calcu(num1,num2));
	}
}

 
Task 3: Array Balance Checker
Method Type:
Return: boolean
Parameters: int[] arr

Return true if sum of even elements equals sum of odd elements.

CODE:

import java.util.*;
class Dada{
	static boolean sum(int array[]){
		int evenSum=0;
		int oddSum=0;
		for(int i=0; i<array.length; i++){
		if(array[i]%2==0){
			evenSum+=array[i];
		}else{
			oddSum+=array[i];
		}
	}if(evenSum==oddSum){
		return true;
	}else {
		return false;
	}
	}
	public static void main(String[] args){
		Scanner input = new Scanner(System.in);
		int[] array = new int[6];
		System.out.println(" Array is : ");
		for(int i=0;i<6;i++){
			array[i]= input.nextInt();
		}
		System.out.println(sum(array));
	}
}
} 


Task 4: Switch-Driven Grading System
Method Type:
Return: String
Parameters: int marks

Use switch on (marks / 10):
• 10 → Distinction
• 9 → Excellent
• 8 → Very Good
• Others → Fail
Note: marks are in range (0-100).

CODE:
import java.util.*;
class Ehsan{
	static String Grading(int marks){
		switch(marks/10){
		case 10:
			return "Distiction";
		case 9:
			return "Excellent";
		case 8:
			return "very good";
		default:
			 return "Fail";
		}
	}
	public static void main(String[] args){
		Scanner input = new Scanner(System.in);
		System.out.println("Enter the marks : ");
		int marks = input.nextInt();
			 if((marks>100) || (marks<0)){
			System.out.println("invalid marks..");
		}
			System.out.println(Grading(marks));
		}
	}

Task 5: String Pattern Validator
Method Type:
Return: boolean
Parameters: String s

Return true if:
• Length ≥ 6
• First character uppercase
• Last character is a digit

CODE:

import java.util.*;
class Prem{
	static boolean pattern(String s){
		if ((s.length()>=6)&&
		(Character.isUpperCase(s.charAt(0)))&&
		(Character.isDigit(s.charAt(s.length()-1))))
			return true;
  		else
 			return false;
}
	public static void main(String[] args){
		Scanner input = new Scanner(System.in);
		System.out.println("Enter the String : ");
		String s = input.next();
		System.out.println(pattern(s));
	}
}
Task 6: Array Peak Finder
Method Type:
Return: int
Parameters: int[] arr

Return index of the largest element.
If multiple max values exist, return first index.


CODE:

import java.util.*;
class Dell{
	static int finder(int arr[]){
		int max=arr[0];
		for(int i=0;i<arr.length;i++){
			if(arr[i]>max){
				max=arr[i];
			}
		}
		for(int i=0;i<arr.length;i++){
			if(arr[i]==max)
			return i;
		}
			return -1;
		}
	public static void main(String[] args){
		Scanner input = new Scanner(System.in);
		System.out.println("Enter the size of array: ");
			int size = input.nextInt();
			int array[] = new int[size];
		System.out.println("THe array is:");
			for(int i=0;i<size;i++){
			array[i]= input.nextInt(); 
		}
		System.out.println("THe output is: ");
			for(int i=0;i<size;i++){
			System.out.println(array[i]);
		}
		System.out.println("The maximun number is found at index:");

		System.out.println(finder(array));
	}
}

 
Task 7: Math-Based Decision Maker
Method Type:
Return: String
Parameters: int a, int b

Return "Perfect Square Difference" if |a − b| is a perfect square.
Otherwise return "Not Perfect Square".




CODE:

import java.util.*;
class Square{
	static String root(int a, int b){
		int minus =0;
		minus = a-b;
		for(int i=1;i<=minus;i++){
			int perSquare = i*i;
			if(perSquare==minus){
				return "This is perfect Square..";
			}
		}
			return "This is not perfect Square..";
	}
	public static void main(String[] args){
		Scanner input = new Scanner(System.in);
		System.out.println("Enter the first number:");
		int num1 =input.nextInt();
		System.out.println("Enter the second number:");
		int num2 =input.nextInt();
		int minus=0;
		minus = num1-num2;
		System.out.println(minus);
		System.out.println(root(num1,num2));
		
	}
}



 
Task 8: Command-Line Validator
Method Type:
Return: void
Parameters: String[] args

Accept 3 numbers via command-line and print:
• Largest number
• Smallest number
• Difference between them

CODE:

import java.util.*;
class Validator {
    static void commandLine(String [] args){
        int a = Integer.parseInt(args[0]);
        int b = Integer.parseInt(args[1]);
        int c = Integer.parseInt(args[2]);
        int max = a;
        int min = a;
        if((a>b) && (a>c)){
            max = a;
        }else if((b>a) && (b>c)){
            max = b;
        }else{
            max = c;
        }
        if((a<b) && (a<c)){
            min = a;
        }else if((b<a) && (b<c)){
            min = b;
        }else{
            min = c;
        }
        int diff = max - min;
        System.out.println("Maximum = " + max);
        System.out.println("Minimum = " + min);
        System.out.println("Difference = " + diff);
    }

     public static void main(String [] args){
        commandLine(args);
     }
 }

 
Task 9: Array Trend Detector
Method Type:
Return: String
Parameters: int[] arr

Return:
• "Increasing" if strictly increasing order in numbers
• "Decreasing" if strictly decreasing order in numbers
• "Mixed" otherwise

CODE:

import java.util.Scanner;

public class oop {

    
    static String arrayTrendDetector(int[] arr) {

        
        if (arr.length < 2) {
            return "Mixed";
        }

        boolean increasing = true;
        boolean decreasing = true;

        
        for (int i = 0; i < arr.length - 1; i++) {

            
            if (arr[i] >= arr[i + 1]) {
                increasing = false;
            }

           
            if (arr[i] <= arr[i + 1]) {
                decreasing = false;
            }
        }

        
        if (increasing) {
            return "Increasing";
        } 
        else if (decreasing) {
            return "Decreasing";
        } 
        else {
            return "Mixed";
        }
    }

   
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        
        System.out.print("Enter array size: ");
        int size = sc.nextInt();

        int[] arr = new int[size];

     
        System.out.println("Enter array elements:");
        for (int i = 0; i < size; i++) {
            arr[i] = sc.nextInt();
        }

       
        String result = arrayTrendDetector(arr);
        System.out.println("Array Trend: " + result);

        sc.close();
    }
}

 

Task 10: Mini Decision Engine
Method Type:
Return: String
Parameters: int n

Return:
• "Prime Even" if n = 2
• "Prime Odd" if prime and odd
• "Composite" if not prime
• "Invalid" if n ≤ 1

CODE:

import java.util.Scanner;
class lab {
	static String decisionMaking(int n){
		for(int i=2; i<n; i++){
			if(n%i==0){
				return "Composite";
			}
		}
		if(n==2){
			return "Prime Even";
		}
		else if(n<=1){
			return  "Invalid";
			}		
		
			else return "Prime Odd";
		
		}
	public static void main(String[]args){

		Scanner sc = new Scanner(System.in);
		
		System.out.print("Enter the Number: ");
		
		int n =sc.nextInt();
		
		System.out.println(decisionMaking(n));
	}
}

 


Task 11: Debugging Practice

Broken Code	Find the Error	Fix It
int[] a = new int[5]; a[5] = 10;	 The error is:
array index is always: 
size -1
because it starts from 0	 int[] a = new int[5]; 
a[4] = 10;
int sum; for(int i=0;i<arr.length;i++) sum+=arr[i];	 The error is:
we have to initialize the variable sum	 int sum=0; for(int i=0;i<arr.length;i++) sum+=arr[i];
static int max(int[] arr){ int m=0; ... }	 The error is:
the array sign [] will be attached with variable arr, not with data type int	 static int max(int arr[]){ int m=0; ... }
switch(x){ case 1: System.out.println("One"); case 2: ... }	 The error is:
we have to use break statement after each output	 switch(x){ case 1: System.out.println("One");
      break;
case 2: ... }
Integer.parseInt(args[0]);	 Data-type is missing	Int a= Integer.parseInt(args[0]);
static void calc(int a,int b){ return a+b; }	 The error is:
in return type void we do not return anything	 static void calc(int a,int b){ System.out.println (a+b); }
return arr[arr.length];	 The error is:
Array index out of bound	 return arr[arr.length - 1];
static String day(int d){ switch(d){ case 1: return "Mon"; case 2: return "Tue"; default: "Invalid"; } }	The error is:
after every case we use break statement	static String day(int d){ switch(d){ case 1: return "Mon";
break; case 2: return "Tue";
break; default: "Invalid"; } }
static int add(int a,int b){ System.out.println(a+b); }	The error is:
in int data-type we return not directly print it	static int add(int a,int b){ return (a+b); }


