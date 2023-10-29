# Business Problem Statement:

As a data analyst in Apple's Online Store team, the goal is to analyze customer behavior and interactions with the online platform to enhance the user experience, optimize the website layout, and improve product recommendations. Through the analysis of browsing behavior, purchase trends, and customer feedback, insights can be derived to refine the online shopping experience and potentially boost sales and customer satisfaction.

## Data Tables:

**Table 1: CustomerInteractions**

| Feature Name    | Feature Description              | Feature Data Type | Comments |
|-----------------|----------------------------------|-------------------|----------|
| interaction_id  | Unique Interaction ID            | int               | Primary Key |
| customer_id     | Customer ID                      | int               | |
| session_id      | Browsing Session ID              | int               | |
| page_viewed     | Page Viewed by Customer         | varchar           | |
| timestamp       | Timestamp of Interaction         | datetime          | |
| action_type     | Type of Action (View, Click, etc.)| enum              | Values: View, Click, Add_to_Cart, Purchase |
| product_id      | Product ID Interacted With       | int               | |

**Table 2: ProductCatalog**

| Feature Name    | Feature Description              | Feature Data Type | Comments |
|-----------------|----------------------------------|-------------------|----------|
| product_id      | Unique Product ID                | int               | Primary Key |
| product_name    | Name of Product                  | varchar           | |
| category        | Category of Product              | varchar           | |
| price           | Price of Product                 | float             | |
| stock_level     | Stock Level                      | int               | |

## SQL Assessment Questions:

**Question 1:**
- **Topics and Operations:** Aggregation, Ordering, Filtering  
- **Scenario:** We want to identify the most viewed products in our online store to ascertain the popularity and visibility of different products.  
- **Task:** Write a SQL query to find the top 5 most viewed products along with the number of views, ordered by the number of views in descending order.

**Question 2:**

- **Topics and Operations:** Join Operations, Aggregation, Grouping  
- **Scenario:** Based on the interactions data, we aim to understand the correlation between page views and purchases to help optimize our product placements and recommendations.  
- **Task:** Write a SQL query to find the total number of views and purchases for each product, grouped by product, and order the result by the number of purchases in descending order. (limit the output to 5 rows)

**Question 3:**
- **Topics and Operations:** Subqueries, Join Operations, Filtering  
- **Scenario:** From the insights gathered, we suspect that products from certain categories are more popular among customers. We want to analyze the interaction data to confirm this hypothesis.  
- **Task:** Write a SQL query to find the total number of interactions (views, clicks, add to cart, purchases) for each category of products, and order the result by the total number of interactions in descending order.