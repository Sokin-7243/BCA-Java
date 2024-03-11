1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-
ANS:-
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
    public double calculateHRA() {
        return 0.20 * basicSalary;
    }
    public double calculateDA() {
        return 0.25 * basicSalary;
    }
    public double calculateMA() {
        return 300;
    }
    public double calculateTotalSalary() {
        double hra = calculateHRA();
        double da = calculateDA();
        double ma = calculateMA();
        return basicSalary + hra + da + ma;
    }
    public boolean startsWithNameN() {
        return name.toLowerCase().startsWith("n");
    }
    public void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Gross Salary: " + calculateTotalSalary());
    }
    public boolean hasEid107() {
        return eid == 107;
    }
    public int getEid() {
        return eid;
    }
    public double getBasicSalary() {
        return basicSalary;
    }
    public static void main(String[] args) {
        Employee[] employees = {
            new Employee("John Doe", 101, 50000),
            new Employee("Nancy Smith", 107, 60000),
            new Employee("Emma Watson", 202, 25000)
            // Add more employees as needed
        };

        for (Employee emp : employees) {
            if (emp.startsWithNameN()) {
                emp.displayInfo();
            }
        }
        for (Employee emp : employees) {
            if (emp.hasEid107()) {
                System.out.println("Eid: " + emp.getEid());
                System.out.println("Gross Salary: " + emp.calculateTotalSalary());
            }
        }
        int count = 0;
        for (Employee emp : employees) {
            if (emp.getBasicSalary() > 20000) {
                count++;
            }
        }
        System.out.println("Total number of employees with salary more than 20000: " + count);
    }
}

