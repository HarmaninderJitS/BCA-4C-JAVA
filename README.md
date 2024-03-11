# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-

Submitted By- Mehardeep kaur
Roll No. 2210997287

Solution:
package javafullcourse;
import java.util.Scanner;

public class Employee {
    private String nameOfEmp;
    private int empId;
    private double basicSalary;
    private double grossSalary;

    
    public Employee() {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Name of Employee: ");
        this.nameOfEmp = sc.nextLine();

        System.out.print("Enter Employee ID: ");
        this.empId = sc.nextInt();

        System.out.print("Enter Basic Salary: ");
        this.basicSalary = sc.nextDouble();

        
        double hra = 0.25 * basicSalary;
        double da = 0.40 * basicSalary;
        this.grossSalary = basicSalary + hra + da;
    }

    
    public void displayConsonantEmployees() {
        if (!nameOfEmp.isEmpty() && !isVowel(nameOfEmp.charAt(0))) {
            System.out.println("Name: " + nameOfEmp + ", Gross Salary: " + grossSalary);
        }
    }

    
    public void displayEmployeesInIdRange() {
        if (empId >= 101 && empId <= 150) {
            System.out.println("Employee ID: " + empId + ", Gross Salary: " + grossSalary);
        }
    }

    
    public static int countEmployeesWithSalaryLessThan(double limit, Employee[] employees) {
        int count = 0;
        for (Employee employee : employees) {
            if (employee != null && employee.grossSalary < limit) {
                count++;
            }
        }
        return count;
    }

    
    private boolean isVowel(char ch) {
        return "AEIOUaeiou".indexOf(ch) != -1;
    }

    public static void main(String[] args) {
        
        Employee[] employees = new Employee[3];

        
        for (int i = 0; i < employees.length; i++) {
            employees[i] = new Employee();
        }

       
        System.out.println("Employees whose name starts with a consonant:");
        for (Employee employee : employees) {
            if (employee != null) {
                employee.displayConsonantEmployees();
            }
        }

        
        System.out.println("\nEmployees with Emp-Id between 101 and 150:");
        for (Employee employee : employees) {
            if (employee != null) {
                employee.displayEmployeesInIdRange();
            }
        }

       
        double limit = 35000;
        int count = countEmployeesWithSalaryLessThan(limit, employees);
        System.out.println("\nTotal number of employees with Gross Salary less than " + limit + ": " + count);
    }
}
