# PIZZA-SALES-ANALYSIS
This project focuses on analyzing pizza sales data to uncover key insights about customer preferences, sales trends, and revenue performance. Using data visualization tools such as Power BI, the goal is to identify the best-selling pizza types, peak sales periods, and factors influencing sales growth.

## Project Objective:
The objective of this project is to analyze pizza sales data to gain insights into sales performance, customer preferences, and operational efficiency. This will be achieved through data visualization and reporting using Power BI.

# Data Used
-	<a href="https://mavenanalytics.io/data-playground?order=date_added%2Cdesc&search=PIZZA">Dataset</a>


## Key Problems
1. How many customers do we have each day? Are there any peak hours?

2. How many pizzas are typically in an order? Do we have any bestsellers?

3. How much money did we make this year? Can we indentify any seasonality in the sales?

4. Are there any pizzas we should take of the menu, or any promotions we could leverage?


## Data Cleaning  and Transformation
In this Pizza Sales Analysis project, tables were joined using data modeling in Power BI to establish relationships between different datasets. The goal was to create a structured model that enables efficient data analysis and reporting.

##Identifying Key Tables
The dataset contained multiple tables, including:

•	Orders Table – Contains order details such as order ID and Date.

•	Order Details Table – Contains item-level data, including order ID, pizza type, quantity, and price.

•	Pizzas Table – Lists pizza types, sizes, and Price.

•	Pizza Categories Table – pizzas Type, Name, categories such as "Veg" or "Non-Veg" and ingredient


## Defining Relationships Using Keys
Relationships were established based on primary and foreign keys:

•	Orders Table (Primary Key: OrderID) was linked to Order Details Table (Foreign Key: OrderID).

•	Order Details Table (Primary Key: PizzaID) was linked to Pizzas Table (Foreign Key: PizzaID).

•	Pizzas Table (Primary Key: PizzaType) was linked to Pizza Categories Table (Foreign Key: PizzaType).

## Cardinality and Relationship Type
•	The Orders Table and Order Details Table have a one-to-many relationship (one order can contain multiple pizzas).

•	The Order Details Table and Pizzas Table have a many-to-one relationship (many order items can reference one pizza type).

•	The Pizzas Table and Pizza Categories Table have a many-to-one relationship (many pizzas belong to one category).

•	The Orders Table and Customers Table have a many-to-one relationship (many orders belong to one customer).


## Created Measures in DAX
 – KPIs such as Total Sales, Average Order , and Popular Pizza Type were calculated using DAX in Power BI.

price = RELATED(pizza[price])

count of pizza = COUNTA(pizza[Pzza Type])

Total Price = OrderDetails[Quantity]*OrderDetails[price]

Total Revenue = SUM(OrderDetails[Total Price])

Total Order = COUNTA(orders[order_id])

Average order = [Total Revenue]/[Total Order]

Order per day = [Total Order]/DISTINCTCOUNT(orders[date].[Date])

Order per month = [Total Order]/DISTINCTCOUNT(orders[Month])

Order per quarter = [Total Order]/DISTINCTCOUNT(orders[Quarter])

Revenue per Day = [Total Revenue]/DISTINCTCOUNT(orders[date])

Revenue per Month = [Total Revenue]/DISTINCTCOUNT(orders[month])

