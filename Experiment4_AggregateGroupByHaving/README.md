# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
<img width="1029" height="578" alt="image" src="https://github.com/user-attachments/assets/9d9e6cf6-91a4-462c-87cb-fa1e9a223fcf" />


```sql
SELECT InsuranceCompany, COUNT(DISTINCT PatientID) AS TotalPatients
FROM Insurance
GROUP BY InsuranceCompany;

```

**Output:**

<img width="1276" height="705" alt="image" src="https://github.com/user-attachments/assets/36bc5d88-a901-4aa8-9e17-2f54103a763e" />


**Question 2**
<img width="1147" height="520" alt="image" src="https://github.com/user-attachments/assets/7774d3d6-75df-4578-b585-83e474114a6e" />


```sql
SELECT Frequency, COUNT(*) AS TotalPrescriptions
FROM Prescriptions
GROUP BY Frequency;

```

**Output:**

<img width="1278" height="574" alt="image" src="https://github.com/user-attachments/assets/a5228e71-c619-4a3a-a6bb-5ace8fff899b" />

**Question 3**
<img width="1116" height="449" alt="image" src="https://github.com/user-attachments/assets/668d1e14-840d-4c38-bd3d-6d73eea3ae76" />


```sql
SELECT STRFTIME('%Y-%m', date) AS Month,
       COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY Month
ORDER BY Month;

```

**Output:**

<img width="1276" height="485" alt="image" src="https://github.com/user-attachments/assets/2a66a18f-f396-47a7-a9b4-4313fd2d0362" />


**Question 4**
<img width="1146" height="474" alt="image" src="https://github.com/user-attachments/assets/749b7096-6ac9-46fc-af45-4e225f4dfe9c" />

```sql
SELECT MAX(purch_amt) AS MAXIMUM
FROM orders;
```

**Output:**

<img width="1276" height="370" alt="image" src="https://github.com/user-attachments/assets/be6cb9db-5895-4d7c-8022-92e3e0c77835" />


**Question 5**
<img width="979" height="429" alt="image" src="https://github.com/user-attachments/assets/4eb858c2-dabb-42b5-b021-d63240b5dcfc" />


```sql
SELECT name, email, LENGTH(email) AS min_email_length
FROM customer
WHERE LENGTH(email) = (
    SELECT MIN(LENGTH(email)) FROM customer
)
LIMIT 1;
```

**Output:**

<img width="1132" height="448" alt="image" src="https://github.com/user-attachments/assets/ae836104-16c7-411d-a5b9-8a351f05e91f" />


**Question 6**
<img width="1280" height="375" alt="image" src="https://github.com/user-attachments/assets/764484cb-4d48-4407-80ae-600baa1daa87" />


```sql
SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```

**Output:**

<img width="1271" height="371" alt="image" src="https://github.com/user-attachments/assets/d36eb60a-d246-4a25-9ddb-6fae46ffabce" />


**Question 7**
<img width="1052" height="467" alt="image" src="https://github.com/user-attachments/assets/5c6c8b75-1d6f-4b2f-b50a-f967fc9bd917" />


```sql
SELECT COUNT(DISTINCT customer_id) AS COUNT
FROM customer
WHERE grade IS NOT NULL;
```

**Output:**

<img width="1273" height="368" alt="image" src="https://github.com/user-attachments/assets/40bf8bc1-7409-4be4-b6a7-71a7ec7d136d" />


**Question 8**
<img width="1242" height="476" alt="image" src="https://github.com/user-attachments/assets/878daf14-394a-4841-be70-9707ab1e782f" />


```sql
SELECT occupation, AVG(workhour) 
FROM employee1
GROUP BY occupation
HAVING AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**
<img width="1278" height="432" alt="image" src="https://github.com/user-attachments/assets/0e1babfb-a629-4bbb-adee-54cb612ffad0" />

**Question 9**
<img width="1223" height="442" alt="image" src="https://github.com/user-attachments/assets/ef9913e3-448c-40ec-a23e-a9679ea16d87" />

```sql
SELECT age, AVG(income)
FROM employee
GROUP BY age
HAVING AVG(income) BETWEEN 300000 AND 500000;
```

**Output:**
<img width="1270" height="390" alt="image" src="https://github.com/user-attachments/assets/7e70dd63-5025-44a3-a88e-193032cf8edc" />


**Question 10**
<img width="1209" height="482" alt="image" src="https://github.com/user-attachments/assets/93b0c9d6-18fe-4e2c-8214-43630c1ac070" />

```sql
SELECT city, AVG(income)
FROM employee
GROUP BY city
HAVING AVG(income) > 500000;
```

**Output:**
<img width="1277" height="472" alt="image" src="https://github.com/user-attachments/assets/3d87e69e-079d-4cd0-b637-a745377a65b7" />


## RESULT
<img width="1451" height="274" alt="image" src="https://github.com/user-attachments/assets/68664edd-6f9a-4762-9f03-0a2da12f87c1" />


Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
