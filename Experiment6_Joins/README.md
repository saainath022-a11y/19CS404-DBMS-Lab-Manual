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
--
<img width="1302" height="808" alt="image" src="https://github.com/user-attachments/assets/06e9a6a1-c0f8-4a34-a794-b57c466fa9e0" />

```sql
SELECT p.admission_date,s.surgery_date FROM PATIENTS p
JOIN SURGERIES s
ON p.patient_id=s.patient_id;
```

**Output:**
<img width="983" height="521" alt="image" src="https://github.com/user-attachments/assets/a3344c68-f147-45d9-8574-7a0f5a1e07a6" />


**Question 2**
---
<img width="1247" height="862" alt="image" src="https://github.com/user-attachments/assets/00ddadec-d872-4fbd-96a5-ef84e0de94d2" />

```sql
SELECT c.cust_name,c.city,c.grade,s.name AS Salesman,s.city FROM customer c
JOIN salesman s
ON c.salesman_id=s.salesman_id
WHERE c.grade<300
ORDER BY c.customer_id;
```

**Output:**
<img width="1227" height="730" alt="image" src="https://github.com/user-attachments/assets/5662769d-e9a3-4876-abad-8f1b18283b2e" />


**Question 3**
---
<img width="1205" height="768" alt="image" src="https://github.com/user-attachments/assets/7e6910f9-c2b8-414a-9194-af8374c60255" />

```sql
SELECT p.* FROM PATIENTS p 
INNER JOIN DOCTORS d
ON p.doctor_id=d.doctor_id
WHERE d.first_name="John" AND d.last_name="Smith";
```

**Output:**

<img width="1237" height="408" alt="image" src="https://github.com/user-attachments/assets/a47795b2-c38a-45de-b41f-dfcf9f8cf388" />

**Question 4**
---
<img width="1212" height="857" alt="image" src="https://github.com/user-attachments/assets/e1dbae30-5649-43a2-9d81-754e716ff234" />


```sql
SELECT c.cust_name AS 'Customer Name',c.city,s.name AS Salesman,s.commission FROM customer c
JOIN salesman s
ON c.salesman_id=s.salesman_id;
```

**Output:**

<img width="1237" height="832" alt="image" src="https://github.com/user-attachments/assets/1a749469-0afd-4440-b9f0-832b8e662ac6" />

**Question 5**
---
<img width="1260" height="790" alt="image" src="https://github.com/user-attachments/assets/c86e87e5-e935-4e9e-8872-a425c40be257" />

```sql
SELECT p.first_name,s.* FROM PATIENTS p
INNER JOIN SURGERIES s
ON p.patient_id=s.patient_id
WHERE discharge_date BETWEEN '2024-03-01' AND '2024-03-31' AND admission_date NOT BETWEEN '2024-03-01' AND '2024-03-31';
```

**Output:**
<img width="1282" height="418" alt="image" src="https://github.com/user-attachments/assets/f77aa4d8-d531-49d5-8ce3-172b456289fd" />

**Question 6**
---

<img width="1257" height="403" alt="image" src="https://github.com/user-attachments/assets/9a34e65f-08a3-4766-803d-decd445689fe" />

```sql
SELECT s.name,c.cust_name,c.city,c.grade,c.salesman_id FROM Salesman s
LEFT JOIN Customer c
ON c.salesman_id=s.salesman_id
WHERE c.grade<=100;
```

**Output:**
<img width="1207" height="493" alt="image" src="https://github.com/user-attachments/assets/c2ff6db0-80f0-4b1a-b7dd-3db6f71bfcf5" />

**Question 7**
---
<img width="1240" height="792" alt="Screenshot 2026-09-01 150449" src="https://github.com/user-attachments/assets/63a3e90e-638d-487d-af8a-cbdd3b4165b0" />
<img width="1166" height="707" alt="Screenshot 2026-09-01 150502" src="https://github.com/user-attachments/assets/1cae6b21-0ca1-43c5-9ba5-48530728d729" />


```sql
SELECT c.cust_name,
       c.city,
       o.ord_no,
       o.ord_date,
       o.purch_amt AS "Order Amount",
       s.name,
       s.commission
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
   AND c.salesman_id = o.salesman_id
LEFT JOIN salesman s
    ON c.salesman_id = s.salesman_id;
```

**Output:**
<img width="1225" height="762" alt="Screenshot 2026-09-01 150528" src="https://github.com/user-attachments/assets/3955d734-dbb2-4cb7-af0c-d3fc0e70558d" />


**Question 8**
---
<img width="1110" height="846" alt="Screenshot 2026-09-01 150629" src="https://github.com/user-attachments/assets/80dbfdff-2a95-4224-9535-152e7593c538" />


```sql
SELECT s.name AS Salesman,
       c.cust_name,
       s.city
FROM salesman s
INNER JOIN customer c
    ON s.city = c.city;
```

**Output:**

<img width="1112" height="657" alt="Screenshot 2026-09-01 150648" src="https://github.com/user-attachments/assets/5fb506c2-fb49-4fab-824f-d32e1d6e449c" />


**Question 9**
---
<img width="1233" height="543" alt="Screenshot 2026-09-01 150701" src="https://github.com/user-attachments/assets/e56216dd-b5a7-4f45-81d8-14a4064bf460" />

```sql
SELECT s.name AS salesman_name,c.cust_name AS customer_name FROM Salesman s
LEFT JOIN Customer c
ON c.salesman_id=s.salesman_id;
```

**Output:**

<img width="716" height="838" alt="Screenshot 2026-09-01 150731" src="https://github.com/user-attachments/assets/fc4a8c70-9adb-481c-b260-ae3b3030bf9a" />


**Question 10**
---
<img width="1226" height="742" alt="Screenshot 2026-09-01 150744" src="https://github.com/user-attachments/assets/f7142998-cf52-4ec7-b662-c7967dd64ab8" />
<img width="685" height="223" alt="Screenshot 2026-09-01 150754" src="https://github.com/user-attachments/assets/6b6fb54c-bc35-4e92-9c9d-e2401c91b6e5" />


```sql
SELECT o.ord_no,o.purch_amt,c.cust_name,c.city FROM customer c
JOIN orders o
ON c.customer_id=o.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

<img width="1232" height="400" alt="Screenshot 2026-09-01 150813" src="https://github.com/user-attachments/assets/38b230f0-2201-4ac7-a5ea-74b6056403ed" />




## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
