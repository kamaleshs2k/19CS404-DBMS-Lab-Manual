# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
<img width="912" height="322" alt="image" src="https://github.com/user-attachments/assets/3dfe120e-62cc-4b27-8a5a-7c8277b7b1a6" />

```sql
CREATE TABLE Departments(DepartmentID INTEGER, DepartmentName TEXT);
```

**Output:**

<img width="1307" height="342" alt="image" src="https://github.com/user-attachments/assets/0882320e-f7b4-46be-9840-467e69b901de" />


**Question 2**
---
<img width="763" height="378" alt="image" src="https://github.com/user-attachments/assets/94562634-72a8-4bf1-bf3a-a49459aa8faa" />


```sql
INSERT into Books (ISBN, Title, Author)
VALUES ('978-6655443321','Big Data Analytics','Karen Adams');
```

**Output:**

<img width="1080" height="312" alt="image" src="https://github.com/user-attachments/assets/70ddf893-2855-4b22-a875-a5ab87aa521f" />


**Question 3**
---
<img width="620" height="287" alt="image" src="https://github.com/user-attachments/assets/ce563d09-27cb-41fe-9803-b0f08f9e155f" />


```sql
INSERT into Employee(EmployeeID, Name, Department, Salary ) select EmployeeID, Name, Department, Salary  from Former_employees  ;
```

**Output:**

<img width="1160" height="282" alt="image" src="https://github.com/user-attachments/assets/96c11b02-584b-4999-83a2-31c4e7d782dc" />

**Question 4**
---
<img width="1071" height="301" alt="image" src="https://github.com/user-attachments/assets/de472d98-b9a1-4cf5-a4eb-284467b8fe8a" />

```sql
ALTER TABLE Employees ADD COLUMN salary INTEGER CHECK(salary>0);
```

**Output:**

<img width="1327" height="305" alt="image" src="https://github.com/user-attachments/assets/2c32fcf0-0740-4d44-8a7e-57f6a7f0aa55" />

**Question 5**
---
<img width="1123" height="273" alt="image" src="https://github.com/user-attachments/assets/65ad3990-910f-4654-b30c-bbdd628e99a8" />

```sql
CREATE TABLE Department(DepartmentID INTEGER PRIMARY KEY, DepartmentName TEXT UNIQUE NOT NULL, Location TEXT);
```

**Output:**

<img width="1384" height="183" alt="image" src="https://github.com/user-attachments/assets/d67a0e4d-714d-4309-afef-8e4aae664081" />

**Question 6**
---
<img width="680" height="385" alt="image" src="https://github.com/user-attachments/assets/bdcde415-8647-4094-9606-e4189a2b7d54" />

```sql
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY) VALUES(1,'Ramesh',32,'Ahmedabad','2000');
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY) VALUES(2,'Khilan',25,'Delhi','1500'); 
INSERT INTO Customers(ID,NAME,AGE,ADDRESS,SALARY) VALUES(3,'Kaushik',23,'Kota','2000');
```

**Output:**

<img width="1121" height="280" alt="image" src="https://github.com/user-attachments/assets/e72f594c-d6ab-47e7-979b-1e10e50c7ccf" />

**Question 7**
---
<img width="1318" height="334" alt="image" src="https://github.com/user-attachments/assets/8cf9a2bb-2c18-4f0d-8dcb-1043c62d7198" />

```sql
CREATE TABLE Employees(EmployeeID INTEGER PRIMARY KEY,
FirstName TEXT NOT NULL,
LastName TEXT NOT NULL,
Email TEXT UNIQUE,
Salary INTEGER CHECK(Salary >0),
DepartmentID INTEGER,
FOREIGN KEY (DepartmentID)REFERENCES DepartmentS);
```

**Output:**

<img width="1341" height="349" alt="image" src="https://github.com/user-attachments/assets/a53aa065-a8bb-405c-9dab-684b1d8a4fb7" />

**Question 8**
---
<img width="863" height="399" alt="image" src="https://github.com/user-attachments/assets/621e6648-ac19-4d0a-b2f4-c304cc9dc0fa" />

```sql
ALTER TABLE customer ADD COLUMN discount DECIMAL(5,2);
```

**Output:**

<img width="1090" height="214" alt="image" src="https://github.com/user-attachments/assets/f217364c-7d99-4fe0-a327-fcddc6ec7e4e" />

**Question 9**
---
<img width="907" height="338" alt="image" src="https://github.com/user-attachments/assets/2c940697-8938-4609-af30-db47c8da3de3" />

```sql
CREATE TABLE products(
product_id INTEGER PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL(10,2) NOT NULL CHECK(list_price>=discount)CHECK(list_price>=0),
discount DECIMAL(10,2) DEFAULT'0' NOT NULL CHECK(discount >=0)
);
```

**Output:**

<img width="1065" height="184" alt="image" src="https://github.com/user-attachments/assets/030cf846-c433-4d8a-96e9-66af8cbd04de" />

**Question 10**
---
<img width="1463" height="665" alt="image" src="https://github.com/user-attachments/assets/c395c782-926a-4db1-90d5-4809bb5c962d" />

```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY(icom_id)REFERENCES company(com_id)
on update set null
on delete set null
);

```

**Output:**

<img width="1841" height="496" alt="image" src="https://github.com/user-attachments/assets/e5c87c0a-f45e-43c5-b01e-75d9d9692782" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
