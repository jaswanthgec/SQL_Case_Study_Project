# SQL_Case_Study_Project
SQL case study with an employee table and an example of creating some tables

Project Purpose:

The project's purpose is to create an Employee table so that the organization can have a clear idea about their employees, and we also create database schemas, i.e., we create 3 tables such as the employee table, the department table, and the grades of employees. 

In the employee table, there are basic details like ID, name, DOB, address, contact details, job title, etc.

In the Department table, there are details such as the particular employee in a particular department.

In the grades of employee table, there are details such as grades of employees so that the organization can have a clear idea of assigning employees to a specific department

Usage:

We can directly set up this code for creating a table, the organization can perform any type of operation on this table here we use insert and select commands. We can use commands like delete update set operations DDL, DML, DCL, TCL, etc.

# Employee table:

//creation of employee table:

CREATE TABLE employee (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(50),
    date_of_birth DATE,
    address VARCHAR(100),
    contact_number VARCHAR(15),
    hire_date DATE,
    job_title VARCHAR(50),
    salary DECIMAL(10, 2)
);

//inserting some rows into the employee table:

INSERT INTO employee (employee_id, employee_name, date_of_birth, address, contact_number, hire_date, job_title, salary)
VALUES
    (1, 'John Smith', '1985-04-15', '123 Main Street, Cityville, USA', '+1 (555) 123-4567', '2010-09-01', 'Software Engineer', 75000.00),
    
    (2, 'Jane Doe', '1990-11-10', '456 Park Avenue, Townsville, USA', '+1 (555) 987-6543', '2015-03-15', 'Marketing Manager', 85000.00),
    
    (3, 'Michael Johnson', '1988-08-22', '789 Oak Road, Villageland, USA', '+1 (555) 222-3333', '2012-06-30', 'Sales Representative', 60000.00),
    
    (4, 'Emily Williams', '1992-02-28', '246 Elm Street, Hamletown, USA', '+1 (555) 444-5555', '2018-11-20', 'Human Resources Specialist', 70000.00),
    
    (5, 'Robert Lee', '1980-12-05', '135 Pine Avenue, Forestville, USA', '+1 (555) 777-8888', '2005-01-10', 'Project Manager', 90000.00);

// retrieving information from employee table

select * from employee

# Department table

//creation of department table:

CREATE TABLE department (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(50),
    department_manager_id INT,
    manager_name VARCHAR(50),
    manager_salary DECIMAL(10, 2),
    FOREIGN KEY (department_manager_id) REFERENCES employee (employee_id)
);

//inserting some rows into the department table:

INSERT INTO department (department_id, department_name,department_manager_id, manager_name, manager_salary) VALUES

    (1, 'Marketing', 2, 'Jane Doe', 85000.00),
    
    (2, 'Sales', 3, 'Michael Johnson', 60000.00),
    
    (3, 'Human Resources', 4, 'Emily Williams', 70000.00),
    
    (4, 'Engineering', 1, 'John Smith', 75000.00),
    
    (5, 'Finance', 5, 'Robert Lee', 90000.00);

//retrieving information from the department table

select * from department;

# Grades of employee table

//creation of grades of employee table:

CREATE TABLE grades_of_employee (
    grade_id INT PRIMARY KEY,
    employee_id INT,
    grade VARCHAR(5),
    FOREIGN KEY (employee_id) REFERENCES employee (employee_id)
);

//inserting some rows into the grades of the employee table:

INSERT INTO grades_of_employee (grade_id, employee_id, grade)
VALUES
    (1, 1, 'A'),
    
    (2, 2, 'B'),
    
    (3, 3, 'C'),
    
    (4, 4, 'B+'),
    
    (5, 5, 'A-');

// retrieving information from grades of employee table

select * from grades_of_employee;

