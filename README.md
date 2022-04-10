# Introduction

OList is an e-commerce company that has faced some losses recently. It wants to manage its inventory very well so as to reduce any unnecessary costs that it might be bearing. It needs to identify the product categories to get rid of without significantly impacting business.


# Objective

- To identify top products that contribute to the revenue
- Analyse the customer purchase behaviour to estimate what items are more likely to be purchased individually or in combination with some other products
- Provide recommendations for better inventory management so as to reduce any unnecessary costs 


# Assumption

•	Only the cases having order status as 'delivered' are to be considered.
•	The columns ‘order_approved_at’ and ‘order_delivered_timestamp’ are assumed to be equivalent to/same as the columns ‘order_purchase_timestamp’ and ‘order_estimated_delivery_date’ respectively.
•	Only those categories which are ordered more than 5 times are considered for creating category association as part of market basket analysis.


# Data Cleaning

##### •	Orders:

- Only the orders with order status as ‘delivered’ are considered for this case study since 97% of the records are successfully delivered. 
- he missing values for ‘order_approved_at’ are replaced with respective ‘order_purchase_timestamp’.
- Similarly, the missing values for ‘order_delivered_timestamp’ are replaced with respective ‘order_estimated_delivery_date’.

##### •	Customer:

- For redundant customer records, only the first occurrence is kept and the duplicated ones are removed.

##### •	Products:

- The missing product category has been replaced with the mode i.e. ‘toys’ as almost 75% of the records belong to ‘toys’ category.
- For product width, length, height and weight, as the data is right-skewed and there is no significant outlier, instead of using mean, the respective median values are used to replace the missing values.


# EDA and Visualizations

Exploratory data analysis is performed on the OList data to identify various patterns in customer purchase behaviour. The visualizations are plotted using Tableau.

##### •	Top 20 products based on revenue generated and number of orders placed

![image](https://user-images.githubusercontent.com/103338455/162641460-56a0dff3-acea-4c0d-b9f1-a314629d285c.png)

- The highest revenue generated  is 63,885.
- The product that generated highest revenue belongs to the Toys category.
- Most of the products in the top 20 list belong to the toys category.

![image](https://user-images.githubusercontent.com/103338455/162641468-69bc21ea-2940-4bfa-b8e2-67027d72118d.png)

- The most ordered product has been purchased 467 times.
- Some products are purchased frequently despite of the high price.

##### •	Number of orders per category

![image](https://user-images.githubusercontent.com/103338455/162641483-ba2974f5-fc58-46d1-b164-4fdc5be4c114.png)

- The Toys category is the most ordered category with a total  74,929 orders.
- The categories here are filtered to show only the top 20 which are ordered more than 5 times.

##### •	Total number of orders and percentage of total running revenue for each product

![image](https://user-images.githubusercontent.com/103338455/162641492-62a0b28c-e9dd-4b7b-a4f3-9c4238132293.png)

- This Revenue Pareto shows the percentage of total running revenue, revenue generated and number of orders for each product id.
- It can be used to identify the contribution of the products towards total revenue.


# Market Basket Analysis

![image](https://user-images.githubusercontent.com/103338455/162641575-1fb21e24-14eb-446b-8ebf-57081cc4a67c.png)

- Market basket analysis is performed to identify the frequently ordered category association.
- Toys are often purchased with various other categories as shown in this Market Basket Analysis.


# Ideal Category Depth

![image](https://user-images.githubusercontent.com/103338455/162641638-04809218-8db1-4db3-a877-2480533bf75e.png)

- Revenue pareto analysis is performed to understand ideal category depth for each category.


# Inferences

•	The category ‘toys’ is the most ordered category as it is ordered 74929 times (76% of the total number of orders)
•	Apart from ‘toys’, the categories ‘health_beauty’,’bed_bath_table’,’sports_leisure’, ‘computer_accessories’ and ‘furniture_decor’ are the most frequently ordered categories.The above categories with ‘toys’ or/and with each other are most frequent in customers’ basket.
•	It is observed that despite of the high price, some products are frequently purchased by the customers.


# Recommendations

•	Target customers who have children to boost up sales as they are most likely to purchase ‘toys’ which is the most ordered category. 
•	Offer Promo-codes or discounts on frequently ordered category associations and the most ordered products to attract more customers.
•	Consider the ideal category depth to minimize the inventory cost by getting rid of the products which are seldom ordered and/or do not have a significant contribution to the total revenue under each product category. 

