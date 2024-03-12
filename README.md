# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-

// Name - Palak Garg
// Class - BCA 4C
// Roll no - 2210997167
import java.util.Scanner;
public class Employee {
    private String nameOfEmp;
    private int empId;
    private double basicSalary;
    private double grossSalary;

    public Employee(String nameOfEmp, int empId, double basicSalary) {
        this.nameOfEmp = nameOfEmp;
        this.empId = empId;
        this.basicSalary = basicSalary;
        calculateSalary();
    }
    
    private void calculateSalary() {
        double hra = 0.25 * basicSalary;
        double da = 0.40 * basicSalary;
        grossSalary = basicSalary + hra + da;
    }

    public void displayDetails() {
        System.out.println("Name of Employee: " + nameOfEmp);
        System.out.println("Employee ID: " + empId);
        System.out.println("Gross Salary: " + grossSalary);
        System.out.println("-----------------------------");
    }

    public double getGrossSalary() {
        return grossSalary;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking user input for employee details
        System.out.print("Enter Name of Employee: ");
        String nameOfEmp = scanner.nextLine();

        System.out.print("Enter Employee ID: ");
        int empId = scanner.nextInt();
        System.out.print("Enter Basic Salary: ");
        double basicSalary = scanner.nextDouble();
        
        Employee employee = new Employee(nameOfEmp, empId, basicSalary);
        if (Character.isLetter(nameOfEmp.charAt(0)) && "aeiouAEIOU".indexOf(nameOfEmp.charAt(0)) == -1) {
            employee.displayDetails();
        }

        if (empId >= 101 && empId <= 150) {
            employee.displayDetails();
        }
        
        if (employee.getGrossSalary() < 35000) {
            System.out.println("Employee with Gross Salary less than 35000/-");
        }
        scanner.close();
    }
}
