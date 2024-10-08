# SQL-Multiple-Table-Project-on--Ecommerce-Dataset

## Project Overview
This project utilizes an E-commerce Order Dataset to extract insights through SQL queries. The dataset contains comprehensive information about orders, items, customers, payments, and products on an e-commerce platform. It is structured with multiple tables, each providing specific details on different aspects of the platform's operations.

### The E-commerce Order Dataset provides comprehensive information related to orders, items within orders, customers, payments, and products for an e-commerce platform. This dataset is structured with multiple tables, each containing specific information about various aspects of the e-commerce operations.
[Dataset Source](https://www.kaggle.com/datasets/bytadit/ecommerce-order-dataset)

#### Problem Statements Explored:

##### 1. Analyze Total Sales by Product Category

Problem: Calculated the total sales amount for each product category.

```mysql
SELECT product_category_name as Product , SUM(payment_value) as Total_sales
FROM orderitems
JOIN payments 
ON orderitems.order_id = payments.order_id
JOIN products 
ON orderitems.product_id = products.product_id
GROUP BY product_category_name
ORDER BY Total_sales DESC;
```

##### Visualization: 

![Total Sales by Product Catagory](https://github.com/user-attachments/assets/3c505374-283c-4f7d-95a5-220117b62fc2)


##### SQL Concept: INNER JOIN, GROUP BY, SUM()

---

##### 2. Identify Customers with the Most Orders

Problem: Find the top 10 customers who have placed the most orders.

```mysql
SELECT COUNT(order_id) as Total_orders, customers.customer_id AS Top_customer
FROM orders
JOIN customers 
ON orders.customer_id = customers.customer_id
GROUP BY Top_customer
ORDER BY Total_orders DESC
LIMIT 10;
```
##### Visualization: ![top 10 customers who have placed the most orders](https://github.com/user-attachments/assets/c2d6f829-3492-4c64-a3fa-720d0a13be43)


##### SQL Concept: INNER JOIN, GROUP BY, COUNT(), ORDER BY

---

##### 3. Determine the Average Order Value by Country

Problem: Calculate the average order value for each country.

```mysql
SELECT AVG(payment_value) AS Average_order_value, customer_state
FROM payments
JOIN orders
ON payments.order_id = orders.order_id
JOIN customers
ON orders.customer_id = customers.customer_id
GROUP BY customer_state;
```

##### Visualization: ![image](https://github.com/user-attachments/assets/5a3a37ee-41a8-45aa-af13-8c67d773653f)


##### SQL Concept: INNER JOIN, AVG(), GROUP BY

---


#### 4. Explore the Relationship Between Customer Location and Product Preferences



Problem: Analyze how customer locations influence product preferences by examining which products are popular in specific regions.

```mysql
SELECT COUNT(od.order_id) AS total_orders, p.product_category_name, c.customer_state
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
JOIN orderitems od ON od.order_id = o.order_id
JOIN products p ON od.product_id = p.product_id
GROUP BY c.customer_state, p.product_category_name;
```
##### Visualization: ![how customer locations influence product preferences by examining which products are popular in specific regions](https://github.com/user-attachments/assets/76bca5a9-bdf0-440c-962c-7c7bc6b44dc7)


#### SQL Concept: INNER JOIN, GROUP BY, COUNT()

^These problem statements will give you hands-on experience with SQL joins and aggregations, allowing you to extract meaningful insights from the dataset while practicing your SQL skills.
