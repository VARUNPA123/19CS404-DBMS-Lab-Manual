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
<img width="1047" height="531" alt="image" src="https://github.com/user-attachments/assets/b647ad8e-8537-4895-a902-57dbfaea8715" />


```sql
UPDATE PRODUCTS
SET sell_price = sell_price + sell_price*0.1
WHERE supplier_id = 6;
```

**Output:**

<img width="1302" height="252" alt="image" src="https://github.com/user-attachments/assets/82cd8fb4-f6b0-4343-8656-696770e3e4e2" />


**Question 2**
---
<img width="1162" height="655" alt="image" src="https://github.com/user-attachments/assets/e76ad85e-83ab-4efd-ba2c-d572569ed52b" />


```sql
select id,value1,
case 
    when value1 < 13 then 'Child'
    when value1 >= 13 and value1 <= 19 then 'Teen'
    else 'Adult'
end as age_group    
from Calculations;
```

**Output:**

<img width="1072" height="377" alt="image" src="https://github.com/user-attachments/assets/b6c3b202-57ba-4211-aa72-249cedd88d27" />


**Question 3**
---
<img width="1152" height="692" alt="image" src="https://github.com/user-attachments/assets/a9aacbe6-4767-4e58-9c8e-8672a95ff102" />


```sql
select * from emp where hiredate between '2022-01-01' and '2022-12-31';
```

**Output:**

<img width="922" height="157" alt="image" src="https://github.com/user-attachments/assets/9275b546-b443-4024-89ef-eda95f621f69" />


**Question 4**
---
<img width="987" height="577" alt="image" src="https://github.com/user-attachments/assets/60fee09b-c670-4c82-9614-bf51785c9266" />


```sql
select id, round(decimal,3) as rounded_value
from Calculations;
```

**Output:**

<img width="952" height="267" alt="image" src="https://github.com/user-attachments/assets/4d93f251-0834-4b0e-a6b3-8f4911052402" />


**Question 5**
---
<img width="1182" height="480" alt="image" src="https://github.com/user-attachments/assets/09175414-5d47-4cd5-9ea5-699023523878" />


```sql
-- Paste your SQL code below for Question 5
```

**Output:**

![Output5](output.png)

**Question 6**
---
-- Paste Question 6 here

```sql
-- Paste your SQL code below for Question 6
```

**Output:**

![Output6](output.png)

**Question 7**
---
-- Paste Question 7 here

```sql
-- Paste your SQL code below for Question 7
```

**Output:**

![Output7](output.png)

**Question 8**
---
-- Paste Question 8 here

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
-- Paste Question 9 here

```sql
-- Paste your SQL code below for Question 9
```

**Output:**

![Output9](output.png)

**Question 10**
---
-- Paste Question 10 here

```sql
-- Paste your SQL code below for Question 10
```

**Output:**

![Output10](output.png)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
