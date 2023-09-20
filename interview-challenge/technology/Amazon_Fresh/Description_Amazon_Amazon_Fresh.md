# Business Problem Statement:
With the growth of Amazon Fresh, we've identified that certain products are frequently added to carts but are not checked out. This leads to potential loss in sales and also may indicate some pain points or hesitations in our customer's shopping journey. The aim is to identify these products, understand patterns, and create strategies to increase conversion.

## Data Tables:

**Table 1: Orders**

| Column Name      | Description                                 | Feature Type |
|------------------|---------------------------------------------|--------------|
| order_id         | Unique identifier for each order            | Integer      |
| customer_id      | Unique identifier for each customer         | Integer      |
| product_id       | ID of the product added to the cart         | Integer      |
| add_to_cart_time | Timestamp when the product was added to cart| Timestamp    |
| checkout_time    | Timestamp when the order was checked out    | Timestamp    |

**Table 2: Products**

| Column Name      | Description                     | Feature Type  |
|------------------|---------------------------------|---------------|
| product_id       | Unique identifier for a product | Integer       |
| product_name     | Name of the product             | Text          |
| product_category | Category the product belongs to | Text          |

## Questions:

### Question 1 (Data Cleaning & Exploration):

**Scenario**:
You notice that some `add_to_cart_time` entries have different date formats. Additionally, some products have `checkout_time` before the `add_to_cart_time`, which might be system errors or outliers.

**Question**:
Given the Orders table, identify and list the `order_id` which have inconsistent date formats or where the `checkout_time` is earlier than the `add_to_cart_time`. What steps would you take to clean these records?

### Question 2 (SQL Queries):

**Scenario**:
The marketing department wishes to create a personalized email campaign for products that are frequently added to carts but not checked out.

**Question**:
Using the Orders and Products tables, write an SQL query to retrieve the top 10 `product_names` that have the highest count of being added to carts but not checked out in the past one year (lastest day is `09/08/2023`). Use Common Table Expressions (CTE's) and Window functions for this task.

### Question 3 (Product & Business Sense):

**Scenario**:
The finance team is alarmed by the observation that the actual revenue from certain product categories in Amazon Fresh is significantly lower than the predicted revenue.

**Question**:
Using the data available, how would you approach understanding the variance between predicted and actual sales for specific product categories? List down the potential factors you'd investigate and how the findings could inform the strategy to bridge the revenue gap.
