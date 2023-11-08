# EXP NO 10: SYNONYMS AND ASSERTIONS IN SQL 
### DATE: 
## AIM:
To create a student database and create a synonym and assertions.

## THEORY
## SYNONYM
<div align="justify">
A SYNONYM provides another name for database object, referred to as original object, that may exist on a local or another server.
</div>
## ASSERTIONS
<div align="justify">
* An assertion is a piece of SQL which makes sure a condition is satisfied, else or it stops the action being taken on a database.
* An assertion is a constraint that might be dependent upon multiple rows of multiple tables.
</div>

### DEVELOPED BY:LOKESH N
### REG.NO:212222100023

## Query:
### 1) Create a table EMPLOYEE and perform insertion of two rows.

### SQL QUERY: 
```python
 CREATE TABLE EMPLOYEE (EmployeeID NUMBER,FirstName VARCHAR2(50),LastName VARCHAR2(50),Salary NUMBER);
```
```python
INSERT INTO EMPLOYEE (EmployeeID, FirstName, LastName, Salary)VALUES (1, 'leo', 'Doe', 50000);
INSERT INTO EMPLOYEE (EmployeeID, FirstName, LastName, Salary)VALUES (2, 'chandru', 'Smith', 60000);
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/4e864e6e-a488-4c9c-8fe8-6a05157b1cfc)

### 2) Create a synonym S1 for EMPLOYEE  table.

### SQL QUERY: 
```python
 CREATE SYNONYM S1 FOR EMPLOYEE;
```
### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/19378afd-027b-4eac-b795-55d0c42cb086)


### 3) Display the EMPLOYEE  table using synonym S1.
 
### SQL QUERY: 
```python
SELECT * FROM S1;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/281ed6c3-488a-4847-b2fd-a979a7abedad)

### 4) Drop the synonym.

### SQL QUERY: 
```python
DROP SYNONYM S1;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/81bbc8df-b707-4ea9-b19a-90791d39af0b)



### 5) Create a supplier table and create a sequence S2 for supplier table id.

### SQL QUERY: 
```python
CREATE TABLE Supplier (SupplierID NUMBER,SupplierName VARCHAR2(50));
CREATE SEQUENCE S2 START WITH 1  INCREMENT BY 1 NOCACHE NOCYCLE;
```

### OUTPUT:

![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/1a5437ee-4090-4a71-a8ad-dc2ec5e98ce5)

### 6) insert the data into supplier table use sequence.

### SQL QUERY: 
```python
INSERT INTO Supplier (SupplierID, SupplierName)VALUES (S2.NEXTVAL, 'ABC Supplier');
INSERT INTO Supplier (SupplierID, SupplierName)VALUES (S2.NEXTVAL, 'XYZ Supplier');
```
```
SELECT * FROM Supplier;
```
### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/74e5da24-d35f-4a09-9fd8-f9d95709ffb8)


### 7) Drop the sequence

### SQL QUERY: 
```python
DROP SEQUENCE S2;
```

### OUTPUT:
![image](https://github.com/lokeshnarayanan/DBMS/assets/119393019/086d9489-889b-4a44-850c-e2aa7581bfc5)

## RESULT :
 Thus the sequence and synonym created and used in SQL.
