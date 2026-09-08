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
<img width="1217" height="333" alt="image" src="https://github.com/user-attachments/assets/3c9e0cc0-ef38-4326-b0ed-87fea5f9e987" />

```sql
UPDATE products 
SET quantity=quantity*1.10;
```

**Output:**

<img width="1237" height="588" alt="image" src="https://github.com/user-attachments/assets/f1828c3e-fc97-4500-b037-0b674d7ccfcc" />

**Question 2**
---
<img width="1042" height="225" alt="image" src="https://github.com/user-attachments/assets/5034f1c0-ab2f-41eb-a466-948ff088656e" />

```sql
update products set product_name='Grapefruit'
where product_id=4;
```

**Output:**

<img width="1217" height="270" alt="image" src="https://github.com/user-attachments/assets/df15d3d8-5fe6-4c1b-8b7e-5eb7b881b4b3" />

**Question 3**
---
<img width="1233" height="747" alt="image" src="https://github.com/user-attachments/assets/338ff861-05cc-4329-ada5-1ef444a85d34" />

```sql
UPDATE products
SET sell_price=CAST(cost_price*1.35 AS INT)
WHERE (sell_price-cost_price)*1.0/cost_price<30;
```

**Output:**

<img width="1245" height="520" alt="image" src="https://github.com/user-attachments/assets/5b12dda4-5064-4343-bdec-0295e1a0cccb" />

**Question 4**
---
<img width="1037" height="817" alt="image" src="https://github.com/user-attachments/assets/0843bfa7-7d49-4c77-bd14-8f4608a1ef41" />

```sql
update sales set sell_price=sell_price+3
where product_id IN(
    select product_id
    from products
    where supplier_id=4
);
```

**Output:**

<img width="1190" height="426" alt="image" src="https://github.com/user-attachments/assets/0370bd67-017d-4f8a-9bd8-7d2efc241e6d" />

**Question 5**
---
<img width="1190" height="426" alt="image" src="https://github.com/user-attachments/assets/6e9d0a67-7e4d-43dc-91cc-750b07254943" />

```sql
update products set product_name='Premium Bread'
where product_id=5;
```

**Output:**

<img width="1228" height="372" alt="image" src="https://github.com/user-attachments/assets/202b122e-1087-4ca6-b050-e55328e7efca" />

**Question 6**
---
<img width="1133" height="160" alt="image" src="https://github.com/user-attachments/assets/fd6f47d1-b5fa-499d-914c-95e05635a5e9" />

```sql
delete from Doctors where specialization='Cardiology';
```

**Output:**

<img width="1228" height="372" alt="image" src="https://github.com/user-attachments/assets/4eeac1f0-72a3-4336-95d1-9d2e5551d6bb" />

**Question 7**
---
<img width="1196" height="717" alt="image" src="https://github.com/user-attachments/assets/11830dc4-2d5e-4d1d-953f-65f4f4d725b9" />

```sql
delete from customer where OPENING_AMT between 4000 and 6000;
```

**Output:**

<img width="1210" height="575" alt="image" src="https://github.com/user-attachments/assets/c9bd4daa-8039-43c2-8e41-1c1383e6f4d3" />

**Question 8**
---
<img width="1183" height="577" alt="image" src="https://github.com/user-attachments/assets/4aaa7c7c-e3b1-4f48-b43e-d0ef53d048d0" />

```sql
delete from Doctors where last_name is NULL;
```

**Output:**

<img width="1196" height="672" alt="image" src="https://github.com/user-attachments/assets/06355e2c-d129-4c5c-9a89-c6d81a393a6b" />

**Question 9**
---
<img width="1230" height="672" alt="image" src="https://github.com/user-attachments/assets/bcd0314a-f0ec-4775-8a16-38029b4edc0c" />

```sql
delete from Customer where Length(Cust_Name)=6;
```

**Output:**

<img width="1220" height="667" alt="image" src="https://github.com/user-attachments/assets/d790857a-bded-45dd-a376-dfa0ac45c08a" />

**Question 10**
---
<img width="1207" height="660" alt="image" src="https://github.com/user-attachments/assets/885c6022-336b-46e8-8d91-0addd6d97aa3" />

```sql
delete from Customer where Grade >= 2;
```

**Output:**

<img width="875" height="522" alt="image" src="https://github.com/user-attachments/assets/68b223e3-44bc-4e24-8616-ec2fb6bc214a" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
