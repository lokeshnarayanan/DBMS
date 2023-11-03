# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```python
UPDATE manager SET SALARY = SALARY + (SALARY *10/100);
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/754295b6-ad98-4fcf-aa8c-f99a80b14b35)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```python
delete from manager where salary<2750;
```
### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/ddad4138-3aab-4f71-9a45-e0bb95b5223f)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:

```python
select ename as "Name",salary*12 as "Annual Salary" from manager;
```
### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/82383b3c-3ab5-4859-adfe-368fbade92c6)

### Q4)	List the names of Clerks from emp table.


### QUERY:

```python
select ename from manager where designation='clerk';
```
### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/29cd7d9f-1ee1-441a-9c14-b5daaa912e8d)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```python
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/2d16de97-31f2-44e6-b6a4-f4829d7ffd38)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```python
select ename from manager where commission=0;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/50a42e7a-dc11-4fb6-8156-71948839276e)

### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```python
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/314ea096-7f78-445a-b866-8dcb1c11ffd8)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```python
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/82af27fe-2ebe-4850-b996-9a2c5f6145ea)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```python
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/1fcf5c01-2260-4329-bd0c-8d9a304a1032)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```python
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/08355707-1870-48d8-8ca0-7b9e1ee5676c)

### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```python
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/569217cb-4352-4c2e-b5f8-4d964761d5f3)

### Q12) Find number of rows in the table EMP

### QUERY:
```python
select count(*) from manager;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/df673376-db88-442c-a4d0-cf5a3839d090)

### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
```python
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/920b3078-8b80-4d74-9928-2fc575784354)


### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```python
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/34b5f805-e0dd-4a91-b19c-c28d2a4aa185)

## RESULT :
Thus the basic DML commands are executed.
