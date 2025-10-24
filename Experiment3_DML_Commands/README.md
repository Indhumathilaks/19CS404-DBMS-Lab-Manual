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

<img width="1236" height="635" alt="image" src="https://github.com/user-attachments/assets/b9390629-2349-4377-820c-a8cebc932cb6" />


```sql
UPDATE Employees
SET salary = salary * 2
WHERE department_id = 20
  AND job_id LIKE '%MAN';


```

**Output:**
<img width="1248" height="437" alt="image" src="https://github.com/user-attachments/assets/b00440b2-cf55-4d05-b03d-1d4d5a34141a" />


**Question 2**
<img width="1070" height="343" alt="image" src="https://github.com/user-attachments/assets/de8de15b-672b-4062-9fa6-70d95dd3a2d6" />


```sql
UPDATE suppliers
SET supplier_name = 'A1 Suppliers'
WHERE supplier_id = 8;


```

**Output:**
<img width="1231" height="479" alt="image" src="https://github.com/user-attachments/assets/65887dc2-b43d-4502-82af-70fc2cfa5ed0" />


**Question 3**

<img width="1228" height="643" alt="image" src="https://github.com/user-attachments/assets/248183cc-c853-4b65-8b6e-2a6fbcca5bb8" />


```sql
UPDATE Employees
SET salary = 8000
WHERE employee_id = 105
  AND salary < 5000;

```

**Output:**
<img width="1231" height="325" alt="image" src="https://github.com/user-attachments/assets/234ce54d-3766-481a-9529-fe336750a6cf" />


**Question 4**
<img width="1223" height="544" alt="image" src="https://github.com/user-attachments/assets/397a5a48-c55d-4696-a216-ac38e621c180" />


```sql
UPDATE products
SET sell_price = sell_price * 1.15
WHERE quantity < 50
  AND supplier_id = 10;

```

**Output:**
<img width="1229" height="583" alt="image" src="https://github.com/user-attachments/assets/23c2c4a0-9e89-492e-b983-5a4d00397b68" />

**Question 5**



```sql
UPDATE products
SET reorder_lvl = reorder_lvl * 0.7
WHERE product_name LIKE '%cream%'
  AND quantity > reorder_lvl;

```

**Output:**
<img width="1234" height="580" alt="image" src="https://github.com/user-attachments/assets/aeae80aa-3736-48fe-b9ff-e035d3886606" />


**Question 6**

<img width="1230" height="655" alt="image" src="https://github.com/user-attachments/assets/813cf253-8255-4d56-8b97-ab519b2da4ad" />


```sql
DELETE FROM customer
WHERE GRADE <> 3;
```

**Output:**
<img width="1033" height="604" alt="image" src="https://github.com/user-attachments/assets/58fcb10d-60f0-4fb0-a869-bb459929dcf3" />


**Question 7**

<img width="1240" height="638" alt="image" src="https://github.com/user-attachments/assets/25edc0dc-a3a8-4df2-a824-002b122e6397" />

```sql
DELETE FROM customer
WHERE CUST_NAME LIKE '%Holmes%';

```

**Output:**

<img width="1223" height="588" alt="image" src="https://github.com/user-attachments/assets/bd6c04bc-ac3b-4774-aa88-dff6ed47f0eb" />


**Question 8**
<img width="998" height="482" alt="image" src="https://github.com/user-attachments/assets/308e3479-588b-4384-955d-6e5090de4100" />

```sql
DELETE FROM surgeries
WHERE surgery_id = 3;

```

**Output:**
<img width="1232" height="461" alt="image" src="https://github.com/user-attachments/assets/bbc9f52e-341b-4d93-9355-38b952270311" />


**Question 9**
<img width="1249" height="504" alt="image" src="https://github.com/user-attachments/assets/8308f98f-2591-46e7-9039-ea391757dfda" />


```sql
DELETE FROM customer
WHERE (GRADE > 2 AND PAYMENT_AMT < (SELECT AVG(PAYMENT_AMT) FROM customer))
   OR OUTSTANDING_AMT > 8000;
```

**Output:**

<img width="1223" height="750" alt="image" src="https://github.com/user-attachments/assets/8e7d6877-aa62-43e9-8b6e-88855b3dadfd" />


**Question 10**
<img width="1095" height="473" alt="image" src="https://github.com/user-attachments/assets/6a237e20-5ac3-4825-b42d-4d99e4a730e8" />


```sql
DELETE FROM doctors
WHERE doctor_id BETWEEN 2 AND 4;
```

**Output:**
<img width="1235" height="908" alt="image" src="https://github.com/user-attachments/assets/3c88396f-4a2c-445e-8b87-d817d5b93014" />


## RESULT
<img width="1432" height="304" alt="image" src="https://github.com/user-attachments/assets/fca6785d-4972-49c0-953b-10f85ab17674" />

Thus, the SQL queries to implement DML commands have been executed successfully.
