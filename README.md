//Swati Thakur 2210997249
package first;
import java.util.Scanner;

public class linear {
    private String nameOfEmp;
    private int empId;
    private double basicSalary;
    private double grossSalary;
    public linear() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter Name of Employee: ");
        this.nameOfEmp = scanner.nextLine();

        System.out.print("Enter Employee ID: ");
        this.empId = scanner.nextInt();

        System.out.print("Enter Basic Salary: ");
        this.basicSalary = scanner.nextDouble();

        // Calculate HRA, DA, and GrossSalary
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
    public static int countEmployeesWithSalaryLessThan(double limit, linear[] employees) {
        int count = 0;
        for (linear employee : employees) {
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
        linear[] employees = new linear[3];
        for (int i = 0; i < employees.length; i++) {
            employees[i] = new linear();
        }
        System.out.println("Employees whose name starts with a consonant:");
        for (linear employee : employees) {
            if (employee != null) {
                employee.displayConsonantEmployees();
            }
        }
        System.out.println("\nEmployees with Emp-Id between 101 and 150:");
        for (linear employee : employees) {
            if (employee != null) {
                employee.displayEmployeesInIdRange();
            }
        }
        double limit = 35000;
        int count = countEmployeesWithSalaryLessThan(limit, employees);
        System.out.println("\nTotal number of employees with Gross Salary less than " + limit + ": " + count);
    }
}
