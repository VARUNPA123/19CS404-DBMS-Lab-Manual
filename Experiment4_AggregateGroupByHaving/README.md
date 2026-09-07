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
<img width="1132" height="557" alt="image" src="https://github.com/user-attachments/assets/03dd6008-18fa-40e5-85c3-0e0fd3327710" />

```sql
SELECT name AS Employee_Name, MIN(age) AS Age
FROM employee;
```

**Output:**

<img width="1105" height="322" alt="image" src="https://github.com/user-attachments/assets/c42fb672-54d6-40e7-9d80-3d88a7dc124c" />

**Question 2**
---
<img width="1151" height="522" alt="image" src="https://github.com/user-attachments/assets/8a7fddbd-56e8-4f5f-8823-a77b80f3d784" />

```sql
SELECT name,max(income)
FROM employee
WHERE city='California';
```

**Output:**

<img width="1110" height="321" alt="image" src="https://github.com/user-attachments/assets/21641704-609f-4a2e-9e40-af2fa92bdf66" />

**Question 3**
---
<img width="1167" height="527" alt="image" src="https://github.com/user-attachments/assets/7db74172-45e3-4355-a1aa-c4b4302a7635" />

```sql
SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```

**Output:**

<img width="972" height="317" alt="image" src="https://github.com/user-attachments/assets/628d683e-2240-4961-bde5-03239e01ad8b" />

**Question 4**
---
<img width="1157" height="597" alt="image" src="https://github.com/user-attachments/assets/f3cab458-6c3d-4174-a7ff-cfe3c1aa7db8" />

```sql
SELECT DoctorID, COUNT(*) AS TotalAppointments
FROM Appointments
GROUP BY DoctorID;
```

**Output:**

<img width="1101" height="687" alt="image" src="https://github.com/user-attachments/assets/8f372799-16e6-469a-95a6-dba18249cd59" />

**Question 5**
---
<img width="1162" height="497" alt="image" src="https://github.com/user-attachments/assets/9bc34ed8-e86f-4a9f-9d77-c88c1df1bfdb" />

```sql
SELECT Gender,COUNT(*) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**

<img width="1117" height="371" alt="image" src="https://github.com/user-attachments/assets/a870ee5f-6984-4484-a677-d51e334f9189" />

**Question 6**
---
<img width="1172" height="582" alt="image" src="https://github.com/user-attachments/assets/39d43811-b42d-4d2c-8eca-7d47e746e735" />

```sql
SELECT DoctorID,COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY DoctorID;
```

**Output:**

<img width="1101" height="677" alt="image" src="https://github.com/user-attachments/assets/cd3bc28c-b0f3-4725-97be-48beab689e76" />

**Question 7**
---
<img width="1137" height="560" alt="image" src="https://github.com/user-attachments/assets/d50fb981-449a-48be-954d-747cc2153a07" />

```sql
SELECT age,MIN(income)
FROM employee
GROUP BY age
HAVING MIN(income)<400000;
```

**Output:**

<img width="1102" height="397" alt="image" src="https://github.com/user-attachments/assets/92996158-ec89-4365-a68b-c51c17bb921b" />

**Question 8**
---
<img width="1145" height="597" alt="image" src="https://github.com/user-attachments/assets/81d2e75f-ca6d-41c7-941a-06121fab3f54" />

```sql
SELECT occupation,MIN(workhour)
FROM employee1
GROUP BY occupation
HAVING MIN(workhour)>8;
```

**Output:**

<img width="1122" height="507" alt="image" src="https://github.com/user-attachments/assets/c9f13c9d-b480-467b-9ce1-382c4afe20c7" />

**Question 9**
---
<img width="1160" height="587" alt="image" src="https://github.com/user-attachments/assets/f10fdd09-ce31-409f-a16f-005c0013b0f4" />

```sql
SELECT city,AVG(income)
FROM employee
GROUP BY city
HAVING AVG(income)>500000;
```

**Output:**

<img width="1111" height="445" alt="image" src="https://github.com/user-attachments/assets/66149070-c9f6-41a3-bf82-2d752233f7a9" />

**Question 10**
---
<img width="1150" height="531" alt="image" src="https://github.com/user-attachments/assets/91d13e65-635a-4fa8-a498-95b90aa731e1" />

```sql
SELECT age,MAX(income)
FROM employee
GROUP BY age
HAVING MAX(income)>2000000;
```

**Output:**

<img width="1070" height="375" alt="image" src="https://github.com/user-attachments/assets/d5ce24c6-b351-4541-a5d5-56c2929f0e19" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
