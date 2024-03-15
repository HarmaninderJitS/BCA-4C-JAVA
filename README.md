# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-

import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.40 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    public String getNameOfEmp() {
        return NameOfEmp;
    }

    public double getGrossSalary() {
        return GrossSalary;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of employees:");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        for (int i = 0; i < numEmployees; i++) {
            System.out.println("Enter NameOfEmp for employee " + (i + 1) + ":");
            String name = scanner.nextLine();

            System.out.println("Enter EmpId for employee " + (i + 1) + ":");
            int id = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            System.out.println("Enter BasicSalary for employee " + (i + 1) + ":");
            double salary = scanner.nextDouble();
            scanner.nextLine(); // Consume newline

            employees[i] = new EMPLOYEE(name, id, salary);
        }

        System.out.println("Employees whose name starts with a consonant and their GrossSalary:");

        for (EMPLOYEE emp : employees) {
            if (isConsonant(emp.getNameOfEmp().charAt(0))) {
                System.out.println(emp.getNameOfEmp() + ": " + emp.getGrossSalary());
            }
        }
    }

    private static boolean isConsonant(char ch) {
        ch = Character.toUpperCase(ch);
        return !(ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U');
    }
}
import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.40 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    public int getEmpId() {
        return EmpId;
    }

    public double getGrossSalary() {
        return GrossSalary;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of employees:");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        for (int i = 0; i < numEmployees; i++) {
            System.out.println("Enter NameOfEmp for employee " + (i + 1) + ":");
            String name = scanner.nextLine();

            System.out.println("Enter EmpId for employee " + (i + 1) + ":");
            int id = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            System.out.println("Enter BasicSalary for employee " + (i + 1) + ":");
            double salary = scanner.nextDouble();
            scanner.nextLine(); // Consume newline

            employees[i] = new EMPLOYEE(name, id, salary);
        }

        System.out.println("Employees whose Emp-Id is between 101 and 150 and their GrossSalary:");

        for (EMPLOYEE emp : employees) {
            if (emp.getEmpId() >= 101 && emp.getEmpId() <= 150) {
                System.out.println("Emp-Id: " + emp.getEmpId() + ", GrossSalary: " + emp.getGrossSalary());
            }
        }
    }
}
import java.util.Scanner;

class EMPLOYEE {
    private String NameOfEmp;
    private int EmpId;
    private double BasicSalary;
    private double GrossSalary;

    public EMPLOYEE(String NameOfEmp, int EmpId, double BasicSalary) {
        this.NameOfEmp = NameOfEmp;
        this.EmpId = EmpId;
        this.BasicSalary = BasicSalary;
        calculateGrossSalary();
    }

    private void calculateGrossSalary() {
        double HRA = 0.25 * BasicSalary;
        double DA = 0.40 * BasicSalary;
        GrossSalary = BasicSalary + HRA + DA;
    }

    public double getGrossSalary() {
        return GrossSalary;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of employees: ");
        int numEmployees = scanner.nextInt();
        scanner.nextLine(); // Consume newline

        EMPLOYEE[] employees = new EMPLOYEE[numEmployees];

        for (int i = 0; i < numEmployees; i++) {
            System.out.println("Enter details for employee " + (i + 1) + ":");
            System.out.print("NameOfEmp: ");
            String name = scanner.nextLine();
            System.out.print("Emp-Id: ");
            int id = scanner.nextInt();
            System.out.print("BasicSalary: ");
            double salary = scanner.nextDouble();
            scanner.nextLine(); // Consume newline

            employees[i] = new EMPLOYEE(name, id, salary);
        }

        int count = 0;
        for (EMPLOYEE emp : employees) {
            if (emp.getGrossSalary() < 35000) {
                count++;
            }
        }

        System.out.println("Total number of employees whose GrossSalary is less than 35000/-: " + count);
    }
}
