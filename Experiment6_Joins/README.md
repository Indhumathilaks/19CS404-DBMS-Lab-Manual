# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
<img width="1271" height="702" alt="image" src="https://github.com/user-attachments/assets/fe418726-a89e-494c-a97f-faea612a0c85" />


```sql
select p.first_name as patient_name from patients as p
inner join doctors as d on p.doctor_id = d.doctor_id
where d.first_name = 'Emily' and d.last_name = 'Johnson' and p.discharge_date is not null;
```

**Output:**

<img width="842" height="470" alt="image" src="https://github.com/user-attachments/assets/3c559515-34c1-4918-a55b-91e9ffd9206b" />


**Question 2**
<img width="1255" height="389" alt="image" src="https://github.com/user-attachments/assets/ff23e20c-6a75-4dd3-9cc4-38c1432b9de9" />


```sql
select c.customer_id,c.cust_name,c.city,c.grade,c.salesman_id from customer c
left join orders o on c.customer_id = o.customer_id
where o.ord_date between '2012-07-01' and '2012-07-30';
```

**Output:**

<img width="1259" height="486" alt="image" src="https://github.com/user-attachments/assets/59c81d93-a794-45b6-84bf-61b8195932cc" />


**Question 3**
<img width="1116" height="889" alt="image" src="https://github.com/user-attachments/assets/b28e59ba-dc08-474d-a2fe-8109d2728ad3" />


```sql
select s.name as Salesman,c.cust_name,c.city from salesman s join customer c on s.city=c.city
```

**Output:**
<img width="1067" height="771" alt="image" src="https://github.com/user-attachments/assets/8d2a8fbc-b92d-435b-bbc2-0913e9f705f3" />

**Question 4**
<img width="1239" height="458" alt="image" src="https://github.com/user-attachments/assets/60234f07-41a0-4d43-8af9-bed29f1b096f" />

```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1267" height="785" alt="image" src="https://github.com/user-attachments/assets/bfd866f6-6955-44a2-990c-b4946f52900d" />

**Question 5**
<img width="1150" height="347" alt="image" src="https://github.com/user-attachments/assets/ca238c83-d6ea-4bdb-9242-d2cbda2807b6" />


```sql
SELECT c.* FROM customer c
LEFT JOIN salesman s 
ON c.salesman_id = s.salesman_id
WHERE s.name = 'Mc Lyon';
```

**Output:**

<img width="1266" height="488" alt="image" src="https://github.com/user-attachments/assets/28a3465e-6eaa-4d53-8558-2b732b21f6d7" />

**Question 6**
<img width="1251" height="756" alt="image" src="https://github.com/user-attachments/assets/838dbc61-8171-43b6-b478-413276541191" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o 
ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;
```

**Output:**
<img width="1261" height="785" alt="image" src="https://github.com/user-attachments/assets/28f74cb1-96f3-4b59-a134-7133f6c40e9f" />

**Question 7**
<img width="1250" height="775" alt="image" src="https://github.com/user-attachments/assets/31480884-5145-4ee3-ab79-7258356c1678" />


```sql
SELECT p.first_name,s.* FROM patients p
INNER JOIN surgeries s 
ON p.patient_id = s.patient_id
WHERE p.first_name = 'Alice';
```

**Output:**
<img width="1257" height="489" alt="image" src="https://github.com/user-attachments/assets/854c4f01-48d6-410d-bae2-ac75a55b5c6c" />

**Question 8**
<img width="1235" height="780" alt="image" src="https://github.com/user-attachments/assets/57baa790-b2c9-41fa-91d8-3bafd1e409c5" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount",
    s.name,
    s.commission
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
LEFT JOIN salesman s ON c.salesman_id = s.salesman_id;
```

**Output:**

<img width="1254" height="786" alt="image" src="https://github.com/user-attachments/assets/05a32c55-cc6d-4282-80ed-4ad7da5c2389" />


**Question 9**
<img width="1254" height="781" alt="image" src="https://github.com/user-attachments/assets/27f5678e-a670-41db-a5dd-2b50dbea3d4e" />

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    c.cust_name,
    c.city
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**
<img width="1269" height="565" alt="image" src="https://github.com/user-attachments/assets/17d14646-d00e-40d4-9fcc-bbeeb4d9573e" />

**Question 10**
<img width="1256" height="754" alt="image" src="https://github.com/user-attachments/assets/226642c3-abb3-46c2-a65b-c81c4aa5e23d" />

```sql
SELECT n.*, d.department_name
FROM nurses n INNER JOIN departments d
ON n.department_id = d.department_id;
```

**Output:**
<img width="1259" height="639" alt="image" src="https://github.com/user-attachments/assets/f4d2dad4-adc3-4874-9562-7386b527ee46" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
