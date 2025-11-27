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
---
<img width="979" height="300" alt="image" src="https://github.com/user-attachments/assets/45156645-f08e-4d2d-99e3-f849cfadc151" />


```sql
ALTER TABLE employee
ADD designation varchar(50);
```

**Output:**

<img width="1246" height="361" alt="image" src="https://github.com/user-attachments/assets/760e96d8-a892-4c3d-90f4-6213da1e484d" />


**Question 2**
---
<img width="1199" height="471" alt="image" src="https://github.com/user-attachments/assets/9934d316-5db7-4d78-8dd0-133e394bc679" />


```sql
INSERT INTO Books (ISBN, Title, Author)
VALUES('978-1234567890','Introduction to AI', 'John Doe');

INSERT INTO Books (ISBN, Title, Author, Publisher, Year)
VALUES('978-9876543210','Deep Learning','Jane Doe','TechPress','2022');

INSERT INTO Books (ISBN, Title, Author, Year)
VALUES('978-1122334455','Cybersecurity Essentials','Alice Smith','2021');
```

**Output:**

<img width="1236" height="377" alt="image" src="https://github.com/user-attachments/assets/e1efd7fb-63dd-4f55-9340-4800e27a4f86" />

**Question 3**
---
<img width="969" height="344" alt="image" src="https://github.com/user-attachments/assets/5c3d5ac2-3452-4f76-984b-a03c15b3dfda" />


```sql
INSERT INTO Books (ISBN,Title, Author,  Publisher, YearPublished)
SELECT ISBN,Title, Author,  Publisher, YearPublished
FROM Out_of_print_books
```

**Output:**

<img width="1222" height="352" alt="image" src="https://github.com/user-attachments/assets/649b3d44-6a6f-4971-b8ea-d31519542b59" />



**Question 4**
---
<img width="1078" height="238" alt="image" src="https://github.com/user-attachments/assets/cda5b4c5-9f8e-468b-9b7c-565912b49e31" />


```sql
INSERT INTO Products (ProductID,  Name, Category, Price, Stock)
VALUES (101,'Laptop','Electronics',1500,50);
```

**Output:**

<img width="1226" height="324" alt="image" src="https://github.com/user-attachments/assets/7f5c2abc-cd6e-4008-a9c4-414774096c40" />


**Question 5**
---
<img width="1230" height="450" alt="image" src="https://github.com/user-attachments/assets/9699a869-aa21-4c9d-a674-cbeaae3eb470" />


```sql
CREATE TABLE Employees (
    EmployeeID INTEGER PRIMARY KEY,
    FirstName TEXT NOT NULL,
    LastName TEXT NOT NULL,
    Email TEXT UNIQUE,
    Salary INTEGER CHECK (Salary>0),
    DepartmentID INTEGER,
    FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**

<img width="1229" height="503" alt="image" src="https://github.com/user-attachments/assets/b665a306-e7a1-4950-8b94-a37592392414" />

**Question 6**
---
<img width="1221" height="410" alt="image" src="https://github.com/user-attachments/assets/df49f244-61d2-4072-8f68-18386fbd65ac" />


```sql
CREATE TABLE Attendance (
    AttendanceID  INTEGER PRIMARY KEY,
    EmployeeID INTEGER,
    AttendanceDate DATE,
    Status TEXT CHECK (Status IN ('Present','Absent','Leave')),
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1239" height="370" alt="image" src="https://github.com/user-attachments/assets/1ada9ffc-0169-444e-93a5-66012db2fcf7" />


**Question 7**
---
<img width="982" height="329" alt="image" src="https://github.com/user-attachments/assets/36f14618-395e-4f5c-8e6a-5ac5b8b29d0b" />


```sql
ALTER TABLE customers
ADD COLUMN email TEXT;
```

**Output:**

<img width="1239" height="369" alt="image" src="https://github.com/user-attachments/assets/a89447c9-d919-402b-a351-77581f5846c5" />


**Question 8**
---
<img width="1225" height="360" alt="image" src="https://github.com/user-attachments/assets/69fed08e-e6bc-4a26-9c39-944a0ef0176b" />


```sql
CREATE TABLE Department  (
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT UNIQUE NOT NULL,
    Location TEXT
);
```

**Output:**

<img width="1228" height="355" alt="image" src="https://github.com/user-attachments/assets/381c7796-93d7-4b9f-af96-8d140b912aeb" />


**Question 9**
---
<img width="1030" height="473" alt="image" src="https://github.com/user-attachments/assets/8b2ded21-e3de-459e-a1f6-6b60ebe1395f" />


```sql
CREATE TABLE item (
    item_id TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate INTEGER NOT NULL,
    icom_id TEXT(4),
    FOREIGN KEY (icom_id)
        REFERENCES company(com_id)
        ON UPDATE SET NULL
        ON DELETE SET NULL
);
```

**Output:**

<img width="1220" height="427" alt="image" src="https://github.com/user-attachments/assets/0a80907b-a68e-4a75-954e-8081c1664d21" />


**Question 10**
---
<img width="912" height="454" alt="image" src="https://github.com/user-attachments/assets/c2be74f3-b486-45bb-875a-6b915457e447" />


```sql
CREATE TABLE Products (
    ProductID INTEGER,
    ProductName TEXT,
    Price REAL,
    Stock INTEGER
);
```

**Output:**

<img width="1226" height="392" alt="image" src="https://github.com/user-attachments/assets/81874424-d520-49c7-b503-71e45c04a83f" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
