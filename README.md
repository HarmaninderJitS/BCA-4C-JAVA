# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-
import java.util.Scanner;

                                     [A]
import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor
    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.40 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Getter methods
    public String getNameOfEmp() {
        return NameOfEmp;
    }

    public double getGrossSalary() {
        return GrossSalary;
    }

    // Method to check if a character is a consonant
    private boolean isConsonant(char c) {
        c = Character.toUpperCase(c);
        return !(c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U');
    }

    // Method to check if the name starts with a consonant
    public boolean startsWithConsonant() {
        return isConsonant(NameOfEmp.charAt(0));
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input for the number of employees
        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline character

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        // Taking input for each employee
        for (int i = 0; i < numEmployees; i++) {
            System.out.println("\nEnter details for Employee " + (i + 1) + ":");
            System.out.print("Name of Employee: ");
            String name = scanner.nextLine();
            System.out.print("Employee ID: ");
            int id = scanner.nextInt();
            System.out.print("Basic Salary: ");
            double basicSalary = scanner.nextDouble();
            scanner.nextLine(); // Consume newline character

            employees[i] = new EMPLOYEE(name, id, basicSalary);
        }

        // Displaying the NameOfEmp and GrossSalary of employees whose names start with a consonant
        System.out.println("\nEmployees whose names start with a consonant:");
        for (EMPLOYEE emp : employees) {
            if (emp.startsWithConsonant()) {
                System.out.println("Name: " + emp.getNameOfEmp() + ", Gross Salary: $" + emp.getGrossSalary());
            }
        }

        scanner.close();
    }
}
                                          [B]
                                          
import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor
    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.40 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Getter methods
    public int getEmpId() {
        return EmpId;
    }

    public double getGrossSalary() {
        return GrossSalary;
    }

    // Method to check if the EmpId is between 101 and 150
    public boolean isEmpIdInRange() {
        return EmpId >= 101 && EmpId <= 150;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input for the number of employees
        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline character

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        // Taking input for each employee
        for (int i = 0; i < numEmployees; i++) {
            System.out.println("\nEnter details for Employee " + (i + 1) + ":");
            System.out.print("Name of Employee: ");
            String name = scanner.nextLine();
            System.out.print("Employee ID: ");
            int id = scanner.nextInt();
            System.out.print("Basic Salary: ");
            double basicSalary = scanner.nextDouble();
            scanner.nextLine(); // Consume newline character

            employees[i] = new EMPLOYEE(name, id, basicSalary);
        }

        // Displaying the Emp-Id and GrossSalary of employees whose Emp-Id is between 101 and 150
        System.out.println("\nEmployees whose Emp-Id is between 101 and 150:");
        for (EMPLOYEE emp : employees) {
            if (emp.isEmpIdInRange()) {
                System.out.println("Emp-ID: " + emp.getEmpId() + ", Gross Salary: $" + emp.getGrossSalary());
            }
        }

        scanner.close();
    }
}
                                            [C]
 import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor
    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.40 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Getter method for GrossSalary
    public double getGrossSalary() {
        return GrossSalary;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input for the number of employees
        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline character

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        // Taking input for each employee
        for (int i = 0; i < numEmployees; i++) {
            System.out.println("\nEnter details for Employee " + (i + 1) + ":");
            System.out.print("Name of Employee: ");
            String name = scanner.nextLine();
            System.out.print("Employee ID: ");
            int id = scanner.nextInt();
            System.out.print("Basic Salary: ");
            double basicSalary = scanner.nextDouble();
            scanner.nextLine(); // Consume newline character

            employees[i] = new EMPLOYEE(name, id, basicSalary);
        }

        // Counting the total number of Employees whose GrossSalary is less than 35000
        int count = 0;
        for (EMPLOYEE emp : employees) {
            if (emp.getGrossSalary() < 35000) {
                count++;
            }
        }

        System.out.println("\nTotal number of Employees whose GrossSalary is less than 35000: " + count);

        scanner.close();
    }
}
                                           
