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
Write a SQL query to  find the average salary of all employees?

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```sql
SELECT avg(income) AS Average_Salary FROM employee

```

**Output:**
<img width="1237" height="398" alt="image" src="https://github.com/user-attachments/assets/ef6a0e71-5396-43f2-beb8-78e69b546fb7" />


**Question 2**

Write a SQL query to count the number of customers. Return number of customers.

Sample table: customer

customer_id |   cust_name    |    city    | grade | salesman_id 

-------------+----------------+------------+-------+-------------

        3002 | Nick Rimando   | New York   |   100 |        5001

        3007 | Brad Davis     | New York   |   200 |        5001

        3005 | Graham Zusi    | California |   200 |        5002

```sql
SELECT count(customer_id) AS COUNT FROM customer

```

**Output:**

<img width="1237" height="405" alt="image" src="https://github.com/user-attachments/assets/2ff1c1c7-5341-407b-b6cb-8229bf45d55f" />


**Question 3**
---

Write a SQL query that counts the number of unique salespeople. Return number of salespeople.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001


```sql
SELECT COUNT(DISTINCT salesman_id) AS COUNT FROM orders
```

**Output:**
<img width="1240" height="400" alt="image" src="https://github.com/user-attachments/assets/0c9cd8b1-c0be-43e7-8e6d-1b457d24e1ad" />


**Question 4**
---
Write a SQL Query to find how many medications are prescribed for each patient?

Sample table:MedicalRecords Table

```sql
SELECT PatientID , count(Medications) AS AvgMedications FROM MedicalRecords group by PatientID

```

**Output:**

<img width="1236" height="691" alt="image" src="https://github.com/user-attachments/assets/8fb51ed1-a61f-4f95-bfa7-69907c0e6f25" />


**Question 5**
---
What is the average duration of insurance coverage for patients covered by each insurance company?

Sample table:Insurance Table

name               type
-----------------  ----------
InsuranceID        INTEGER
PatientID          INTEGER
InsuranceCompany   TEXT
PolicyNumber       TEXT
PolicyHolder       TEXT
StartDate          DATE
EndDate            DATE

```sql

SELECT InsuranceCompany, AVG(EndDate - StartDate) AS AvgCoverageDurationDays FROM Insurance GROUP BY InsuranceCompany
```

**Output:**

<img width="1241" height="770" alt="image" src="https://github.com/user-attachments/assets/b6a9ba15-6697-44d4-ac84-08b25b3d0f25" />


**Question 6**
---
Write a SQL query to Calculate the average income of the employees with names starting with 'A': 

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```sql
SELECT avg(income) AS avg_income FROM employee WHERE name LIKE ('A%');

```

**Output:**

<img width="1239" height="399" alt="image" src="https://github.com/user-attachments/assets/bc20a5a5-9eb2-4f8c-8f9a-fc4253650374" />


**Question 7**
---
Write a SQL query to find the youngest employee in the company?

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```sql

SELECT name AS Employee_Name , age AS Age FROM employee ORDER BY Age ASC LIMIT 1;
```

**Output:**

<img width="1231" height="401" alt="image" src="https://github.com/user-attachments/assets/4df50435-4694-4a6c-b9ed-56e1aed791d7" />



**Question 8**
---
Write a SQL query to identify the cities (addresses) where the average salary is greater than Rs. 5000, as per the "customer1" table.

Sample table: customer1

```sql

SELECT address,AVG(salary) FROM customer1 GROUP BY address HAVING salary > 5000
```

**Output:**

<img width="1239" height="527" alt="image" src="https://github.com/user-attachments/assets/85976177-727d-4ea5-9e04-356fa7fe52c5" />


**Question 9**
---

Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the maximum work hours for each date, and excludes dates where the maximum work hour is not greater than 12.

Sample table: employee1

```sql
SELECT jdate,MAX(workhour) FROM employee1 GROUP BY jdate HAVING workhour > 12

```

**Output:**

<img width="1239" height="470" alt="image" src="https://github.com/user-attachments/assets/3a92b15f-a631-43ea-8ca0-d7dfece4a43c" />


**Question 10**
---
Write the SQL query that achieves the grouping of data by age, calculates the minimum income for each age group, and includes only those age groups where the minimum income is less than 1,000,000.

Sample table: employee

```sql
SELECT age,MIN(income) as Income FROM employee GROUP BY age HAVING income < 1000000

```

**Output:**

<img width="1236" height="525" alt="image" src="https://github.com/user-attachments/assets/2c07f528-26c9-48e8-bb9e-fc3822d4bdd5" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
