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
--
<img width="1027" height="628" alt="image" src="https://github.com/user-attachments/assets/3b0e5ad7-3252-4128-bca2-42c03d77a893" />


```sql
SELECT DoctorID,count(PrescriptionID) as TotalPrescriptions
FROM Prescriptions
GROUP BY DoctorID;
```

**Output:**
<img width="745" height="736" alt="image" src="https://github.com/user-attachments/assets/5844d53d-6f5a-408a-85ea-620043d247f5" />


**Question 2**
---
<img width="1171" height="666" alt="image" src="https://github.com/user-attachments/assets/396fee37-697d-4998-bd52-48f11cfced7d" />


```sql
SELECT InsuranceCompany,COUNT(*) AS TotalExpiredPatients FROM Insurance
WHERE date(substr(ValidityPeriod,14,10)<date('now'))
GROUP BY InsuranceCompany
ORDER BY InsuranceCompany;
```

**Output:**

<img width="917" height="727" alt="image" src="https://github.com/user-attachments/assets/bf7586d2-2fd8-4ada-bf71-d6b3a6d132b3" />


**Question 3**
---

<img width="1037" height="572" alt="image" src="https://github.com/user-attachments/assets/da6e0079-e557-4c32-8ede-fecce5577614" />

```sql
SELECT Specialty,Gender,Count(*) AS TotalDoctors
FROM Doctors 
GROUP BY Specialty,Gender
ORDER BY Specialty,Gender;
```

**Output:**
<img width="902" height="630" alt="image" src="https://github.com/user-attachments/assets/1471e73b-74db-46f3-8cf6-7061530aeeba" />



**Question 4**
---
<img width="840" height="466" alt="image" src="https://github.com/user-attachments/assets/915db222-463c-4e59-9524-f84dbde5fdf8" />


```sql
SELECT AVG(Length(email)) AS avg_email_length FROM customer;
```

**Output:**
<img width="760" height="410" alt="image" src="https://github.com/user-attachments/assets/c668f175-1007-4b46-b10f-3eec7046985f" />



**Question 5**
---
<img width="956" height="538" alt="image" src="https://github.com/user-attachments/assets/93a09723-92a5-4eed-9977-0de54b93255a" />


```sql
SELECT SUM(inventory) AS total FROM fruits where unit='LB';

```

**Output:**

<img width="495" height="306" alt="image" src="https://github.com/user-attachments/assets/5e9ffacf-5a11-4ed5-b91a-2db6581b88b4" />


**Question 6**
---
<img width="906" height="487" alt="image" src="https://github.com/user-attachments/assets/d1f33239-4141-4a2d-9de9-bccb0d539245" />


```sql
SELECT count(*) AS COUNT FROM customer;
```

**Output:**
<img width="673" height="362" alt="image" src="https://github.com/user-attachments/assets/b213a1ab-9cfd-4356-94f5-1c42f8697f27" />


**Question 7**
---

<img width="888" height="451" alt="image" src="https://github.com/user-attachments/assets/5005b766-48bd-47b2-80f8-defd22bb559d" />

```sql
SELECT Count(*) AS employees_count from employee where income>50000;
```

**Output:**
<img width="516" height="283" alt="image" src="https://github.com/user-attachments/assets/515fabaf-01f7-4d8d-bb34-1144859c17fb" />


**Question 8**
---
<img width="1251" height="500" alt="image" src="https://github.com/user-attachments/assets/7dce112d-00b6-4f8b-ae25-a054e7d307d3" />

```sql
SELECT category_id,count(product_name) FROM products WHERE category_id<3
GROUP BY category_id ;
```

**Output:**

<img width="831" height="347" alt="image" src="https://github.com/user-attachments/assets/19884328-ebb0-4c6e-b490-bad0fe62b731" />


**Question 9**
---
<img width="1228" height="543" alt="image" src="https://github.com/user-attachments/assets/12508a3a-e709-47cd-8357-1bfdce848dbf" />

```sql
SELECT category_id,product_name,MAX(Price) AS Price FROM products
GROUP BY category_id
HAVING MAX(Price)>15;
```

**Output:**
<img width="890" height="356" alt="image" src="https://github.com/user-attachments/assets/6e2a4c58-f640-4a7b-a808-3b9b5841ee85" />



**Question 10**
---
<img width="1191" height="520" alt="image" src="https://github.com/user-attachments/assets/91a545ed-25b9-4652-a3dd-3ed55bf01ffa" />


```sql
SELECT category_id,SUM(price*category_id) AS Revenue FROM products
GROUP BY category_id
Having SUM(price*category_id)>25;
```

**Output:**

<img width="617" height="427" alt="image" src="https://github.com/user-attachments/assets/8524b420-c460-44e1-bec5-acfec376549f" />

## Grade:

<img width="1473" height="477" alt="image" src="https://github.com/user-attachments/assets/9578b958-fc7f-4a4c-bbdc-21472cbbc234" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
