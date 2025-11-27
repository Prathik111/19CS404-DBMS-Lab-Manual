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
<img width="1037" height="530" alt="image" src="https://github.com/user-attachments/assets/e1017d22-fdd5-4b80-96bb-b52dc644eaf5" />

```sql
select upper(EmpFname) as EmpName from EmployeeInfo;
```

**Output:**
image

**Question 2**
---
image
```sql
select ename,hiredate,strftime('%w',hiredate) as day_of_week from emp where strftime('%w',hiredate) in ('0','6');
```

**Output:**
image

**Question 3**
---
image
```sql
select ord_no, purch_amt, (purch_amt/60) as "Achieved %", 100-(purch_amt/60) as "Unachieved %" from orders where "Achieved %" >50;
```

**Output:**
image

**Question 4**
---
image
```sql
select *,original_price * discount_percentage as discount_amount from Products where discount_amount>50;
```

**Output:**
image

**Question 5**
---
image
```sql
select * from salesman where city!='Paris' and city!='Rome';
```

**Output:**
image

**Question 6**
---
image
```sql
alter table Calculations add column base_status;
update Calculations set base_status='Provided' where base is not null;
update Calculations set base_status='Not Provided' where base is null;
select id,base,base_status from Calculations;
```

**Output:**
image

**Question 7**
---
image
```sql
delete from Customer where GRADE=2;
```

**Output:**
image

**Question 8**
---
image
```sql
delete from Surgeries where surgery_id=3;
```

**Output:**
image

**Question 9**
---
image
```sql
update Employees set EMAIL='Unavailable';
```

**Output:**
image

**Question 10**
---
image
```sql
update Customer set grade=5 where city='Chennai';
```

**Output:**
image

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
