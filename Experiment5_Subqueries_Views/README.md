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
--
<img width="1095" height="536" alt="image" src="https://github.com/user-attachments/assets/992fbbba-9e3d-4409-bb42-7a4107e812f8" />


```sql
SELECT name FROM customer 
WHERE phone IN (SELECT phone FROM customer 
    GROUP BY phone
    HAVING COUNT(*)=1); 
```

**Output:**

<img width="1032" height="500" alt="image" src="https://github.com/user-attachments/assets/6acc6d68-d619-4a7e-b3ce-a0152666c010" />


**Question 2**
---
<img width="1262" height="717" alt="image" src="https://github.com/user-attachments/assets/d096b578-79db-44c8-9880-df5219e02830" />


```sql
SELECT salesman_id,name FROM salesman
WHERE salesman_id IN (
    SELECT salesman_id FROM customer 
    GROUP BY salesman_id
    HAVING COUNT(*)>1
);
```

**Output:**

<img width="630" height="465" alt="image" src="https://github.com/user-attachments/assets/6bbdb4d6-b308-42be-838c-c36478caf842" />


**Question 3**
---
<img width="1277" height="671" alt="image" src="https://github.com/user-attachments/assets/9381b91f-fd59-46cf-8afc-17eff421fa69" />


```sql
SELECT student_name,grade FROM GRADES g
WHERE grade = (SELECT MAX(grade) FROM GRADES
    WHERE subject=g.subject
);
```

**Output:**
<img width="881" height="417" alt="image" src="https://github.com/user-attachments/assets/51bdb660-7088-4f3d-a011-e900a534078c" />



**Question 4**
---
<img width="1223" height="820" alt="image" src="https://github.com/user-attachments/assets/9942f79d-a782-4efd-bd27-905dcf886a9f" />


```sql

SELECT * FROM orders
WHERE salesman_id IN (
    SELECT salesman_id FROM salesman
    WHERE city='New York'
    );
```

**Output:**

<img width="1242" height="457" alt="image" src="https://github.com/user-attachments/assets/49d55678-5155-489d-88f2-c3ff6578449d" />

**Question 5**
---
<img width="1111" height="647" alt="image" src="https://github.com/user-attachments/assets/3a2fa928-b76d-400e-9646-95a0a67a4b71" />

```sql
SELECT * FROm CUSTOMERS 
WHERE salary=1500;
```

**Output:**

<img width="1202" height="290" alt="image" src="https://github.com/user-attachments/assets/084d39ea-3e7a-4dd1-8ff9-23424743415e" />


**Question 6**
---
<img width="1238" height="630" alt="image" src="https://github.com/user-attachments/assets/15e11a03-d1d3-458c-ba75-fb267d37665e" />


```sql
SELECT *
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);
```

**Output:**

<img width="1273" height="463" alt="image" src="https://github.com/user-attachments/assets/47e8d47d-d1e1-4767-81b0-c81b5d1f7c5d" />


**Question 7**
---
<img width="1267" height="598" alt="image" src="https://github.com/user-attachments/assets/8db85fa7-d80c-41c4-9b00-064a451b522a" />


```sql
SELECT * FROM GRADES g
WHERE grade = (SELECT MIN(grade) FROM GRADES
    WHERE subject=g.subject
    );

```

**Output:**
<img width="1232" height="441" alt="image" src="https://github.com/user-attachments/assets/257df999-6e29-427a-a75a-2718679206c0" />


**Question 8**
---
<img width="1221" height="683" alt="image" src="https://github.com/user-attachments/assets/dce7991b-4dae-4d19-b8a1-68dbd950cc7f" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;
```

**Output:**

<img width="1263" height="450" alt="image" src="https://github.com/user-attachments/assets/3d3d8ccf-6a4b-4f03-8af8-8f44ec3ad874" />


**Question 9**
---
<img width="983" height="732" alt="image" src="https://github.com/user-attachments/assets/97747627-5791-42f6-a602-98e71766bd56" />


```sql
SELECT *
FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**
<img width="1200" height="561" alt="image" src="https://github.com/user-attachments/assets/d6a97ef8-1e4a-47cb-883c-09b6fb521db7" />



**Question 10**
---
<img width="1037" height="498" alt="image" src="https://github.com/user-attachments/assets/6ca728ae-4c41-4e6e-9462-cfa14dafd51e" />


```sql
SELECT *
FROM Medications
WHERE dosage = (
    SELECT MIN(dosage)
    FROM Medications
);
```

**Output:**

<img width="895" height="375" alt="image" src="https://github.com/user-attachments/assets/798426b3-a1fd-4244-8dc9-1490d0958740" />




## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
