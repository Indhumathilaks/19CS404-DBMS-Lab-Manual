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

<img width="1029" height="578" alt="image" src="https://github.com/user-attachments/assets/720040ba-63ff-4c37-8e4f-104fb2f062af" />


```sql
SELECT InsuranceCompany, COUNT(DISTINCT PatientID) AS TotalPatients
FROM Insurance
GROUP BY InsuranceCompany;

```

**Output:**
<img width="1276" height="705" alt="image" src="https://github.com/user-attachments/assets/e51143a3-41e0-4d3e-a519-7f167cda8134" />


**Question 2**
<img width="1147" height="520" alt="image" src="https://github.com/user-attachments/assets/7523dc4f-cd87-4c9a-a86a-f8c8c1ed6397" />


```sql
SELECT Frequency, COUNT(*) AS TotalPrescriptions
FROM Prescriptions
GROUP BY Frequency;

```

**Output:**
<img width="1278" height="574" alt="image" src="https://github.com/user-attachments/assets/d4378f0c-4e2e-44ea-a829-6d9d296a1b89" />


**Question 3**

<img width="1116" height="449" alt="image" src="https://github.com/user-attachments/assets/14053995-28c9-4c3d-833e-e8a62d4d8a95" />


```sql
SELECT STRFTIME('%Y-%m', date) AS Month,
       COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY Month
ORDER BY Month;

```

**Output:**
<img width="1276" height="485" alt="image" src="https://github.com/user-attachments/assets/40377843-8f5e-4912-bc5f-45b07d465f29" />


**Question 4**
<img width="1146" height="474" alt="image" src="https://github.com/user-attachments/assets/332c9eca-0e06-4125-94bf-0d00d8e5d33c" />


```sql
SELECT MAX(purch_amt) AS MAXIMUM
FROM orders;
```

**Output:**

<img width="1276" height="370" alt="image" src="https://github.com/user-attachments/assets/82193371-b5c5-4e8a-9d5c-3bfabda3adf2" />


**Question 5**

<img width="979" height="429" alt="image" src="https://github.com/user-attachments/assets/35d89c4b-1cce-40ca-a765-d7652ea894d2" />


```sql
SELECT name, email, LENGTH(email) AS min_email_length
FROM customer
WHERE LENGTH(email) = (
    SELECT MIN(LENGTH(email)) FROM customer
)
LIMIT 1;
```

**Output:**
<img width="1280" height="375" alt="image" src="https://github.com/user-attachments/assets/8ca03c55-2ca1-4ea3-9806-13d48770de7d" />


**Question 6**

<img width="1132" height="448" alt="image" src="https://github.com/user-attachments/assets/bd8ff7be-b44f-4ab6-929f-b6e0f1ce29bc" />


```sql
SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```

**Output:**

<img width="1271" height="371" alt="image" src="https://github.com/user-attachments/assets/54505496-2352-42f3-93dd-603daa7d038c" />


**Question 7**

<img width="1052" height="467" alt="image" src="https://github.com/user-attachments/assets/31f4c39b-fad3-4235-a1a8-52f691ab0307" />


```sql
SELECT COUNT(DISTINCT customer_id) AS COUNT
FROM customer
WHERE grade IS NOT NULL;
```

**Output:**

<img width="1273" height="368" alt="image" src="https://github.com/user-attachments/assets/e6b37361-e8cd-4d13-834e-b0aeb46ed363" />


**Question 8**

<img width="1242" height="476" alt="image" src="https://github.com/user-attachments/assets/f79cae50-7c36-4330-b165-0b1ad93bfe7e" />


```sql
SELECT occupation, AVG(workhour) 
FROM employee1
GROUP BY occupation
HAVING AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**

<img width="1278" height="432" alt="image" src="https://github.com/user-attachments/assets/5d91f32b-60dd-47c2-bc54-ef61b3051628" />


**Question 9**
<img width="1223" height="442" alt="image" src="https://github.com/user-attachments/assets/2f2ec904-ac66-4eae-acde-c1ab20fe2c77" />


```sql
SELECT age, AVG(income)
FROM employee
GROUP BY age
HAVING AVG(income) BETWEEN 300000 AND 500000;
```

**Output:**

<img width="1270" height="390" alt="image" src="https://github.com/user-attachments/assets/0e990716-fca8-4ea3-81e6-1d003cfc94e7" />


**Question 10**
<img width="1209" height="482" alt="image" src="https://github.com/user-attachments/assets/44b7cf50-5b10-4b28-abdf-1d782d039d86" />


```sql
SELECT city, AVG(income)
FROM employee
GROUP BY city
HAVING AVG(income) > 500000;
```

**Output:**
<img width="1277" height="472" alt="image" src="https://github.com/user-attachments/assets/f3aadcd9-9134-4503-a8b5-98b04b82b9f2" />


## RESULT
<img width="1451" height="274" alt="image" src="https://github.com/user-attachments/assets/82033c57-4e3a-4c8c-9f70-8e5b1465650a" />

Thus, the SQL queries to implement DML commands have been executed successfully.
