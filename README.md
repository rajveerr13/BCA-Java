1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-


import java.util.ArrayList;

public class Employee {
    private String name;
    private int eid;
    private double basicSalary;

    // Constructor
    public Employee(String name, int eid, double basicSalary) {
        this.name = name;
        this.eid = eid;
        this.basicSalary = basicSalary;
    }

    // Method to calculate gross salary
    public double calculateGrossSalary() {
        double hra = 0.20 * basicSalary;
        double da = 0.25 * basicSalary;
        double ma = 300;
        return basicSalary + hra + da + ma;
    }

    // Main method for testing
    public static void main(String[] args) {
        // Creating a list of employees
        System.out.println("Name:- Rajveer");
        System.out.println("Roll No:- 2210997188");
        ArrayList<Employee> employees = new ArrayList<>();
        employees.add(new Employee("Rajveer", 101, 25000));
        employees.add(new Employee("Vaibhav", 102, 18000));
        employees.add(new Employee("Nandini", 107, 22000));
        // a) Display the name and gross salary of an employee whose name starts with 'n'
        System.out.println("Employees whose name starts with 'n':");
        for (Employee emp : employees) {
            if (emp.name.toLowerCase().startsWith("n")) {
                System.out.println("Name: " + emp.name + ", Gross Salary: " + emp.calculateGrossSalary());
            }
        }

        // b) Display the Eid and gross salary whose Eid is equal to 107
        System.out.println("\nEmployee with Eid equal to 107:");
        for (Employee emp : employees) {
            if (emp.eid == 107) {
                System.out.println("Eid: " + emp.eid + ", Gross Salary: " + emp.calculateGrossSalary());
            }
        }

        // c) Count the total number of employees whose salary is more than 20000/-
        int count = 0;
        for (Employee emp : employees) {
            if (emp.basicSalary > 20000) {
                count++;
            }
        }
        System.out.println("\nTotal number of employees with salary more than 20000: " + count);
    }
}
