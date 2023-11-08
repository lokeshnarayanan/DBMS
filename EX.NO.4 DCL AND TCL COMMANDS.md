# EX.NO 4 Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL
### DATE:
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names


```
## DEVELOPED BY:LOKESH N
## REG.NO:212222100023
```
### Q1) Create a table employee with employee id ,name and Address

### QUERY:
```
create table employee(
emp_id numeric,
emp_name varchar(10),
addr varchar(40)
);
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/f2ca3ca2-3757-4bcd-9a56-3febfcc9e55a)

### Q2) Insert three rows into emploee table 


### QUERY:
```
INSERT INTO employee (employee_id, name, address)
VALUES (1, 'John Doe', '123 Main Street'),
       (2, 'Jane Doe', '456 Elm Street'),
       (3, 'Peter Parker', '789 Queens Boulevard');
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/b11d57df-9016-4bf7-ba4a-e295ca55be75)

### Q3) Start the transaction and create a save point s1.

### QUERY:
```
START TRANSACTION;
SAVEPOINT s1;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/92996d91-ebfc-49a8-9183-71e35bc7c0a0)

### Q4) Perform insertion into employee table.

### QUERY:
```
INSERT INTO employee (employee_id, name, address)
VALUES (4, 'Mary Jane Watson', '1011 Mockingbird Lane');
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/1ef3daa4-db44-42e3-ae75-fa8e2d8ba241)

### Q6)	Display the employee table and create a save point s2 .


### QUERY:
```
SELECT * FROM employee;
SAVEPOINT s2;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/4784e819-ffd7-439a-b6b6-c5c3c9e35682)


### Q7)	Perform updation on any one of the row.


### QUERY:
```
UPDATE employee SET name = 'Spider-Man' WHERE employee_id = 3;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/2dedd78e-12a5-4413-ac2f-79e51a49b37e)

### Q8) Display the employee table and rollback to  save point s2 


### QUERY:
```
SELECT * FROM employee;
ROLLBACK TO SAVEPOINT s2;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/0a45e0d8-79d0-46c1-8836-aaf5bd7adfef)

### Q9) Display the employee table and commit the changes; 


### QUERY:
```
SELECT * FROM employee;
COMMIT;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/e98d2366-0fe6-4c94-8eb9-f8f01c015a5e)

### Q10) Rollback to save point s1;


### QUERY:
```
ROLLBACK TO SAVEPOINT s1;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/6c114e2f-ffed-4939-bc76-dcb8aa24a1dc)

### Q11)	Create a new user and grant access to any one database with "insert and update"


### QUERY:
```
CREATE USER new_user;
GRANT INSERT, UPDATE ON database_name TO new_user;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/8a6a4395-1d97-4491-8f0a-e92137ffb435)

### Q12) Check the user access and display the result 


### QUERY:
```
SHOW GRANTS FOR new_user;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/9e1f1917-42b5-49c5-909d-898b1ff4b3cb)

### Q13) Revoke the privillages.

### QUERY:
```
SHOW GRANTS FOR new_user;
REVOKE INSERT, UPDATE ON database_name FROM new_user;
SHOW GRANTS FOR new_user;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/b9c711fd-f418-4259-a3de-c8925b31cb6c)


## RESULT :
Thus the basic TCL and DCL commands are executed.
