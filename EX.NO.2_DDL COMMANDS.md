# EXP NO 2: DATA DEFINITION LANGUGE COMMANDS 
### DATE
## AIM:
To create a student database and execute DDL queries using SQL.


## THEORY
### DDL (Data Definition Language)

* DDL or Data Definition Language actually consists of the SQL commands that can be used to define the database schema.
* It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database.
* DDL is a set of SQL commands used to create, modify, and delete database structures but not data.
* These commands are normally not used by a general user, who should be accessing the database via an application.

 
### List of DDL commands: 
1. CREATE: This command is used to create the database or its objects (like table, index, function, views, store procedure, and triggers).
2. DROP: This command is used to delete objects from the database.
3. ALTER: This is used to alter the structure of the database.
4. TRUNCATE: This is used to remove all records from a table, including all spaces allocated for the records are removed.
5. RENAME: This is used to rename an object existing in the database.

## Query:
### 1) Create a database studentdb

### SQL QUERY:
```
use STUDENT
```
### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/95bc23ab-1008-4958-b109-f0123c394b83)

### 2) Create a table student  and insert any two rows with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY: 
```python
create table STUDENT(S_Roll_no int,S_Name char(20),S_Age int,S_Address char(30),S_Phone_no int);
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/46f207aa-8303-471c-93a7-903f740d59ed)

### 3) Alter the above student table by adding another attribute department

### SQL QUERY: 
```python
alter table STUDENT add S_Dept char(10);
```
### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/babc4922-74ba-4c65-9bca-3e2b728f86a5)

### 4) Rename the student table to mystudent

### SQL QUERY: 
```python
rename table STUDENT to MYSTUDENT;
```


### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/c837c026-290e-4692-b174-5b02d9a31bc7)

### 5) Delete the mystudent rows using truncate keyword

### SQL QUERY: 
```python
 truncate table STUDENT;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/e415a7b1-b1a1-4e25-bb12-8834dd43ad32)

### 6) Drop the mystudent table
 
### SQL QUERY: 
```python
 drop table MYSTUDENT;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/34b12e6e-beed-458e-af6a-879b724ecf62)








## Result:

Thus the basic DDL commands in SQL are executed. 


