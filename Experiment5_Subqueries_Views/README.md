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
<img width="1171" height="542" alt="image" src="https://github.com/user-attachments/assets/34d1948b-2083-4e6f-8397-7a7a373bba9c" />

```sql
SELECT grade,COUNT(*) FROM customer
WHERE grade>(SELECT AVG(grade) FROM customer
WHERE city='New York')
GROUP BY grade;
```

**Output:**

<img width="1092" height="342" alt="image" src="https://github.com/user-attachments/assets/7e50c6aa-9c29-4ba9-a7c1-1c60cb7cff85" />

**Question 2**
---
<img width="1162" height="692" alt="image" src="https://github.com/user-attachments/assets/8c7f8b81-d4a7-4345-8942-8bfd8f526410" />

```sql
SELECT * FROM customers
WHERE address='Delhi';
```

**Output:**

<img width="1172" height="341" alt="image" src="https://github.com/user-attachments/assets/a9f8dc3b-c541-44b7-88e7-97391bb876c3" />

**Question 3**
---
<img width="1167" height="715" alt="image" src="https://github.com/user-attachments/assets/af8a9483-cc0c-4850-b9e3-28db7268d505" />

```sql
SELECT s.salesman_id,s.name FROM salesman s
JOIN customer c
ON s.salesman_id=c.salesman_id
GROUP BY s.salesman_id,s.name
HAVING COUNT(c.customer_id)>1;
```

**Output:**

<img width="1102" height="442" alt="image" src="https://github.com/user-attachments/assets/005a9000-be10-41e2-80e0-6b4cc0c3c139" />

**Question 4**
---
<img width="1172" height="657" alt="image" src="https://github.com/user-attachments/assets/670612af-524a-46d0-ad70-25ba4812e799" />

```sql
SELECT * FROM customers
WHERE salary<2500;
```

**Output:**

<img width="1172" height="457" alt="image" src="https://github.com/user-attachments/assets/b6e50150-5eec-4ea8-93a2-89159aecd074" />

**Question 5**
---
<img width="1205" height="607" alt="image" src="https://github.com/user-attachments/assets/fd94b1cd-c562-4ffa-aabb-8abfd8088e80" />

```sql
SELECT * FROM Employee
WHERE age<(SELECT AVG(age) FROM Employee
WHERE income>1000000);
```

**Output:**

<img width="1162" height="287" alt="image" src="https://github.com/user-attachments/assets/d26b3150-3757-4b0f-ba07-2815aec8e49c" />

**Question 6**
---
<img width="1202" height="622" alt="image" src="https://github.com/user-attachments/assets/fd777199-8e59-4034-abe3-8a24b7ac6015" />

```sql
SELECT * FROM orders
WHERE salesman_id IN (SELECT salesman_id FROM salesman
WHERE name='Paul Adam');
```

**Output:**

<img width="1165" height="270" alt="image" src="https://github.com/user-attachments/assets/a701e0c4-e561-478f-8d74-a81aa2929277" />

**Question 7**
---
<img width="1197" height="537" alt="image" src="https://github.com/user-attachments/assets/2a9dc502-0883-41b8-ae95-d9cf46b2306d" />

```sql
SELECT * FROM customer
WHERE city NOT IN (SELECT city FROM customer
WHERE id=(SELECT MAX(id) FROM customer));
```

**Output:**

<img width="1252" height="342" alt="image" src="https://github.com/user-attachments/assets/ec9143b5-f03e-4d9e-aa34-2d44da5315b5" />

**Question 8**
---
<img width="1162" height="665" alt="image" src="https://github.com/user-attachments/assets/3ea2520a-75aa-4b1d-ad20-b7eacecbbd50" />

```sql
SELECT commission FROM salesman
WHERE salesman_id IN(SELECT salesman_id FROM customer
WHERE city='Paris');
```

**Output:**

<img width="1085" height="306" alt="image" src="https://github.com/user-attachments/assets/980ce09e-e0a7-4f6b-953c-5889ac8d8d8a" />

**Question 9**
---
<img width="1181" height="490" alt="image" src="https://github.com/user-attachments/assets/ced3fd4e-41c3-4463-98b9-ea26e4219dea" />

```sql
SELECT * FROM Medications
WHERE dosage=(SELECT MIN(dosage)
FROM Medications);
```

**Output:**

<img width="1117" height="370" alt="image" src="https://github.com/user-attachments/assets/a9838a8c-442a-447b-b747-140039c6f37b" />

**Question 10**
---
<img width="1177" height="592" alt="image" src="https://github.com/user-attachments/assets/474db4b8-e723-4178-b1fe-7c8e1d455840" />

```sql
<img width="1177" height="592" alt="image" src="https://github.com/user-attachments/assets/6297ed12-080a-4ef7-bcb5-27010259f809" />

```

**Output:**

<img width="1151" height="442" alt="image" src="https://github.com/user-attachments/assets/ee011b4a-138f-4fcd-875a-ee898d200cd2" />


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
