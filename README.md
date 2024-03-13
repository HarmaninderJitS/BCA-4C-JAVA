# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-
a) import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor to initialize data members
    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.4 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Method to get NameOfEmp
    public String getNameOfEmp() {
        return NameOfEmp;
    }

    // Method to get GrossSalary
    public double getGrossSalary() {
        return GrossSalary;
    }

    // Method to check if a character is a consonant
    private boolean isConsonant(char c) {
        c = Character.toLowerCase(c);
        return !(c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u');
    }

    // Method to display NameOfEmp and GrossSalary of employees whose name starts with a consonant
    public void displayConsonantEmployees() {
        if (isConsonant(NameOfEmp.charAt(0))) {
            System.out.println("Name: " + NameOfEmp + ", Gross Salary: " + GrossSalary);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input employe



b)import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor to initialize data members
    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.4 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Method to get EmpId
    public int getEmpId() {
        return EmpId;
    }

    // Method to get GrossSalary
    public double getGrossSalary() {
        return GrossSalary;
    }

    // Method to display EmpId and GrossSalary of employees whose EmpId is between 101 and 150
    public void displayEmployeesWithEmpIdBetween101And150() {
        if (EmpId >= 101 && EmpId <= 150) {
            System.out.println("Emp-Id: " + EmpId + ", Gross Salary: " + GrossSalary);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input employee details
        System.out.print("Enter Name of Employee: ");
        String name = scanner.nextLine();
        System.out.print("Enter Employee ID: ");
        int id = scanner.nextInt();
        System.out.print("Enter Basic Salary: ");
        double basicSalary = scanner.nextDouble();

        // Create an EMPLOYEE object
        EMPLOYEE employee = new EMPLOYEE(name, id, basicSalary);

        // Display EmpId and GrossSalary of Employees whose EmpId is between 101 and 150
        employee.displayEmployeesWithEmpIdBetween101And150();
    }
}



c)import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    // Constructor to initialize data members
    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    // Method to calculate GrossSalary
    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.4 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    // Method to get GrossSalary
    public double getGrossSalary() {
        return GrossSalary;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input number of employees
        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline

        // Array to store employee objects
        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        // Input employee details
        for (int i = 0; i < numEmployees; i++) {
            System.out.println("\nEnter details for Employee " + (i + 1));
            System.out.print("Enter Name of Employee: ");
            String name = scanner.nextLine();
            System.out.print("Enter Employee ID: ");
            int id = scanner.nextInt();
            System.out.print("Enter Basic Salary: ");
            double basicSalary = scanner.nextDouble();

            // Create an EMPLOYEE object and store in the array
            employees[i] = new EMPLOYEE(name, id, basicSalary);

            // Consume newline
            scanner.nextLine();
        }

        // Count the total number of employees whose GrossSalary is less than 35000/-
        int count = 0;
        for (EMPLOYEE employee : employees) {
            if (employee.getGrossSalary() < 35000) {
                count++;
            }
        }

        System.out.println("\nTotal number of Employees whose GrossSalary is less than 35000/-: " + count);
    }
}
