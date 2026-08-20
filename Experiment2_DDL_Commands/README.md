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
--

<img width="1007" height="377" alt="image" src="https://github.com/user-attachments/assets/344243d2-103f-4a41-93e6-8cdfaac02843" />


```sql
INSERT INTO Employee(EmployeeID, Name, Position)
VALUES (4, 'Emily White', 'Analyst');
```

**Output:**

<img width="1202" height="340" alt="image" src="https://github.com/user-attachments/assets/4b7de3c4-6e60-4877-b44b-1794ed9630d8" />



**Question 2**
---

<img width="1187" height="570" alt="image" src="https://github.com/user-attachments/assets/1beb4da5-972c-4bdf-a2ff-65ebf8c9f5b6" />


```sql
ALTER TABLE customer
ADD COLUMN birth_date timestamp;
```

**Output:**
<img width="1202" height="375" alt="image" src="https://github.com/user-attachments/assets/d21dbdda-20e6-4ed1-90c4-5be3d985304f" />


**Question 3**
---

<img width="1192" height="227" alt="image" src="https://github.com/user-attachments/assets/e6e000bb-774e-4296-ad1f-6bdf1c861815" />


```sql
INSERT INTO Customers(CustomerID, Name, Address, City, ZipCode)
VALUES (301, 'Michael Jordan', '123 Maple St', 'Chicago', 60616);
```

**Output:**

<img width="1202" height="262" alt="image" src="https://github.com/user-attachments/assets/4868cc17-f469-4a14-939b-cd6c3c265477" />



**Question 4**
---

<img width="1122" height="340" alt="image" src="https://github.com/user-attachments/assets/6f6fc1a5-6cbc-4335-ace3-4b57f1983be1" />


```sql
INSERT INTO Customers(CustomerID, Name, Address, Email)
SELECT CustomerID,Name,Address, Email
FROM Old_customers ;
```

**Output:**

<img width="1202" height="305" alt="image" src="https://github.com/user-attachments/assets/20882d42-b5d7-4153-ad75-1e925a152376" />


**Question 5**
---

<img width="1207" height="332" alt="image" src="https://github.com/user-attachments/assets/32ca3aa4-2199-4587-bfb1-fb6b04882c9c" />



```sql
CREATE TABLE Orders(
OrderID INTEGER PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INTEGER,
FOREIGN KEY(CustomerID)REFERENCES Customers(CustomerID)
);
```

**Output:**

<img width="1205" height="300" alt="image" src="https://github.com/user-attachments/assets/2b6ec2b0-b58a-45ea-8352-4ebec063b6da" />


**Question 6**
---

<img width="1092" height="330" alt="image" src="https://github.com/user-attachments/assets/0b1ebc32-fd95-4335-91ff-86cfbb25201c" />


```sql
CREATE TABLE Products(
ProductID INTEGER PRIMARY KEY,
ProductName VARCHAR(30) NOT NULL,
Price REAL CHECK(Price >0),
Stock INT CHECK (Stock  >= 0)
)
```

**Output:**

<img width="1197" height="297" alt="image" src="https://github.com/user-attachments/assets/f4ebe695-186a-41ca-9f3d-a61bed5789af" />


**Question 7**
---

<img width="1220" height="450" alt="image" src="https://github.com/user-attachments/assets/17e92880-b694-4b1f-9661-e6029717dc38" />


```sql
CREATE TABLE item (
    item_id   TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate      INTEGER NOT NULL,
    icom_id   TEXT CHECK(length(icom_id) = 4),
    FOREIGN KEY (icom_id)
        REFERENCES company(com_id)
        ON UPDATE SET NULL
        ON DELETE SET NULL
);
```

**Output:**

<img width="1207" height="362" alt="image" src="https://github.com/user-attachments/assets/69ab63b5-c375-4678-b2b3-163b374ad400" />


**Question 8**
---

<img width="1186" height="441" alt="image" src="https://github.com/user-attachments/assets/93b98fa4-6493-4b3d-9501-1f4f24a251a2" />


```sql
CREATE TABLE item (
    item_id   TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate      INTEGER NOT NULL,
    icom_id   TEXT CHECK(length(icom_id) = 4),
    FOREIGN KEY (icom_id)
        REFERENCES company(com_id)
        ON UPDATE CASCADE
        ON DELETE CASCADE
);
```

**Output:**

<img width="1202" height="367" alt="image" src="https://github.com/user-attachments/assets/254e4dae-7531-4b98-8ff4-4e49fb210601" />


**Question 9**
---

<img width="1206" height="331" alt="image" src="https://github.com/user-attachments/assets/3fbe7760-13c9-43e6-bb86-ee335abf7fc1" />


```sql
CREATE TABLE Department(
DepartmentID INTEGER PRIMARY KEY,
DepartmentName TEXT UNIQUE NOT NULL,
Location TEXT
);
```

**Output:**

<img width="1205" height="297" alt="image" src="https://github.com/user-attachments/assets/6e64f9cc-78e3-4f59-95c6-fef1982665f4" />



**Question 10**
---
<img width="1212" height="577" alt="image" src="https://github.com/user-attachments/assets/e70b1350-bc7a-4fb0-bc35-c537e5911c85" />


```sql
ALTER TABLE Student_details
ADD COLUMN State TEXT;
```

**Output:**

<img width="1202" height="377" alt="image" src="https://github.com/user-attachments/assets/02eadf46-73e3-4210-b2b3-dfb97d272ef5" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
