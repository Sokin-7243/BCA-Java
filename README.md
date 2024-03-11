public class Employee {
    String Name;
    int Eid;
    double Basic_Salary;

    public Employee(String Name, int Eid, double Basic_Salary) {
        this.Name = Name;
        this.Eid = Eid;
        this.Basic_Salary = Basic_Salary;
    }

    public double calculateHRA() {
        return 0.2 * Basic_Salary;
    }

    public double calculateDA() {
        return 0.25 * Basic_Salary;
    }

    public double calculateMA() {
        return 300;
    }

    public double calculateGrossSalary() {
        return Basic_Salary + calculateHRA() + calculateDA() + calculateMA();
    }

    public static void main(String[] args) {
        // Create Employee objects, calculate gross salary, and implement the queries here
        // Remember to use an ArrayList or any suitable data structure to store multiple employees
    }
}
