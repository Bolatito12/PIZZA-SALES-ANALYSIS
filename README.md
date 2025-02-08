# PIZZA-SALES-ANALYSIS
This project focuses on analyzing pizza sales data to uncover key insights about customer preferences, sales trends, and revenue performance. Using data visualization tools such as Power BI, the goal is to identify the best-selling pizza types, peak sales periods, and factors influencing sales growth.

## Project Objective:
The objective of this project is to analyze pizza sales data to gain insights into sales performance, customer preferences, and operational efficiency. This will be achieved through data visualization and reporting using Power BI.

## Data Used
-	<a href="https://mavenanalytics.io/data-playground?order=date_added%2Cdesc&search=PIZZA">Dataset</a>


## Key Problems
1. How many customers do we have each day? Are there any peak hours?

2. How many pizzas are typically in an order? Do we have any bestsellers?

3. How much money did we make this year? Can we indentify any seasonality in the sales?

4. Are there any pizzas we should take of the menu, or any promotions we could leverage?


## Data Cleaning  and Transformation
In this Pizza Sales Analysis project, tables were joined using data modeling in Power BI to establish relationships between different datasets. The goal was to create a structured model that enables efficient data analysis and reporting.

## Identifying Key Tables
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

- price = RELATED(pizza[price])

- count of pizza = COUNTA(pizza[Pzza Type])

- Total Price = OrderDetails[Quantity]*OrderDetails[price]

- Total Revenue = SUM(OrderDetails[Total Price])

- Total Order = COUNTA(orders[order_id])

- Average order = [Total Revenue]/[Total Order]

- Order per day = [Total Order]/DISTINCTCOUNT(orders[date].[Date])

- Order per month = [Total Order]/DISTINCTCOUNT(orders[Month])

- Order per quarter = [Total Order]/DISTINCTCOUNT(orders[Quarter])

- Revenue per Day = [Total Revenue]/DISTINCTCOUNT(orders[date])

- Revenue per Month = [Total Revenue]/DISTINCTCOUNT(orders[month])

  <img width="885" alt="new pizza" src="https://github.com/user-attachments/assets/5211d160-aeb6-489a-9164-588ab02ad56d" />



  ##Key Insights & Business Implications
1️ Sales Performance Analysis

Total Revenue: $817.86K

Indicates a strong sales performance, but further analysis is needed to understand peak periods and slow seasons.

Average Order Value: $38.31

Helps in setting pricing strategies and upselling opportunities.

Revenue Per Day: $2.28K

Gives insight into daily sales trends and whether promotions or discounts impact daily revenue.

🔹 Problem Solved: Helps in understanding overall financial performance and making pricing adjustments if necessary.

2️  Revenue & Order Trends
Revenue by Month:
Shows fluctuations, with peaks in July ($73K) and dips in October ($64K).
Identifies seasonality trends, which can be used to optimize promotions and marketing efforts.
Total Orders by Hour:
Peak order times are around 12 PM - 2 PM and 6 PM - 8 PM.
Suggests higher demand during lunch and dinner hours.
Order by Day:
Friday (3.5K orders) and Saturday (3.2K orders) are the busiest days, indicating a weekend sales boost.
🔹 Problem Solved: Helps in scheduling staff efficiently, optimizing marketing for peak hours, and running targeted promotions during slow periods.

3️⃣ Product Performance & Preferences
Best-Selling Pizzas:
Thai Chicken Pizza ($43,434.25) is the the highest revenue-generating items while Brie Carre Pizza ($11,588.50) are the lowest revenue-generating items.
The high revenue generating item should be promoted further, and similar flavors can be explored.
% Total Price by Size:
Large (45.89%) and Medium (30.49%) pizzas generate the most revenue.
Small and XL pizzas contribute less, which may indicate pricing or customer preference issues.
% Total Order by Categories:
Classic (29.02%) and Supreme (23.89%) are the most preferred pizza categories.
Chicken and Veggie pizzas have lower sales, indicating a possible opportunity for better marketing or recipe adjustments.
🔹 Problem Solved: Guides menu optimization, pricing adjustments, and promotional strategies to maximize revenue.

4️⃣ Operational Efficiency & Inventory Management
Order Trends by Hour & Day:
Peak times and days indicate when ingredient demand is highest, helping in better inventory planning.
Reduces waste by forecasting demand more accurately.
🔹 Problem Solved: Helps in reducing food waste, preventing ingredient shortages, and optimizing kitchen efficiency.

How This Dashboard Solves Business Problems
Problem	Insight from Dashboard	Solution
Fluctuating Sales	Revenue trends show peaks and dips	Run targeted promotions during slow months
Staffing Issues	Peak order times identified	Adjust staff shifts based on high demand hours
Low-Performing Items	Some pizza categories have lower sales	Improve recipes, offer discounts, or remove them
Inventory Waste	Demand by day & size identified	Optimize inventory stocking based on demand
Customer Preferences	Large pizzas & Classic/Supreme categories sell best	Focus marketing on high-demand pizzas

# Final Recommendations
✅ Optimize Promotions: Offer discounts during slow months (e.g., October) to increase sales.
✅ Improve Inventory Management: Stock more ingredients for peak times (lunch & dinner).
✅ Focus on Popular Products: Promote best-sellers and experiment with new flavors similar to them.
✅ Enhance Staffing Strategy: Ensure more staff are available on Fridays & weekends.




