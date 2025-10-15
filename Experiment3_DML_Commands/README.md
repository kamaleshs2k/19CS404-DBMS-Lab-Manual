# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="1215" height="621" alt="image" src="https://github.com/user-attachments/assets/5139e98b-6c21-4006-8d3e-c36b07348605" />

**Program**
```sql
UPDATE purchases
set per_unit_price = 25,total_price = quantity*25 where purchase_date ='2022-08-15' and product_id=12;
```

**Output:**

<img width="1783" height="410" alt="image" src="https://github.com/user-attachments/assets/ede36e66-5a0a-48a5-9f5f-c64d2dffabab" />


**Question 2**
---
<img width="705" height="221" alt="image" src="https://github.com/user-attachments/assets/18268d12-fb33-47df-9b43-5cbd6fbc9de6" />

**Program**
```sql
UPDATE suppliers
set supplier_name='A1 Suppliers' where supplier_id=8;
```

**Output:**

<img width="1847" height="391" alt="image" src="https://github.com/user-attachments/assets/dc26397a-be6a-4571-8e4b-ecbe6394f367" />

**Question 3**
---
<img width="849" height="453" alt="image" src="https://github.com/user-attachments/assets/57caa6b0-4586-4dde-9bdd-71f57e5fd553" />

**Program**
```sql
UPDATE PRODUCTS
set sell_price=CAST(sell_price*1.1 as INT) where supplier_id=6;
```

**Output:**

<img width="1794" height="434" alt="image" src="https://github.com/user-attachments/assets/e0c5dd92-a4ac-497d-8db1-74bc8a600336" />

**Question 4**
---
<img width="1190" height="438" alt="image" src="https://github.com/user-attachments/assets/e52ce000-0dcd-4c8f-95d1-f4c2e2d2867f" />

**Program**
```sql
UPDATE Employees
SET email='not available',commission_pct=0.55 where department_id=110;
```

**Output:**
<img width="1865" height="480" alt="image" src="https://github.com/user-attachments/assets/b3916b49-8ab2-442d-9943-933d0db33d04" />


**Question 5**
---
<img width="1113" height="515" alt="image" src="https://github.com/user-attachments/assets/09ad0820-12b6-4420-8cbf-90a1bd4278cf" />

**Program**
```sql
UPDATE Suppliers
set address='58 Lakeview, Magnolia' where supplier_id=5;
```

**Output:**

<img width="1829" height="333" alt="image" src="https://github.com/user-attachments/assets/48627199-2dd5-40cc-a335-6228897832ad" />


**Question 6**
---
<img width="712" height="347" alt="image" src="https://github.com/user-attachments/assets/4e2d9788-57a5-4e35-b346-790a2c7ae7e4" />

**Program**
```sql
DELETE from Doctors
where doctor_id BETWEEN 2 and 4;

```

**Output:**

<img width="1037" height="650" alt="image" src="https://github.com/user-attachments/assets/2c5e4f2e-9464-4bae-a457-c8c635b45c08" />


**Question 7**
---
<img width="1099" height="317" alt="image" src="https://github.com/user-attachments/assets/7fb3af92-f5ce-41b5-9427-47153520faf0" />

**Program**
```sql
DELETE from Customer
where CUST_COUNTRY NOT IN('India','USA');
```

**Output:**

<img width="1918" height="390" alt="image" src="https://github.com/user-attachments/assets/c616b763-c745-4276-8eb0-8e8babc73de2" />


**Question 8**
---
<img width="1434" height="425" alt="image" src="https://github.com/user-attachments/assets/d126074a-75d5-4656-9664-526f649cb8d5" />

**Program**
```sql
DELETE from Customer
where GRADE=3 and CUST_NAME LIKE'%BBB%' and PAYMENT_AMT>2000;
```

**Output:**

<img width="1816" height="337" alt="image" src="https://github.com/user-attachments/assets/491e8268-b11b-4128-9dcd-63af1b4c06d2" />


**Question 9**
---
Write a SQL query to delete a specific doctor from Doctors table whose ID is 1.

Sample table: Doctors

attributes : doctor_id, first_name, last_name, specialization
**Program**
```sql
DELETE from Doctors
where doctor_id=1;
```

**Output:**

<img width="1654" height="446" alt="image" src="https://github.com/user-attachments/assets/13d08945-148d-4623-a0f8-f2814c78daba" />


**Question 10**
---
<img width="1164" height="834" alt="image" src="https://github.com/user-attachments/assets/a0064fed-cd6e-41d6-a6b4-95b56631f8ba" />

**Program**
```sql
DELETE from Surgeries
where surgery_id=3 or surgeon_id=4;
```

**Output:**

<img width="1153" height="862" alt="image" src="https://github.com/user-attachments/assets/e6049f32-90b8-4b75-b7df-123e336f86f9" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
