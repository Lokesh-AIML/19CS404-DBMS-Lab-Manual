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

Developed By : Lokeshwaran S

Register No : 212224240080

**Question 1**
--
<img width="1224" height="818" alt="image" src="https://github.com/user-attachments/assets/bbff7c23-f31d-417e-ac88-7ee5f0e66e96" />


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;

```

**Output:**

<img width="1153" height="444" alt="image" src="https://github.com/user-attachments/assets/e762aca3-7f1c-47c9-9844-e34b0254050d" />


**Question 2**
---
<img width="891" height="460" alt="image" src="https://github.com/user-attachments/assets/5114ba27-9f68-48a4-a2c1-0df7fed27d92" />


```sql
SELECT 
    name
FROM 
    customer
WHERE 
    phone IN (
        SELECT 
            phone
        FROM 
            customer
        GROUP BY 
            phone
        HAVING 
            COUNT(phone) = 1
    );
```

**Output:**

<img width="612" height="451" alt="image" src="https://github.com/user-attachments/assets/04883ee2-6bb8-440b-81a1-fb00fbe1dacf" />


**Question 3**
---


```sql
select * from CUSTOMERS where AGE < 30;
```

**Output:**

<img width="1166" height="538" alt="image" src="https://github.com/user-attachments/assets/97c5f1c8-345a-4dc7-9f17-a15a0bcdb114" />


**Question 4**
---
<img width="1280" height="635" alt="image" src="https://github.com/user-attachments/assets/c4ccbba2-7427-4a78-9c1c-8310918b0add" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE city = 'New York'
);

```

**Output:**



**Question 5**
---
<img width="1068" height="502" alt="image" src="https://github.com/user-attachments/assets/56192822-c519-4b46-9c48-94722fdd7f26" />


```sql
SELECT student_id, student_name, subject, grade
FROM GRADES
WHERE (subject, grade) IN (
    SELECT subject, MAX(grade)
    FROM GRADES
    GROUP BY subject
);

```

**Output:**

<img width="1164" height="418" alt="image" src="https://github.com/user-attachments/assets/d77d6a80-7016-41e4-b8d9-19c6329fa083" />


**Question 6**
---
<img width="765" height="395" alt="image" src="https://github.com/user-attachments/assets/6317f24b-7dc0-4080-8b44-24727a1785c4" />


```sql
SELECT *
FROM Medications
WHERE dosage = (
    SELECT MAX(dosage)
    FROM Medications
);

```

**Output:**

<img width="781" height="382" alt="image" src="https://github.com/user-attachments/assets/6cd6d9d8-1ae2-4934-8bee-733fd48bc7c8" />


**Question 7**
---
<img width="782" height="506" alt="image" src="https://github.com/user-attachments/assets/8ab89ef1-d51e-4f47-a13e-eb6c2cf29e90" />


```sql
select * from CUSTOMERS where ADDRESS = "Delhi";
```

**Output:**

<img width="1026" height="352" alt="image" src="https://github.com/user-attachments/assets/20b85967-e739-4f41-bd94-f45fce3619d2" />


**Question 8**
---
<img width="942" height="446" alt="image" src="https://github.com/user-attachments/assets/854e6b24-a6d5-447e-8003-7693702dbe01" />


```sql
SELECT name, city
FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="682" height="450" alt="image" src="https://github.com/user-attachments/assets/e7c1f8bc-8d6f-4c9d-94be-96322bef04d5" />


**Question 9**
---
<img width="888" height="513" alt="image" src="https://github.com/user-attachments/assets/9d766409-f9c3-4ba9-be84-2efa6bd0668b" />


```sql
select * from CUSTOMERS where ADDRESS = "Delhi" and AGE < 30 group by ID;
```

**Output:**

<img width="1134" height="361" alt="image" src="https://github.com/user-attachments/assets/fdb9a81b-1624-4cf0-90bc-8e3af0cda583" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
