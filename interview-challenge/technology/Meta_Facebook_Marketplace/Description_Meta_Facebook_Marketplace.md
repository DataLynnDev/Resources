# Business Problem Statement:
**How can we optimize product categorization in Facebook's Marketplace to enhance buyer's search experience and increase seller transactions?**

The Facebook Marketplace, a hub for buying and selling, has witnessed immense growth in recent years. However, with this expansion, there have been numerous challenges, especially regarding product categorization. An efficient categorization system can significantly improve buyer search experiences and potentially increase the number of transactions for sellers. By understanding user behavior, transaction trends, and product preferences, we can offer invaluable insights to optimize this system.

## Data Tables:

**Table 1: Product_Listings**

| Column Name | Description | Feature Type |
|-------------|-------------|--------------|
| product_id  | Unique identifier for the product | Numeric |
| seller_id   | Unique identifier for the seller | Numeric |
| category    | Category of the product | Categorical |
| price       | Price of the product | Numeric |
| description | Description of the product | Text |
| reviews_avg | Average rating of the product | Numeric |
| transaction_count | Number of transactions for the product | Numeric |
| search_count | Number of times product was searched | Numeric |

Table 2: User_Searches

| Column Name | Description | Feature Type |
|-------------|-------------|--------------|
| search_id   | Unique identifier for the search event | Numeric |
| user_id     | Unique identifier for the user | Numeric |
| search_query | The search string input by the user | Text |
| results_count | Number of products returned for the search | Numeric |
| clicked_product_id | Product ID clicked after the search (if any) | Numeric |

## Questions:

1. **Data Cleaning & Exploration:**

**Scenario:** You are given the `Product_Listings` table. Before delving deep into analysis, you need to check the data quality and extract preliminary insights.

**Task:** Identify products with the maximum and minimum price difference in the same category and compute the median transaction count across all and each categories.

2. **SQL Queries:**

**Scenario:**
Using the `Product_Listings` and `User_Searches` tables, your goal is to analyze user interactions with products in the Marketplace to better understand user preferences and behaviors related to product searches.

**Task:**
Write an SQL query to join the `Product_Listings` and `User_Searches` tables to find the category, price, and search_query of the 5th most searched product. This will help in understanding the kind of products users are more inclined to search for and how the search queries correlate with the actual product categories and prices.

3. **Probability and Statistical Analysis:**

**Scenario:** You are analyzing the user behavior from the `User_Searches` table to understand the user interactions with the products listed.

**Task:** Calculate the probability that a user who searched for a product also clicked on a product.

4. **Product & Business Sense:**

**Scenario:** Observing data from the `Product_Listings` table, you realize that the transaction count for certain categories has dropped by 10% in the last month.

**Task:** As a data analyst, propose a structured approach to investigate this drop. Consider aspects like the user search behavior, reviews, and pricing of the products. How might you correlate this drop to real-world events or changes in the marketplace interface? Offer potential improvements based on your insights.
