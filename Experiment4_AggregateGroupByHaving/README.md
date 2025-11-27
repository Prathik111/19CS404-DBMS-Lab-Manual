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
<img width="651" height="658" alt="image" src="https://github.com/user-attachments/assets/c537b366-4578-49fb-82ab-ffbe80df14fb" />


```sql
select DATE(AppointmentDateTime) as AppointmentDate,count(*) as TotalAppointments from Appointments group by DATE(AppointmentDateTime);
```

**Output:**

<img width="816" height="724" alt="image" src="https://github.com/user-attachments/assets/cf2c657f-2c19-4738-b00d-196dda375b8e" />


**Question 2**
---
<img width="605" height="603" alt="image" src="https://github.com/user-attachments/assets/28bef9d7-8767-4191-9285-24b7062fe60e" />



```sql
select strftime('%H', AppointmentDateTime)as HourOfDay,count(*) as TotalAppointments from Appointments group by HourofDay;
```

**Output:**

<img width="698" height="610" alt="image" src="https://github.com/user-attachments/assets/84c5021d-c3d6-44ba-9960-f2548a0920f4" />


**Question 3**
---
<img width="969" height="488" alt="image" src="https://github.com/user-attachments/assets/35c30080-91d9-405a-8cee-6e1ba5b518e2" />


```sql
select count(*) as COUNT from customer where grade is not null;
```

**Output:**

<img width="356" height="388" alt="image" src="https://github.com/user-attachments/assets/e18e243b-780f-42af-b0cf-dd2f0e31d680" />


**Question 4**
---
<img width="728" height="476" alt="image" src="https://github.com/user-attachments/assets/f070d93b-94b9-4d8b-93b4-e4968dd8e1e1" />


```sql
select avg(length(email)) as avg_email_length from customer;
```

**Output:**

<img width="473" height="382" alt="image" src="https://github.com/user-attachments/assets/06482b3e-cfc2-48cd-881f-de48074ddb8c" />


**Question 5**
---
<img width="670" height="540" alt="image" src="https://github.com/user-attachments/assets/b5f88cdd-3bec-45c8-899e-06c8aa6c79e0" />


```sql
select name as fruit_name, min(inventory) as lowest_quantity from fruits;
```

**Output:**

<img width="687" height="389" alt="image" src="https://github.com/user-attachments/assets/660d158b-d725-4087-99de-50bd1e6d010b" />


**Question 6**
---
<img width="673" height="504" alt="image" src="https://github.com/user-attachments/assets/dede6949-5975-4d95-beed-f7c499237c7e" />

```sql
select name as Employee_Name, min(age) as Age from employee; 
```

**Output:**

<img width="635" height="384" alt="image" src="https://github.com/user-attachments/assets/8b7da0bc-005d-4363-a1a1-c4570e641936" />


**Question 7**
---
<img width="1204" height="498" alt="image" src="https://github.com/user-attachments/assets/54d127df-fa28-4dcd-bffc-9c31da632f26" />


```sql
select age, MIN(income) from employee where income < 400000 group by age;
```

**Output:**

<img width="607" height="474" alt="image" src="https://github.com/user-attachments/assets/7cfee4e5-d422-4949-a94b-0023481f961e" />


**Question 8**
---
<img width="1206" height="548" alt="image" src="https://github.com/user-attachments/assets/bd2392fb-55e2-4cc0-b9b0-6128154f5711" />


```sql
select occupation,MIN(workhour) from employee1 where workhour>8 group by occupation;
```

**Output:**

<img width="619" height="563" alt="image" src="https://github.com/user-attachments/assets/aa863cdb-016f-4d01-8437-1a15e2a701d0" />


**Question 9**
---
<img width="1202" height="464" alt="image" src="https://github.com/user-attachments/assets/33846c74-db6e-4eca-9f59-694c063feb60" />


```sql
select jdate, AVG(workhour) from employee1 group by jdate having avg(workhour)<10;
```

**Output:**

<img width="630" height="415" alt="image" src="https://github.com/user-attachments/assets/4489ac1c-440c-439a-9f06-ba0c846e317e" />


**Question 10**
---
<img width="746" height="450" alt="image" src="https://github.com/user-attachments/assets/5c79ebf2-5a43-45f8-be65-1ce535ef650d" />


```sql
select avg(length(email)) as avg_email_length from customer;
```

**Output:**

<img width="494" height="400" alt="image" src="https://github.com/user-attachments/assets/3fadc989-4f37-4e52-85e6-100845275a5e" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
