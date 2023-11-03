# Ex. No: 6 PL/SQL program using Triggers 
### DATE: 
### AIM: To create PL/SQL program to display new and old salary of customer when before/ after updation takes place. 

### Steps:
1. Create a trigger for each row when updation occurs.
2. Declare the variable in Declare section.
3. Start the begin section.
4. Calculate the salary changes.
5. Display the result 
6. End the begin section.

### Program:
```
DEVELOPED BY:LOKESH N
REG.NO:212222100023
```
## Create employee table:
```python
create table EMPLOYEE1(empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
```
## Insert values into employee table:
```python
insert into EMPLOYEE1(empid,empname,dept,salary) values(1,'Chandru','HR',2500000);
insert into EMPLOYEE1(empid,empname,dept,salary) values(2,'Chethan','MD',950000);
insert into EMPLOYEE1(empid,empname,dept,salary) values(3,'Dileep','HR',800000);
```
## Create salary_log table:
```python
create table salary_log (log_id NUMBER , empid NUMBER,empname VARCHAR(10),old_salary NUMBER,new_salary NUMBER,update_date DATE);
```
## PL/SQL Trigger code
```python
create or replace trigger log_salary_update
       before update on EMPLOYEE1
       for each row
       declare
       v_old_salary number;
       v_new_salary number;
       begin
       v_old_salary := :OLD.salary;
       v_new_salary := :NEW.salary;
       if v_old_salary <> v_new_salary then
       insert into salary_log(empid,empname,old_salary,new_salary,update_date)values(:OLD.empid,:OLD.empname,v_old_salary,v_new_salary,SYSDATE);
       end if;
       end;
       /
```
## Update the salary of an employee:
```python
update EMPLOYEE1 set salary = 97000 where empid = 2;
```
## Display the salary_log table:
```python
select * from salary_log;
```
### Output:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/e1d76ea8-74b3-47ad-8a9b-897c8cc251ec)

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/3619b17b-62d0-4a84-a0c1-07d0265d83f8)

### Result:
Thust the program was performed sucessfully.
