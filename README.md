# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-

//nikhil7157
package java_lab;

import java.util.Scanner;

class EmployeeDetails {
    private String nameOfEmp;
    private int empId;
    private double basicSalary;
    private double grossSalary;

    public EmployeeDetails(String nameOfEmp, int empId, double basicSalary) {
        this.nameOfEmp = nameOfEmp;
        this.empId = empId;
        this.basicSalary = basicSalary;
        calculateSalary();
    }

    public String getNameOfEmp() {
        return nameOfEmp;
    }

    public int getEmpId() {
        return empId;
    }

    public double getGrossSalary() {
        return grossSalary;
    }

    private void calculateSalary() {
        double HRA = 0.25 * basicSalary;
        double DA = 0.4 * basicSalary;
        grossSalary = basicSalary + HRA + DA;
    }

    public static boolean isConsonant(char ch) {
        ch = Character.toUpperCase(ch);
        return !(ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U');
    }
}

public class EMPLOYEE {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input size of array
        System.out.print("Enter size of array: ");
        int size = scanner.nextInt();

        // Create array of EmployeeDetails objects
        EmployeeDetails[] employees = new EmployeeDetails[size];

        // Input details for each employee
        for (int i = 0; i < size; i++) {
            System.out.println("Enter details for employee " + (i + 1) + ":");

            System.out.print("Enter NameOfEmp: ");
            String nameOfEmp = scanner.nextLine();

            System.out.print("Enter Emp-Id: ");
            int empId = scanner.nextInt();

            System.out.print("Enter BasicSalary: ");
            double basicSalary = scanner.nextDouble();

            // Create EmployeeDetails object using the constructor
            employees[i] = new EmployeeDetails(nameOfEmp, empId, basicSalary);
        }

        // Query a)
        for (EmployeeDetails employee : employees) {
            if (EmployeeDetails.isConsonant(employee.getNameOfEmp().charAt(0))) {
                System.out.println("NameOfEmp: " + employee.getNameOfEmp());
                System.out.println("GrossSalary: " + employee.getGrossSalary());
            }
        }

        // Query b)
        for (EmployeeDetails employee : employees) {
            if (employee.getEmpId() >= 101 && employee.getEmpId() <= 150) {
                System.out.println("Emp-Id: " + employee.getEmpId());
                System.out.println("GrossSalary: " + employee.getGrossSalary());
            }
        }

        // Query c)
        for (EmployeeDetails employee : employees) {
            if (employee.getGrossSalary() < 35000) {
                System.out.println("Employee with GrossSalary less than 35000");
            }
        }
    }
}
