# 📚SQL Retail & Sales Analysis – Northwind Database

## Overview
This project was completed as part of a **Data Technician bootcamp** and focuses on analysing retail and sales data using SQL.  
Using the **Northwind Traders** relational database, I wrote and executed a range of SQL queries to extract meaningful business insights related to customers, orders, products, suppliers, and sales performance.

The project demonstrates core SQL skills required for **entry-level data roles**, including data administrators and junior data analysts, with an emphasis on querying structured relational databases using MySQL.

---

## Tools & Technologies
- **SQL**
- **MySQL**
- **MySQL Workbench**
- **Northwind sample database**
- **GitHub** (project documentation and version control)

---

## Key SQL Skills Demonstrated

### Data Retrieval & Filtering
- Writing queries using `SELECT` to retrieve relevant columns
- Filtering data using `WHERE`, `BETWEEN`, `IN`, and logical operators (`AND`, `OR`)
- Sorting results using `ORDER BY`
- Removing duplicates using `DISTINCT`

### Aggregation & Analysis
- Grouping data using `GROUP BY`
- Applying aggregate functions such as:
  - `COUNT()`
  - `SUM()`
  - `AVG()`
- Generating insights such as product counts, total quantities ordered, and customer distributions

### Table Joins
- Using **INNER JOINs** to combine related tables
- Linking customers, orders, products, suppliers, categories, and employees
- Producing multi-table reports for business analysis

### Relational Database Concepts
- Working with structured relational data
- Understanding primary keys and foreign key relationships
- Querying real-world retail schemas commonly used in business environments

---

## Example Queries

### Retrieve Customer Names, Cities and Countries
```sql
SELECT CustomerName, City, Country
FROM Customers;
```
<img width="606" height="417" alt="image" src="https://github.com/user-attachments/assets/7b87ca1a-e0a6-4180-b6d5-c0ca21929f96" />


### Products Priced Above £50
```sql
SELECT *
FROM Products
WHERE Price > 50;
```

<img width="671" height="235" alt="image" src="https://github.com/user-attachments/assets/4c4bb625-78c7-4b55-8efe-620ccfd6dedf" />


### Orders with Customer and Employee Details
```sql
SELECT o.OrderID, o.OrderDate, c.CustomerName, e.FirstName, e.LastName
FROM Orders o
LEFT JOIN Customers c ON o.CustomerID = c.CustomerID
LEFT JOIN Employees e ON o.EmployeeID = e.EmployeeID;
```

<img width="612" height="412" alt="image" src="https://github.com/user-attachments/assets/1212e121-23ce-49ec-b511-3a73ee19d066" />


### Product Count by Category
```sql
SELECT c.CategoryName, COUNT(p.ProductID) AS Product_Count
FROM Categories c
LEFT JOIN Products p ON c.CategoryID = p.CategoryID
GROUP BY c.CategoryName;
```

<img width="260" height="207" alt="image" src="https://github.com/user-attachments/assets/22aba9f8-12e6-47f9-bc32-eacbe85201b9" />


### Total Quantity Ordered per Product
```sql
SELECT p.ProductID, p.Price, SUM(od.Quantity) AS Total_Quantity
FROM Products p
LEFT JOIN Order_Details od ON p.ProductID = od.ProductID
GROUP BY p.ProductID;
```

<img width="275" height="383" alt="image" src="https://github.com/user-attachments/assets/6f11206a-c91a-43b5-b168-2b6a9db8b5a8" />


## Key Learnings
- Gained hands-on experience querying a realistic retail database
- Improved confidence in writing clean, readable SQL queries
- Learned how to extract business-relevant insights from raw relational data
- Strengthened understanding of how SQL supports reporting, analysis, and operational decision-making
- Developed skills directly applicable to data administrator and junior data analyst roles
