 PREM VISHAL



 Objects, Instance Methods & Encapsulation (Java)
Objectives
1.	Understand the  
2.	Define classes with instance variables
3.	Create and use objects in Java
4.	Call non-static methods using objects
5.	Understand reference variables and object aliasing
6.	Use constructors to initialize objects
7.	Apply basic encapsulation using private
8.	Implement getters and setters
9.	Use the this keyword correctly
Prerequisite
Students should have completed Lab–2 and must be familiar with static methods, control statements, arrays, and basic Java syntax.
1. Transition from Static to Object-Oriented Programming
Static methods belong to the class, whereas non-static methods belong to objects. Object-oriented programming focuses on methods operating on object data.
Example
// Static
static int add(int a, int b) { return a + b; }

// Non-static
int add(int a, int b) { return a + b; }
2. Class and Object Basics
A class is a blueprint, and an object is an instance created from that class.
Example
class Student {
    String name;
    int age;
}

Student s1 = new Student();
3. Instance Variables vs Local Variables
Instance variables belong to objects, while local variables exist only within methods.
Example
class Student {
    String name;
    void show() {
        int x = 10;
    }
}
4. Object Creation and Method Calling
Non-static members are accessed using objects and the dot operator.
Example
Student s1 = new Student();
s1.name = "Ali";
s1.age = 20;
s1.display();
5. Reference Variables and Object Aliasing
Multiple references can point to the same object.
Example
Student s1 = new Student();
Student s2 = s1;
s1.name = "Ali";
System.out.println(s2.name);
6. Constructors
Constructors initialize objects and are called automatically.
Example
class Student {
    String name;
    int age;
    Student(String n, int a) {
        name = n;
        age = a;
    }
}
7. Encapsulation
Encapsulation hides data using private and provides controlled access.
Example
class Student {
    private int age;
}
8. Getters and Setters
Getters and setters access private data safely.
Example
class Student {
    private int age;
    void setAge(int a) { age = a; }
    int getAge() { return age; }
}
9. this Keyword
this refers to the current object and resolves naming conflicts.
Example
class Student {
    private int age;
    void setAge(int age) {
        this.age = age;
    }
}
 
Practice Tasks
Instructions:
• All methods must be non-static (except main).
• Use private data members wherever applicable.
• Access data using constructors, getters, and setters.
• Do not write logic directly inside main.

Task 1: Student Profile Management
Create a class named Student with the following private fields:
• id (int)
• name (String)
• age (int)
• cgpa (double)

Requirements:
1. Create setters and getters for all fields.
2. Validate age (15–60) and cgpa (0.0–4.0).
3. If invalid data is provided, do not update the value and display a message.
4. Create an instance method display() to print complete student information.

In main:
• Create two Student objects.
• Set values using setters and display both objects.

CODE:

 class Student{
	private int id;
	private String name;
	private int age;
	private double cgpa;
	public void setId(int id){
		this.id=id;
	}
	public int getId(){
		return id;
	}
	public void setName(String name){
		this.name=name;
	}
	public String getName(){
		return name;
	}
	public void setAge(int age){
		if(age>=15 && age<=60){
			this.age=age;
		}else{
			System.out.println("Invalid age");
		}
	}
	public int getAge(){
		return age;
	}
	public void setCgpa(double cgpa){
		if(cgpa>=0.0 && cgpa<=4.0){
			this.cgpa=cgpa;
		}else{
			System.out.println("Invalid CGPA");
		}
	}
		public double getCgpa(){
			return cgpa;
		}
		public void display(){
			System.out.println("-----------------");
			System.out.println("Name is: " + name);
			System.out.println("Age is: " + age);
			System.out.println("CGPA is: " + cgpa);
			System.out.println("ID is: " + id);
		}
	}
		public class Profile{
	public static void main(String[] args){
		Student s1 = new Student();
		s1.setId(101);
		s1.setName("Vishal");
		s1.setAge(20);
		s1.setCgpa(3.50);
		Student s2 = new Student();
		s2.setId(103);
		s2.setName("Ehsan");
		s2.setAge(21);
		s2.setCgpa(3.55);
		s1.display();
		s2.display();
	}
}
 



Task 2: Bank Account System
Create a class named BankAccount with the following private fields:
• accountNumber (String)
• accountHolder (String)
• balance (double)

Requirements:
1. Use a parameterized constructor to initialize all fields.
2. Create methods deposit(amount) and withdraw(amount).
3. Deposit amount must be greater than 0.
4. Withdrawal amount must be greater than 0 and less than or equal to balance.
5. Create a method getBalance() that returns current balance.
6. Create a method printStatement() to display account details.

In main:
• Create one account object.
• Perform multiple deposits and withdrawals.
• Display account details after each operation.







CODE:

class BankAccount{
	private String accNum;
	private String accHolder;
	private double balance;
	BankAccount(String accNum, String accHolder, double balance){
		this.accNum = accNum;
		this.accHolder = accHolder;
		this.balance = balance;
	}
	public void deposit(double amount){ 
		if(amount > 0){
			balance+=amount;
			System.out.println("deposit is: "+ amount);
		}else{
			System.out.println("invalid amount");
		}
		statement();
	}
	public void withdraw(double amount){
				if(amount>0 && amount<=balance){
					balance -= amount;
			System.out.println("withdraw is:" + amount);
		}else{
			System.out.println("invalid amount");
		}
		statement();
	}
	public double getBalance(){
			return balance;
	}
	public void statement(){
		System.out.println("-----here starts again-----\n");
		System.out.println("Account Number is: " + accNum);
		System.out.println("Account Holder is: " + accHolder);
		System.out.println("Current balance is: " + balance );
	}
}
	public class OOP{
		public static void main(String[] args){
	BankAccount account = new BankAccount("10203040", "Vishal", 100000.22);
			account.deposit(8000);
			account.deposit(11500);
			account.withdraw(7500);
			account.withdraw(85000);
		}
	}



 

Task 3: Car Showroom Inventory
Create a class named Car with the following private fields:
• brand (String)
• model (String)
• year (int)
• price (double)

Requirements:
1. Create a parameterized constructor using the this keyword.
2. Create a display() method to print car details.
3. Create a getter for price only.

In main:
• Create three Car objects.
• Display all car details.
• Identify and display the most expensive car.
Task 4: Reference and Object Aliasing Demonstration
Create a class named Box with the following fields:
• length (double)
• width (double)

Requirements:
1. Create an instance method area() that returns the area.
2. In main:
   • Create one Box object and assign values.
   • Create another reference pointing to the same object.
   • Modify dimensions using the second reference.
   • Print area using both references.

Observation:
• Both references should reflect the same updated area.

CODE:
class Box{
	double length;
	double width;

	public double area(){
		return length*width;
	}
		Box(double length, double width){
		this.length = length;
		this.width = width;
	}
}
public class Dada{
	public static void main(String[] args){
		Box box1 = new Box(25.5, 12.5);
		Box	box2 = box1;

		box2.length = 30.5;
		box2.width = 15.5;
			System.out.println("\n");
		System.out.println("1st dimension is: " + box1.area());
		System.out.println("2nd dimension is: " + box2.area());	
			System.out.println("\n");
	}
}


 
Task 5: Employee Salary Calculator
Create a class named Employee with the following private fields:
• employeeId (int)
• name (String)
• basicSalary (double)

Requirements:
1. Create setters and getters with validation (basicSalary ≥ 30000).
2. Create methods:
   • hra() → returns 20% of basic salary
   • tax() → returns 5% of basic salary
   • netSalary() → returns basic + hra − tax
   • printSlip() → prints formatted salary slip

In main:
• Create two Employee objects.
• Display salary slips for both employees.

CODE:

class Employee{

	private int employeeID;
	private String name;
	private double basicSalary;

	 public void setID(int employeeID){
	 	this.employeeID = employeeID;
	 }
	 public int getID(){
	 	return employeeID;
	 }
	 public void setName(String name){
	 	this.name=name;
	 }
	 public String getName(){
	 	return name;
	 }
	 public void setPay(double basicSalary){
	 	if(basicSalary>=30000){
	 		this.basicSalary = basicSalary;
	 	}else{
	 	System.out.println("invalid basic salary");
	 	}
	 }
	 public double getPay(){
	 	return basicSalary;
	 }

	 public double hra(){
	 	return (0.20*basicSalary);
	 }
	 public double tax(){
	 	return (0.05*basicSalary);
	 }
	 public double netSalary(){
	 	return ( basicSalary+ hra() - tax() );
	 }
	 public void printSlip(){
	 	System.out.println("-------------");
	 	System.out.println("Employee ID is: "+ employeeID);
	 	System.out.println("Name is: "+ name);
	 	System.out.println("Basic Salary is: "+ basicSalary);
	 	System.out.printf("Basic HRA is: %.2f %n ", hra() );
	 	System.out.printf("tax is: %.2f %n " , tax() );
	 	System.out.printf("netSalary is: %.2f %n" , netSalary() );
	 }

}
		public class Salary{
	public static void main(String[] args){
		

		Employee person1 = new Employee();
		person1.setName("Prem Vishal");
		person1.setID(1203);
		person1.setPay(75000.25);


		Employee person2 = new Employee();
		person2.setName("M. Ehsan");
		person2.setID(1130);
		person2.setPay(85400.25);

		person1.printSlip();
		person1.hra();
		person1.tax();

		person2.printSlip();
		person2.hra();
		person2.tax();


		}
	}







 
