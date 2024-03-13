# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-

a)import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor to initialize data members
    public EMPLOYEE(String name, int id, double basicSalary) {
        NameOfEmp = name;
        EmpId = id;
        BasicSalary = basicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.4 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Getter method for NameOfEmp
    public String getNameOfEmp() {
        return NameOfEmp;
    }

    // Getter method for GrossSalary
    public double getGrossSalary() {
        return GrossSalary;
    }

    // Method to check if a character is a consonant
    private boolean isConsonant(char c) {
        c = Character.toLowerCase(c);
        return !(c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u');
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input data for employees
        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline character

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        for (int i = 0; i < numEmployees; i++) {
            System.out.println("\nEnter details for employee " + (i + 1) + ":");
            System.out.print("Name: ");
            String name = scanner.nextLine();
            System.out.print("Employee ID: ");
            int id = scanner.nextInt();
            System.out.print("Basic Salary: ");
            double basicSalary = scanner.nextDouble();
            scanner.nextLine(); // Consume newline character

            employees[i] = new EMPLOYEE(name, id, basicSalary);
        }

        // Display employees whose name starts with a consonant
        System.out.println("\nEmployees whose name starts with a consonant:");
        for (EMPLOYEE emp : employees) {
            if (emp.getNameOfEmp().length() > 0 && emp.isConsonant(emp.getNameOfEmp().charAt(0))) {
                System.out.println("Name: " + emp.getNameOfEmp() + ", Gross Salary: " + emp.getGrossSalary());
            }
        }
    }
}

b)import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor to initialize data members
    public EMPLOYEE(String name, int id, double basicSalary) {
        NameOfEmp = name;
        EmpId = id;
        BasicSalary = basicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.4 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Getter method for EmpId
    public int getEmpId() {
        return EmpId;
    }

    // Getter method for GrossSalary
    public double getGrossSalary() {
        return GrossSalary;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input data for employees
        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline character

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        for (int i = 0; i < numEmployees; i++) {
            System.out.println("\nEnter details for employee " + (i + 1) + ":");
            System.out.print("Name: ");
            String name = scanner.nextLine();
            System.out.print("Employee ID:

c)import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor to initialize data members
    public EMPLOYEE(String name, int id, double basicSalary) {
        NameOfEmp = name;
        EmpId = id;
        BasicSalary = basicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.4 * BasicSalary;
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

        // Input data for employees
        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline character

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        for (int i = 0; i < numEmployees; i++) {
            System.out.println("\nEnter details for employee " + (i + 1) + ":");
            System.out.print("Name: ");
            String name = scanner.nextLine();
            System.out.pr
