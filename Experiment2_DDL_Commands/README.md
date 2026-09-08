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
<img width="1072" height="462" alt="image" src="https://github.com/user-attachments/assets/cf0315b1-969b-49e0-8187-e93fd1c478f6" />


```sql
CREATE TABLE Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT);
```

**Output:**

<img width="1342" height="468" alt="image" src="https://github.com/user-attachments/assets/6139f6f8-1a1c-4c74-82cb-6b5e2d630cc4" />


**Question 2**
---
<img width="1240" height="383" alt="image" src="https://github.com/user-attachments/assets/7ffd1a4f-f282-463c-8d35-956f74152fd5" />


```sql
INSERT INTO Employee(EmployeeID,Name,Position)
VALUES(4,"Emily White","Analyst");
```

**Output:**

<img width="1213" height="300" alt="image" src="https://github.com/user-attachments/assets/7d32a8ec-304f-402b-b5a4-3ad70b7cac7e" />


**Question 3**
---
<img width="1233" height="378" alt="image" src="https://github.com/user-attachments/assets/3d7f334b-7658-4857-90ad-e49e01f3ee1e" />

```sql
CREATE TABLE Orders(
OrderID INTEGER PRIMARY KEY,
OrderDate Date NOT NULL,
CustomerID INTEGER REFERENCES Customers(CustomerID));
```

**Output:**

<img width="1237" height="367" alt="image" src="https://github.com/user-attachments/assets/12429ca7-2a62-4e2b-8d3d-ea4aff3a9ddf" />

**Question 4**
---
<img width="1218" height="442" alt="image" src="https://github.com/user-attachments/assets/d98c7335-e0c9-4bd7-8b45-85bf452103a1" />

```sql
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER REFERENCES Employees(EmployeeID),
BonusAmount REAL CHECK(BonusAmount>0),
BonusDate Date,
Reason TEXT NOT NULL);
```

**Output:**

<img width="1231" height="358" alt="image" src="https://github.com/user-attachments/assets/b5f6c48b-1dae-48ab-bcd0-84f1497ad382" />

**Question 5**
---
<img width="1205" height="391" alt="image" src="https://github.com/user-attachments/assets/92d345d0-d6ce-4f5e-acb6-2dd3dd29b6cc" />

```sql
ALTER TABLE Student_details ADD COLUMN MobileNumber NUMBER;
ALTER TABLE Student_details ADD COLUMN Address VARCHAR(100);
```

**Output:**

<img width="1238" height="405" alt="image" src="https://github.com/user-attachments/assets/4776f912-3cc9-4e35-89c6-09e691fad80b" />

**Question 6**
---
<img width="1066" height="606" alt="image" src="https://github.com/user-attachments/assets/db8f3068-07a4-4097-ae66-8d189bb1e920" />

```sql
ALTER TABLE Student_details ADD COLUMN mobilenumber number;
```

**Output:**

<img width="1223" height="447" alt="image" src="https://github.com/user-attachments/assets/1deb7cb0-54cd-433b-8b72-bd9334b592da" />

**Question 7**
---
<img width="1050" height="362" alt="image" src="https://github.com/user-attachments/assets/500e8dea-71a9-4ac0-8abe-bdcbf4f7c5b1" />

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

<img width="1251" height="357" alt="image" src="https://github.com/user-attachments/assets/59e7c625-c3a9-4fa9-be3d-70544c205054" />

**Question 8**
---
<img width="1077" height="467" alt="image" src="https://github.com/user-attachments/assets/bfb57615-122c-42e3-8e17-2cae6c6dc21e" />

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

<img width="1223" height="431" alt="image" src="https://github.com/user-attachments/assets/28831351-3d98-4ee8-8989-cb988036a48d" />

**Question 9**
---
<img width="907" height="382" alt="image" src="https://github.com/user-attachments/assets/5ed520bf-75f5-43dc-a9e5-00866af89cb0" />

```sql
INSERT INTO Employee SELECT EmployeeID,Name,Department,Salary FROM Former_employees;
```

**Output:**

<img width="1268" height="302" alt="image" src="https://github.com/user-attachments/assets/260d765a-0069-4288-bef8-23172939afdf" />

**Question 10**
---
<img width="1192" height="501" alt="image" src="https://github.com/user-attachments/assets/8f8454d4-ea83-4739-85bc-485bc2fc6bec" />

```sql
INSERT INTO Customers(CustomerID,Name,Address) VALUES (306,"Diana Prince","Themyscira");
INSERT INTO Customers(CustomerID,Name,Address,City,ZipCode) VALUES (307,"Bruce Wayne","Wayne Manor","Gotham",10007);
INSERT INTO Customers(CustomerID,Name,Address,ZipCode) VALUES (308,"Peter Parker","Queens",11375);


```

**Output:**

<img width="1240" height="322" alt="image" src="https://github.com/user-attachments/assets/9bf4d9b8-c0f4-4607-9755-62d13d66b3fc" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
