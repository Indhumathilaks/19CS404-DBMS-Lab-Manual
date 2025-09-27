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

<img width="1446" height="361" alt="image" src="https://github.com/user-attachments/assets/653c786f-c417-4781-9de3-ec4aec1d9e93" />


```sql
create table Orders (
OrderID INT PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID int,
FOREIGN KEY(CustomerID) REFERENCES Customers(CustomerID));
```

**Output:**

<img width="1302" height="372" alt="image" src="https://github.com/user-attachments/assets/1879f0dd-7dc0-4b7a-b6d1-9f9242e90fd2" />


**Question 2**

<img width="1140" height="254" alt="image" src="https://github.com/user-attachments/assets/b2d069f7-d7b4-4194-a848-9646c4525344" />


```sql
INSERT INTO Employee (EmployeeID,Name,Position,Department,Salary)
values(001,'Sarah Parker','Manager','HR','60000');
```

**Output:**

<img width="1295" height="323" alt="image" src="https://github.com/user-attachments/assets/3ab2c84e-852e-44bb-b977-952a7455bf58" />


**Question 3**

<img width="1057" height="565" alt="image" src="https://github.com/user-attachments/assets/8bfdb05e-9dd2-49ba-b5b5-d882e71a2404" />


```sql
ALTER TABLE Student_details ADD COLUMN Mobilenumber number;
```

**Output:**

<img width="1293" height="429" alt="image" src="https://github.com/user-attachments/assets/ac70101b-edf1-4b01-a06c-6e0646633e5c" />


**Question 4**

<img width="875" height="341" alt="image" src="https://github.com/user-attachments/assets/4dfcf3c9-a5ce-432e-9d47-e312604d851a" />


```sql
INSERT INTO Customers (CustomerID,Name,Address,Email) SELECT CustomerID,Name,Address,Email FROM Old_customers;
```

**Output:**

<img width="1276" height="358" alt="image" src="https://github.com/user-attachments/assets/ba9dcbbe-e340-473a-b039-a3d27d088fbf" />


**Question 5**

<img width="1282" height="413" alt="image" src="https://github.com/user-attachments/assets/d1e77f42-6282-41fa-a32a-35a10eb5da66" />

```sql
CREATE TABLE Bonuses(
BonusID INTEGER ,
EmployeeID INTEGER,
BonusAmount REAL CHECK(BonusAmount>0),
BonusDate DATE,
Reason TEXT NOT NULL);
```

**Output:**

<img width="1280" height="356" alt="image" src="https://github.com/user-attachments/assets/42fd9474-f38a-4499-9625-8aefd809121e" />

**Question 6**

<img width="1012" height="426" alt="image" src="https://github.com/user-attachments/assets/e800fe85-a503-431e-bb82-3aff13fbcb9c" />

```sql
CREATE TABLE Customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME);
```

**Output:**

<img width="1283" height="463" alt="image" src="https://github.com/user-attachments/assets/f652c477-fb59-4675-8fb6-bbbe5c378ece" />

**Question 7**

<img width="1234" height="469" alt="image" src="https://github.com/user-attachments/assets/2ebf4bcb-aab9-4b90-9066-2e9bcc6c5891" />


```sql
INSERT INTO Products (ProductID,Name,Category) values(106,'Fitness Tracker','Wearables');
INSERT INTO Products (ProductID,Name,Category,Price,Stock) values(107,'Laptop','Electronics',999.99,50);
INSERT INTO Products (ProductID,Name,Category,Stock) values(108,'Wireless Earbuds','Accessories',100);
```

**Output:**

<img width="1283" height="358" alt="image" src="https://github.com/user-attachments/assets/488dceca-7e44-4cd1-8565-23cb284bd299" />


**Question 8**

<img width="1114" height="536" alt="image" src="https://github.com/user-attachments/assets/cb298e66-bf80-41ce-85be-a413fb0109af" />


```sql
ALTER TABLE CUSTOMER RENAME CITY TO location;
```

**Output:**

<img width="1280" height="402" alt="image" src="https://github.com/user-attachments/assets/563b9456-cff5-4577-ad17-f1472e7c40e4" />


**Question 9**

<img width="1281" height="341" alt="image" src="https://github.com/user-attachments/assets/1b7275aa-3bfa-42eb-aa93-dfa18bf299e6" />


```sql
CREATE TABLE Department(
DepartmentID INTEGER PRIMARY KEY,
DepartmentName TEXT NOT NULL UNIQUE,
Location TEXT);
```

**Output:**

<img width="1278" height="357" alt="image" src="https://github.com/user-attachments/assets/c058ecce-6e87-4d4f-8c38-71b704c4e94f" />


**Question 10**

<img width="952" height="426" alt="image" src="https://github.com/user-attachments/assets/9b22b1e0-677b-4516-9943-d369d91f589f" />


```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY(icom_id) REFERENCES company(com_id) on update cascade on delete cascade);
```

**Output:**

<img width="1284" height="426" alt="image" src="https://github.com/user-attachments/assets/aef45e4d-af3c-48d0-81d6-015dc61c8e9e" />



## RESULT

<img width="1448" height="143" alt="image" src="https://github.com/user-attachments/assets/5f344b07-ea5a-42d1-842b-d468917cd3ea" />



Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
