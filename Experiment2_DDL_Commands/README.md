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
Properties: Must contain unique values. Cannot be null. Should contain minimal fields.
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
image
```sql
ALTER TABLE employee ADD designation varchar(50);
```
**Output:**
image

**Question 2**
---
image
```sql
INSERT INTO Books (ISBN, Title, Author) VALUES('978-1234567890','Introduction to AI', 'John Doe');
INSERT INTO Books (ISBN, Title, Author, Publisher, Year) VALUES('978-9876543210','Deep Learning','Jane Doe','TechPress','2022');
INSERT INTO Books (ISBN, Title, Author, Year) VALUES('978-1122334455','Cybersecurity Essentials','Alice Smith','2021');
```
**Output:**
image

**Question 3**
---
image
```sql
INSERT INTO Books (ISBN,Title, Author, Publisher, YearPublished)
SELECT ISBN,Title, Author, Publisher, YearPublished FROM Out_of_print_books
```
**Output:**
image

**Question 4**
---
image
```sql
INSERT INTO Products (ProductID, Name, Category, Price, Stock) VALUES (101,'Laptop','Electronics',1500,50);
```
**Output:**
image

**Question 5**
---
image
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
image

**Question 6**
---
image
```sql
CREATE TABLE Attendance (
  AttendanceID INTEGER PRIMARY KEY,
  EmployeeID INTEGER,
  AttendanceDate DATE,
  Status TEXT CHECK (Status IN ('Present','Absent','Leave')),
  FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```
**Output:**
image

**Question 7**
---
image
```sql
ALTER TABLE customers ADD COLUMN email TEXT;
```
**Output:**
image

**Question 8**
---
image
```sql
CREATE TABLE Department (
  DepartmentID INTEGER PRIMARY KEY,
  DepartmentName TEXT UNIQUE NOT NULL,
  Location TEXT
);
```
**Output:**
image

**Question 9**
---
image
```sql
CREATE TABLE item (
  item_id TEXT PRIMARY KEY,
  item_desc TEXT NOT NULL,
  rate INTEGER NOT NULL,
  icom_id TEXT(4),
  FOREIGN KEY (icom_id) REFERENCES company(com_id)
  ON UPDATE SET NULL
  ON DELETE SET NULL
);
```
**Output:**
image

**Question 10**
---
image
```sql
CREATE TABLE Products (
  ProductID INTEGER,
  ProductName TEXT,
  Price REAL,
  Stock INTEGER
);
```
**Output:**
image

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
