Q1
```sql
CREATE TABLE Employees (
emp_id INT PRIMARY KEY,
emp_name VARCHAR(50),
manager_id INT,
department VARCHAR(50),
salary INT
);

INSERT INTO Employees VALUES (1,'Amit',NULL,'Management',120000);
INSERT INTO Employees VALUES (2,'Ravi',1,'Engineering',80000);
INSERT INTO Employees VALUES (3,'Neha',1,'Engineering',82000);
INSERT INTO Employees VALUES (4,'Karan',2,'Engineering',60000);
INSERT INTO Employees VALUES (5,'Simran',2,'Engineering',62000);
INSERT INTO Employees VALUES (6,'Pooja',3,'Engineering',61000);
INSERT INTO Employees VALUES (7,'Rahul',3,'Engineering',64000);
INSERT INTO Employees VALUES (8,'Arjun',1,'HR',70000);

SELECT 
e1.manager_id,
e1.emp_name AS employee_1,
e2.emp_name AS employee_2
FROM Employees e1
JOIN Employees e2
ON e1.manager_id = e2.manager_id
AND e1.emp_id < e2.emp_id
WHERE e1.manager_id IS NOT NULL;
```
OUTPUT 
<img width="438" height="201" alt="Screenshot 2026-03-10 at 11 46 53 AM" src="https://github.com/user-attachments/assets/9dfab9c7-820b-4b96-90e3-b1b8a02b12d0" />

Q2
```sql
SELECT MAX(Salary) AS Second_Highest_Salary
FROM Employees
WHERE Salary < (SELECT MAX(Salary) FROM Employees);
```
OUTPUT
<img width="384" height="158" alt="Screenshot 2026-03-10 at 12 02 27 PM" src="https://github.com/user-attachments/assets/a330aef5-bc90-43a4-946e-8d6be8ae9f38" />

