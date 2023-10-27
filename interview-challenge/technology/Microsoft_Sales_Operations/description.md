# **Business Problem Statement:**
Sales Operations at Microsoft has been witnessing inconsistent sales across different regions. The management believes that by diving deep into the sales data, they can unearth patterns that could help in optimizing sales strategies. They want to understand which products are selling well in which regions, the impact of discounts on sales, and if there are any standout sales agents. As a data analyst, your role is to extract these insights from the sales data.

## **Data Tables:**

**1. SalesData**

| Feature Name     | Description                                           | Data Type     | Comments                     |
|------------------|-------------------------------------------------------|---------------|------------------------------|
| sale_id          | Unique identifier for each sale                       | int           | Primary Key                  |
| product_id       | Identifier for the product sold                       | int           | Foreign Key (from Products)  |
| agent_id         | Identifier for the sales agent                        | int           | Foreign Key (from Agents)    |
| region           | Region where the sale occurred                        | varchar       |                              |
| units_sold       | Number of units of the product sold                   | int           |                              |
| discount_applied | Discount percentage given on the product              | decimal(5,2)  |                              |
| sale_date        | Date on which the sale was made                       | date          |                              |

**2. Products**

| Feature Name     | Description                                           | Data Type     | Comments                     |
|------------------|-------------------------------------------------------|---------------|------------------------------|
| product_id       | Unique identifier for each product                    | int           | Primary Key                  |
| product_name     | Name of the product                                   | varchar       |                              |
| base_price       | Standard price of the product before any discount     | decimal(8,2)  |                              |

## Question:

**Question 1:**

*Topics and Operations:* Aggregation, Sorting

*Scenario:* The management wants to understand which products have been the top sellers in terms of units sold.

*Task:* Write a SQL query to find the top 3 products in terms of units sold.

**Question 2:**

*Topics and Operations:* Joining Tables, Aggregation, Filtering

*Scenario:* The management believes that giving discounts leads to higher sales. They want to analyze the relationship between the amount of discount given and the number of units sold for each product.

*Task:* Write a SQL query to find the average units sold for each product when a discount of more than 10% was applied. Also, return the product name from the Products table (limit the output to 5 rows).


**Question 3:**

*Topics and Operations:* Joining Tables, Aggregation, Pivoting

*Scenario:* To strategize region-specific sales campaigns, the management wants a region-wise break-up of sales for each product.

*Task:* Write a SQL query to pivot the sales data such that for each product, we get the total units sold in each region. The output columns should be product_name, region1, region2, ..., where each region column shows the total units sold in that region for the respective product.