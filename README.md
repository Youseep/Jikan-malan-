// Company Jikan malan
class Company {
    constructor(name) {
        this.name = name;
        this.employees = [];
    }

    // Method to add an employee
    addEmployee(employee) {
        this.employees.push(employee);
    }

    // Method to calculate total expenses of the company
    calculateTotalExpenses() {
        let totalExpenses = 0;
        this.employees.forEach(employee => {
            totalExpenses += employee.calculateSalary();
        });
        return totalExpenses;
    }
}

// Employee class
class Employee {
    constructor(name, position, yearsOfExperience) {
        this.name = name;
        this.position = position;
        this.yearsOfExperience = yearsOfExperience;
    }

    // Method to calculate the salary of an employee
    calculateSalary() {
        let baseSalary = 50000;
        let experienceMultiplier = this.yearsOfExperience > 10 ? 1.5 : 1;
        return baseSalary * experienceMultiplier;
    }
}

// Usage example
let jikanMalan = new Company("Jikan malan");

let employee1 = new Employee("John Doe", "Software Engineer", 5);
let employee2 = new Employee("Jane Smith", "Project Manager", 8);

jikanMalan.addEmployee(employee1);
jikanMalan.addEmployee(employee2);

console.log(`Total expenses for Jikan malan: ${jikanMalan.calculateTotalExpenses()}`);
