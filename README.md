# BCA-4C-JAVA
 //Name = Himanshu Kumar 
 // Roll NO = 2210997098

 package him;
import java.util.ArrayList;
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
        calculateGrossSalary();
    }

    public String getNameOfEmp() {
        return nameOfEmp;
    }

    public int getEmpId() {
        return empId;
    }

    public double getBasicSalary() {
        return basicSalary;
    }

    public double getGrossSalary() {
        return grossSalary;
    }

    private void calculateGrossSalary() {
        double hra = 0.25 * basicSalary;
        double da = 0.40 * basicSalary;
        grossSalary = basicSalary + hra + da;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Employee> employees = new ArrayList<>();

        System.out.println("Enter the number of employees: ");
        int n = scanner.nextInt();
        scanner.nextLine();

        for (int i = 0; i < n; i++) {
            System.out.println("Enter the name of employee " + (i + 1) + ": ");
            String nameOfEmp = scanner.nextLine();

            System.out.println("Enter the employee id of employee " + (i + 1) + ": ");
            int empId = scanner.nextInt();
            scanner.nextLine();

            System.out.println("Enter the basic salary of employee " + (i + 1) + ": ");
            double basicSalary = scanner.nextDouble();

            Employee employee = new Employee(nameOfEmp, empId, basicSalary);
            employees.add(employee);
        }

        System.out.println("\nEmployees whose name starts with a consonant: ");
        for (Employee employee : employees) {
            if (Character.isLetter(employee.getNameOfEmp().charAt(0)) && !Character.isLowerCase(employee.getNameOfEmp().charAt(0))) {
                System.out.println("Name: " + employee.getNameOfEmp() + ", Gross Salary: " + employee.getGrossSalary());
            }
        }

        System.out.println("\nEmployees whose employee id is between 101 and 150: ");
        for (Employee employee : employees) {
            if (employee.getEmpId() >= 101 && employee.getEmpId() <= 150) {
                System.out.println("Employee Id: " + employee.getEmpId() + ", Gross Salary: " + employee.getGrossSalary());
            }
        }

        int count = 0;
        for (Employee employee : employees) {
            if (employee.getGrossSalary() < 35000) {
                count++;
            }
        }

        System.out.println("\nTotal number of employees whose gross salary is less than 35000/-: " + count);
    }
}

