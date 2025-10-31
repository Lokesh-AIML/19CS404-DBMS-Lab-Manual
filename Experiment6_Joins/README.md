# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

Developed By : Lokeshwaran S

Register No : 212224240080

**Question 1**
--
<img width="1311" height="577" alt="image" src="https://github.com/user-attachments/assets/10a7f1d4-740d-435f-9f41-a6a2ba04cd78" />


```sql
SELECT 
    n.nurse_id,
    d.department_name
FROM 
    nurses n
INNER JOIN 
    departments d
ON 
    n.department_id = d.department_id
WHERE 
    n.first_name = 'David'
    AND n.last_name = 'Moore';

```

**Output:**

<img width="640" height="389" alt="image" src="https://github.com/user-attachments/assets/b25153be-eaa8-484e-83e4-976ad3fbb479" />


**Question 2**
---


```sql
SELECT 
    c.cust_name,
    c.city,
    c.grade,
    s.name as "Salesman",
    s.city
FROM 
    customer c
INNER JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;

```

**Output:**

<img width="1308" height="808" alt="image" src="https://github.com/user-attachments/assets/692f801b-cd2a-4f02-9003-a0428d091b48" />


**Question 3**
---
<img width="1278" height="590" alt="image" src="https://github.com/user-attachments/assets/7811b07d-4c5e-4fdb-bdf7-f349a698cceb" />


```sql
SELECT 
    p.first_name AS patient_name,
    a.*
FROM 
    patients p
INNER JOIN 
    appointments a
ON 
    p.patient_id = a.patient_id;

```

**Output:**

<img width="1187" height="392" alt="image" src="https://github.com/user-attachments/assets/6afcd892-713c-4551-a04e-da9c2352c965" />


**Question 4**
---
<img width="1253" height="502" alt="image" src="https://github.com/user-attachments/assets/19804be7-5741-4c65-b763-3893bbae83b2" />


```sql
SELECT 
    c.cust_name
FROM 
    customer c
LEFT JOIN 
    orders o
ON 
    c.customer_id = o.customer_id;

```

**Output:**

<img width="476" height="781" alt="image" src="https://github.com/user-attachments/assets/d7aa668e-b001-4c12-a38c-912c18383dfb" />


**Question 5**
---
<img width="1337" height="469" alt="image" src="https://github.com/user-attachments/assets/05239040-973f-4a70-8811-52b31af740ba" />


```sql
SELECT 
    p.*
FROM 
    patients p
INNER JOIN 
    doctors d
ON 
    p.doctor_id = d.doctor_id
WHERE 
    d.first_name = 'John'
    AND d.last_name = 'Smith';

```

**Output:**

<img width="1364" height="300" alt="image" src="https://github.com/user-attachments/assets/0a995592-cfb4-4bee-8104-b1c87b50f638" />


**Question 6**
---
<img width="1152" height="785" alt="image" src="https://github.com/user-attachments/assets/83b6ce92-e30d-401c-9ca7-77ced493c573" />


```sql
SELECT 
    o.ord_no, 
    o.purch_amt, 
    c.cust_name, 
    c.city
FROM 
    orders o
JOIN 
    customer c 
ON 
    o.customer_id = c.customer_id
WHERE 
    o.purch_amt BETWEEN 500 AND 2000;

```

**Output:**

<img width="1236" height="459" alt="image" src="https://github.com/user-attachments/assets/502e945c-3605-49a6-a911-d8a31cd27539" />


**Question 7**
---
<img width="849" height="893" alt="image" src="https://github.com/user-attachments/assets/b9a7203c-4552-4331-87c2-3ce8f60dc0b7" />


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders o
INNER JOIN customer c 
    ON o.customer_id = c.customer_id
INNER JOIN salesman s 
    ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1115" height="532" alt="image" src="https://github.com/user-attachments/assets/3e5dfce9-ddd2-40b8-b74b-f54013ddc0a9" />


**Question 8**
---


```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c
    ON s.salesman_id = c.salesman_id
WHERE c.city = 'London';

```

**Output:**

<img width="463" height="453" alt="image" src="https://github.com/user-attachments/assets/6c2a85b0-c1a7-4f01-a1f2-2836b8737c83" />


**Question 9**
---
<img width="1308" height="720" alt="image" src="https://github.com/user-attachments/assets/d4eded6e-876d-41a5-84b7-ca946170565a" />


```sql
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS "Salesman",
    s.city,
    s.commission
FROM customer c
JOIN salesman s
    ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;

```

**Output:**

<img width="1308" height="571" alt="image" src="https://github.com/user-attachments/assets/9aa4e3c9-5f67-4aa0-99f3-de9b8c2b8e7c" />


**Question 10**
---
<img width="1011" height="896" alt="image" src="https://github.com/user-attachments/assets/dfd316cc-9d53-4e34-9ca0-54a191425805" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**




## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
