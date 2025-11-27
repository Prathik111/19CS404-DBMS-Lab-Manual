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
<img width="1059" height="566" alt="image" src="https://github.com/user-attachments/assets/55ae0df8-2e63-4975-9e68-bb47fe58cb78" />


```sql
select name from customer where phone in (select phone from customer group by phone having count(phone)=1);
```

**Output:**

<img width="488" height="528" alt="image" src="https://github.com/user-attachments/assets/c15dc98f-f29b-46a9-8a43-c2a2fa8c7a3a" />


**Question 2**
---
<img width="1226" height="640" alt="image" src="https://github.com/user-attachments/assets/65d2550d-eccd-4da0-ac76-a9c40a160630" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);

```

**Output:**

<img width="1266" height="522" alt="image" src="https://github.com/user-attachments/assets/d7b589a5-dc27-4a9a-bba9-b153a3bee10c" />


**Question 3**
---
<img width="1171" height="717" alt="image" src="https://github.com/user-attachments/assets/2f7ec381-db55-4a1f-ac37-7a70c5498620" />

```sql
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c
    ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

<img width="598" height="548" alt="image" src="https://github.com/user-attachments/assets/233c125d-a9db-40dd-8637-af374b86283a" />


**Question 4**
---
<img width="969" height="489" alt="image" src="https://github.com/user-attachments/assets/e8b453b2-e447-4281-8a55-656d7e22b6bf" />


```sql
SELECT medication_id,
       medication_name,
       dosage
FROM Medications
WHERE dosage = (
    SELECT MIN(dosage)
    FROM Medications
);

```

**Output:**

<img width="878" height="468" alt="image" src="https://github.com/user-attachments/assets/85d07c28-d444-4205-a13d-77987c549e4d" />


**Question 5**
---
<img width="974" height="678" alt="image" src="https://github.com/user-attachments/assets/9410ff74-dfb2-401a-a036-dfddff1d8727" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;

```

**Output:**

<img width="1204" height="521" alt="image" src="https://github.com/user-attachments/assets/2e4c7b74-7a56-46f7-8684-0162f7644daa" />


**Question 6**
---
<img width="1244" height="556" alt="image" src="https://github.com/user-attachments/assets/64a7879c-2783-4ed9-bd28-113b7a80e581" />


```sql
SELECT ord_no,
       purch_amt,
       ord_date,
       customer_id,
       salesman_id
FROM orders
WHERE salesman_id IN (
        SELECT salesman_id
        FROM orders
        WHERE customer_id = 3007
);

```

**Output:**

<img width="1253" height="492" alt="image" src="https://github.com/user-attachments/assets/60cd0809-e217-4c2c-9cc4-1cab325d62a8" />


**Question 7**
---
<img width="1168" height="738" alt="image" src="https://github.com/user-attachments/assets/d8222b4c-136c-486e-b0f4-622ece93f022" />


```sql
SELECT o.ord_no,
       o.purch_amt,
       o.ord_date,
       o.customer_id,
       o.salesman_id
FROM orders o
JOIN salesman s
      ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam';

```

**Output:**

<img width="1264" height="451" alt="image" src="https://github.com/user-attachments/assets/abad091e-5412-4c66-9a63-d488631f212c" />


**Question 8**
---
<img width="1252" height="629" alt="image" src="https://github.com/user-attachments/assets/c2c7825c-f289-4e3d-81f3-9da932c07143" />


```sql
SELECT *
FROM Grades g
WHERE grade = (
    SELECT MIN(grade)
    FROM Grades
    WHERE subject = g.subject
);

```

**Output:**

<img width="1269" height="520" alt="image" src="https://github.com/user-attachments/assets/7224231b-0dbc-42c2-8ec2-472df5175fd5" />


**Question 9**
---
<img width="968" height="486" alt="image" src="https://github.com/user-attachments/assets/c86b27cb-07d1-4487-be34-14cb64c1b222" />


```sql
SELECT medication_id,
       medication_name,
       dosage
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage)
    FROM Medications
);


```

**Output:**

<img width="866" height="467" alt="image" src="https://github.com/user-attachments/assets/5c066ca4-5e70-455d-82c2-aaf5d1c1aa97" />


**Question 10**
---
<img width="846" height="506" alt="image" src="https://github.com/user-attachments/assets/ad206dc0-9c4e-48e3-9d06-4774cc223989" />


```sql
SELECT medication_id,
       medication_name,
       dosage
FROM Medications
WHERE dosage = (
    SELECT MIN(dosage)
    FROM Medications
);

```

**Output:**

<img width="894" height="405" alt="image" src="https://github.com/user-attachments/assets/c5c115d3-2a0c-414c-b5d3-fbef249ae8b1" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
