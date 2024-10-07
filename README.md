# SQL-Multiple-Table-Project-on--Ecommerce-Dataset

## The E-commerce Order Dataset provides comprehensive information related to orders, items within orders, customers, payments, and products for an e-commerce platform. This dataset is structured with multiple tables, each containing specific information about various aspects of the e-commerce operations.
[Dataset](https://www.kaggle.com/datasets/bytadit/ecommerce-order-dataset)

### Explored problem statements:

#### 1. Analyze Total Sales by Product Category



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

![Total Sales by Product Catagory](https://github.com/user-attachments/assets/3c505374-283c-4f7d-95a5-220117b62fc2)


SQL Concept: INNER JOIN, GROUP BY, SUM()

---

#### 2. Identify Customers with the Most Orders



Problem: Find the top 10 customers who have placed the most orders.

```
SELECT COUNT(order_id) as Total_orders, customers.customer_id AS Top_customer
FROM orders
JOIN customers 
ON orders.customer_id = customers.customer_id
GROUP BY Top_customer
ORDER BY Total_orders DESC
LIMIT 10;
```
![top 10 customers who have placed the most orders](https://github.com/user-attachments/assets/c2d6f829-3492-4c64-a3fa-720d0a13be43)


SQL Concept: INNER JOIN, GROUP BY, COUNT(), ORDER BY

---

#### 3. Determine the Average Order Value by Country



Problem: Calculate the average order value for each country.

```
SELECT AVG(payment_value) AS Average_order_value, customer_state
FROM payments
JOIN orders
ON payments.order_id = orders.order_id
JOIN customers
ON orders.customer_id = customers.customer_id
GROUP BY customer_state;
```

![image](https://github.com/user-attachments/assets/5a3a37ee-41a8-45aa-af13-8c67d773653f)


SQL Concept: INNER JOIN, AVG(), GROUP BY

---

#### 4. Find Products with Low Inventory and High Sales



Problem: Identify products that have low inventory levels but high sales figures.

Details: Join the products table with the order_items table to get sales data and filter the results to show only products with inventory below a certain threshold and high total sales.

SQL Concept: INNER JOIN, SUM(), WHERE

---

#### 5. Explore the Relationship Between Customer Location and Product Preferences



Problem: Analyze how customer locations influence product preferences by examining which products are popular in specific regions.

Details: Join the customers, orders, and order_items tables to group and count the number of each product sold by region.

SQL Concept: INNER JOIN, GROUP BY, COUNT()

^These problem statements will give you hands-on experience with SQL joins and aggregations, allowing you to extract meaningful insights from the dataset while practicing your SQL skills.
