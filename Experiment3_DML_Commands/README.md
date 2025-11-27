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

<img width="395" height="409" alt="image" src="https://github.com/user-attachments/assets/69f658a5-48d4-4c77-a8c8-df69069b3fd2" />


**Question 2**
---
<img width="965" height="588" alt="image" src="https://github.com/user-attachments/assets/9a80a5e3-4f2b-4e89-b7c8-179edb925353" />


```sql
select ename,hiredate,strftime('%w',hiredate) as day_of_week from emp where strftime('%w',hiredate) in ('0','6');
```

**Output:**

<img width="814" height="338" alt="image" src="https://github.com/user-attachments/assets/14812240-616c-421c-84a8-fd568da1a539" />


**Question 3**
---
<img width="1166" height="599" alt="image" src="https://github.com/user-attachments/assets/bcc0ce18-fc4e-4d51-a20d-df04e467354b" />


```sql
select ord_no, purch_amt, (purch_amt/60) as "Achieved %", 100-(purch_amt/60) as "Unachieved %" from orders where "Achieved %" >50;
```

**Output:**

<img width="1042" height="472" alt="image" src="https://github.com/user-attachments/assets/06564a3d-26d8-45dd-acb2-96c567903a41" />


**Question 4**
---
<img width="1090" height="622" alt="image" src="https://github.com/user-attachments/assets/baefc82c-7e83-4963-a0f5-b3ffd2e2c96e" />


```sql
select *,original_price * discount_percentage as discount_amount from Products where discount_amount>50;
```

**Output:**

<img width="1214" height="313" alt="image" src="https://github.com/user-attachments/assets/1babcc8c-97d6-4e09-aa45-7b1a5e2c5f3f" />


**Question 5**
---
<img width="1106" height="601" alt="image" src="https://github.com/user-attachments/assets/f3898e9b-bd21-4150-a26f-7d4c9719ec6e" />


```sql
select * from salesman where city!='Paris' and city!='Rome';
```

**Output:**

<img width="1028" height="452" alt="image" src="https://github.com/user-attachments/assets/ebb66779-0471-40ee-a7ff-9ccf8aa80375" />


**Question 6**
---
<img width="980" height="583" alt="image" src="https://github.com/user-attachments/assets/410f103c-eafd-4de4-9a0d-afe9c8bd89d3" />


```sql
alter table Calculations add column base_status;
update Calculations set base_status='Provided' where base is not null;
update Calculations set base_status='Not Provided' where base is null;
select id,base,base_status from Calculations;
```

**Output:**

<img width="831" height="546" alt="image" src="https://github.com/user-attachments/assets/939f256a-95a9-4619-8c03-d9e51beb4cf8" />


**Question 7**
---
<img width="1219" height="715" alt="image" src="https://github.com/user-attachments/assets/fff3c5c3-1b82-4d6e-bcd1-36755bc5be6a" />


```sql
delete from Customer where GRADE=2;
```

**Output:**

<img width="691" height="653" alt="image" src="https://github.com/user-attachments/assets/ac1a6f14-0307-413d-b291-8a485e355725" />


**Question 8**
---
<img width="743" height="502" alt="image" src="https://github.com/user-attachments/assets/dd7be70d-8ee5-4f42-84d1-2d6ee6e27216" />


```sql
delete from Surgeries where surgery_id=3;
```

**Output:**

<img width="1223" height="457" alt="image" src="https://github.com/user-attachments/assets/cff63b51-61c9-4e6d-a8d3-5d04e16da455" />

**Question 9**
---
<img width="1092" height="653" alt="image" src="https://github.com/user-attachments/assets/280dc535-fa92-4072-9c7e-571bd8cf07b9" />


```sql
update Employees set EMAIL='Unavailable';
```

**Output:**

<img width="1227" height="489" alt="image" src="https://github.com/user-attachments/assets/5cd9a26f-00fe-495a-aa52-bb88fbda38c7" />


**Question 10**
---
<img width="698" height="80" alt="image" src="https://github.com/user-attachments/assets/a03fd848-6142-4415-b064-ac7034366f1f" />


```sql
update Customer set grade=5 where city='Chennai';
```

**Output:**

<img width="1215" height="534" alt="image" src="https://github.com/user-attachments/assets/88b465e2-b9f1-4ee3-87e4-be18f1f9b48e" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
