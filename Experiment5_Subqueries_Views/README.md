# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
<img width="1243" height="819" alt="Screenshot 2025-10-31 104435" src="https://github.com/user-attachments/assets/321f81f5-9ba8-4058-930c-c8d8f259c32c" />


```sql
select ord_no, purch_amt, ord_date,salesman_id from orders where salesman_id in 
(SELECT salesman_id FROM salesman WHERE commission = (SELECT MAX(commission) FROM salesman));
```

**Output:**

<img width="1189" height="538" alt="image" src="https://github.com/user-attachments/assets/cfde83e5-4ddc-4782-9568-94b5bbc2af07" />


**Question 2**
<img width="1114" height="612" alt="image" src="https://github.com/user-attachments/assets/c2a03615-f744-4248-966f-7e244dd51640" />


```sql
select * from customers where age<30 and address="Delhi" order by id
```

**Output:**

<img width="1238" height="425" alt="image" src="https://github.com/user-attachments/assets/742af8bf-b48a-4a22-9698-eb8fb3078d9d" />


**Question 3**
<img width="1245" height="544" alt="image" src="https://github.com/user-attachments/assets/ceaf7466-25b9-48b6-9a76-3fcbe1f0eb48" />


```sql
select name,city from customer WHERE city IN ( SELECT city FROM customer WHERE id IN (3, 7));
```

**Output:**

<img width="867" height="519" alt="image" src="https://github.com/user-attachments/assets/21ec7a49-a29a-421a-a9b2-77f88339c2e2" />


**Question 4**
<img width="1203" height="530" alt="image" src="https://github.com/user-attachments/assets/34600da6-193c-480d-b4e6-d4ce6fe5aeb9" />

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s
ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**
<img width="1271" height="563" alt="image" src="https://github.com/user-attachments/assets/785ec199-3727-4a5e-a204-4c2483a73790" />


**Question 5**
<img width="1146" height="726" alt="image" src="https://github.com/user-attachments/assets/2aa1d87f-b3ef-42a8-885b-d946acd3cb96" />

```sql
SELECT * FROM customer WHERE customer_id = ((SELECT salesman_id FROM salesman WHERE name = 'Mc Lyon') - 2001);
```

**Output:**

<img width="1265" height="383" alt="image" src="https://github.com/user-attachments/assets/50191213-164a-423a-8ee6-0c1792b223e3" />


**Question 6**
<img width="1216" height="676" alt="image" src="https://github.com/user-attachments/assets/92fa208b-0fec-4e4f-9c7c-74eb27c76aee" />

```sql
select * from customers where salary<2500 order by id
```

**Output:**
<img width="1268" height="528" alt="image" src="https://github.com/user-attachments/assets/4c3cb54e-215a-4112-8882-fd713e9c5dfc" />

**Question 7**
<img width="1206" height="523" alt="image" src="https://github.com/user-attachments/assets/8bc4f009-1ac1-4215-bd1e-f03862aba0a0" />

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s
ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**

<img width="1278" height="526" alt="image" src="https://github.com/user-attachments/assets/cf308f84-c6e9-46c2-bbbf-de29ecc365f7" />


**Question 8**
<img width="1216" height="745" alt="image" src="https://github.com/user-attachments/assets/7cf7c79c-4ec8-452d-86ef-b47e6d99e652" />

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s
ON o.salesman_id = s.salesman_id
WHERE s.city = 'London';
```

**Output:**

<img width="1260" height="471" alt="image" src="https://github.com/user-attachments/assets/03e5f5a9-c95e-40e1-b9a7-f324f96d9504" />


**Question 9**
<img width="1046" height="547" alt="image" src="https://github.com/user-attachments/assets/c085b5ce-2764-4f66-96b7-7cda33691c22" />

```sql
select * from customer where city <> (select city from customer where id=(select max(id) from customer))
```

**Output:**

<img width="1262" height="561" alt="image" src="https://github.com/user-attachments/assets/730af208-e4f2-435a-84f1-5b7ec9cdef85" />


**Question 10**
<img width="1152" height="747" alt="image" src="https://github.com/user-attachments/assets/ab91ae8a-2a18-435e-8e2b-c61458ad7926" />


```sql
select * from customers where salary>1500 order by id
```

**Output:**

<img width="1260" height="672" alt="image" src="https://github.com/user-attachments/assets/ad1da3f9-9d52-44be-9a9d-80063bbc4d63" />


## RESULT

<img width="1468" height="402" alt="image" src="https://github.com/user-attachments/assets/bfd5e4c7-1805-4cbe-83d6-c1f54493ee5b" />


Thus, the SQL queries to implement subqueries and views have been executed successfully.
