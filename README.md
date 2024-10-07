# SQL-Multiple-Table-Project-on--Ecommerce-Dataset

### Here are five problem statements you can explore using the E-commerce Order Dataset from Kaggle to practice SQL joins:

1. Analyze Total Sales by Product Category

---

Problem: Calculate the total sales amount for each product category.

Details: Join the orders table with the products table on the product_id to aggregate the sales amount by category. This will help in understanding which categories generate the most revenue.

SQL Concept: INNER JOIN, GROUP BY, SUM()

---

2. Identify Customers with the Most Orders

---

Problem: Find the top 10 customers who have placed the most orders.

Details: Join the customers table with the orders table using the customer_id. Count the number of orders for each customer to identify the most active ones.

SQL Concept: INNER JOIN, GROUP BY, COUNT(), ORDER BY

---

3. Determine the Average Order Value by Country

---

Problem: Calculate the average order value for each country.

Details: Join the orders table with the customers table on customer_id, and then group the results by country to find the average order amount.

SQL Concept: INNER JOIN, AVG(), GROUP BY

---

4. Find Products with Low Inventory and High Sales

---

Problem: Identify products that have low inventory levels but high sales figures.

Details: Join the products table with the order_items table to get sales data and filter the results to show only products with inventory below a certain threshold and high total sales.

SQL Concept: INNER JOIN, SUM(), WHERE

---

5. Explore the Relationship Between Customer Location and Product Preferences

---

Problem: Analyze how customer locations influence product preferences by examining which products are popular in specific regions.

Details: Join the customers, orders, and order_items tables to group and count the number of each product sold by region.

SQL Concept: INNER JOIN, GROUP BY, COUNT()
These problem statements will give you hands-on experience with SQL joins and aggregations, allowing you to extract meaningful insights from the dataset while practicing your SQL skills.
