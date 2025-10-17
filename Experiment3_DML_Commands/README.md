# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

Developed by : Lokeshwaran S

Register No : 212224240080

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
<img width="1171" height="703" alt="image" src="https://github.com/user-attachments/assets/f1e8e700-4878-4692-99f8-b1a609cea371" />
   

```sql
update Products
set reorder_lvl = reorder_lvl - (reorder_lvl * 0.3) where cost_price > 50 and quantity < 100;
```

**Output:**

<img width="1773" height="367" alt="image" src="https://github.com/user-attachments/assets/d7c434d6-74a9-4381-a5a9-2bee697be6f5" />


**Question 2**
---
<img width="859" height="101" alt="image" src="https://github.com/user-attachments/assets/a5fdb9ab-945f-42ea-8591-dce6beffeb8f" />


```sql
update Customer set grade = 5 where city = "Chennai";
```

**Output:**

<img width="1847" height="565" alt="image" src="https://github.com/user-attachments/assets/12baa09f-201e-44ac-a1ba-9ee2add205f6" />


**Question 3**
---
<img width="1085" height="340" alt="image" src="https://github.com/user-attachments/assets/50698e59-84ff-4791-8df1-f2e334984709" />


```sql
update Products
set product_name = "Premium Bread" where product_id = 5;
```

**Output:**

<img width="1795" height="356" alt="image" src="https://github.com/user-attachments/assets/de24be37-2c85-4faf-975b-b036822533a9" />


**Question 4**
---
<img width="758" height="167" alt="image" src="https://github.com/user-attachments/assets/24962628-c846-426e-b4a6-8b7f0ae90d1d" />


```sql
update Products
set product_name = "Grapefruit" where product_id = 4;
```

**Output:**

<img width="1001" height="246" alt="image" src="https://github.com/user-attachments/assets/5fe7f1f0-8a5f-4225-8f51-65d3e1b48e42" />


**Question 5**
---
<img width="734" height="217" alt="image" src="https://github.com/user-attachments/assets/74b82962-690f-46eb-9bd5-38f3d7e5a145" />


```sql
update sales
set sell_price = sell_price + (sell_price * 0.05) where product_id = 15 and sale_date = '2023-01-31';
```

**Output:**

<img width="1905" height="375" alt="image" src="https://github.com/user-attachments/assets/610b780f-191d-41f1-9cab-aa819c313840" />


**Question 6**
---
<img width="1204" height="365" alt="image" src="https://github.com/user-attachments/assets/fddfa71f-157c-4e1b-8e0c-137e269a6475" />


```sql
delete from customer where CUST_COUNTRY not in('India' , 'USA');
```

**Output:**

<img width="1379" height="466" alt="image" src="https://github.com/user-attachments/assets/30eef360-99cb-4603-a322-594d4ad7642c" />


**Question 7**
---
<img width="1884" height="383" alt="image" src="https://github.com/user-attachments/assets/cb94c44b-3900-4411-8d3e-84c3169ca2e9" />


```sql
delete from customer
where OPENING_AMT >= 4000 AND OPENING_AMT <= 6000;
```

**Output:**

<img width="723" height="392" alt="image" src="https://github.com/user-attachments/assets/c9b20118-6a4f-42cf-927b-aa6881e8fd5f" />


**Question 8**
---
<img width="810" height="397" alt="image" src="https://github.com/user-attachments/assets/c1688230-233f-40fe-88fa-2c88cb4f673c" />


```sql
delete from Doctors
where doctor_id >= 2 and doctor_id <= 4;
```

**Output:**

<img width="1165" height="767" alt="image" src="https://github.com/user-attachments/assets/07dbecf2-c454-4c9c-8c74-49d6a5e68ddf" />


**Question 9**
---
<img width="832" height="547" alt="image" src="https://github.com/user-attachments/assets/88e8588c-33d9-4476-a6c2-ec2d617de375" />


```sql
delete from surgeries where surgery_id = 3 or surgeon_id = 4;
```

**Output:**

<img width="1124" height="822" alt="image" src="https://github.com/user-attachments/assets/5b66398a-0ba1-4b73-8fc7-51e29721363a" />


**Question 10**
---
<img width="1430" height="565" alt="image" src="https://github.com/user-attachments/assets/bb841b47-b3b7-463a-8d55-e75488a53c82" />


```sql
delete from customer
where LENGTH(CUST_NAME) = 6;
```

**Output:**

<img width="1877" height="490" alt="image" src="https://github.com/user-attachments/assets/2b3f29b0-5390-41b4-9bf6-416b3ceb60b0" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
