# **Business Problem Statement:**

With Amazon's vast range of products and millions of global consumers, there is a constant need to ensure the platform remains efficient, user-friendly, and sales-optimized. One critical aspect of this is understanding customer behavior in real-time and making data-driven recommendations to enhance the overall shopping experience and drive sales. The challenge lies in analyzing customer behavior data, product reviews, sales patterns, and integrating these insights into the platform for real-time optimizations.

## **Data Tables:**

**Table 1: CustomerBehavior**

| Column Name | Description                      | Feature Type  |
|-------------|----------------------------------|---------------|
| customer_id | Unique ID for each customer      | Nominal       |
| visit_date  | The date of the website visit    | Date          |
| product_id  | ID of the product viewed/bought  | Nominal       |
| time_spent  | Time spent viewing the product  | Continuous    |
| action      | Buy/View/Cart/Review             | Categorical   |

**Table 2: ProductReviews**

| Column Name | Description                   | Feature Type  |
|-------------|-------------------------------|---------------|
| review_id   | Unique ID for each review     | Nominal       |
| product_id  | ID of the product reviewed    | Nominal       |
| customer_id | ID of the customer reviewing  | Nominal       |
| rating      | Rating out of 5               | Ordinal       |
| review_text | Text of the review            | Text          |

## **Questions**

**Question 1: Data Cleaning & Exploration**

*Scenario:* You're handed the `CustomerBehavior` table. Before any analysis can be done, the data quality needs to be ensured. You suspect there might be some data issues.

1. Identify and address any missing values in the `CustomerBehavior` table.
2. Check for any outliers, especially in the `time_spent` column and devise a method to address them.
3. Ensure the `visit_date` is in a uniform date format.


**Question 2: SQL Queries**

*Scenario:* With both `CustomerBehavior` and `ProductReviews` tables at your disposal, the marketing team wants insights into customers' engagement and their feedback.

1. Using a JOIN operation, retrieve a list of `customer_id`s who have both bought a product and written a review for it.
2. Using UNION, combine all unique `product_id`s from both tables.
3. Write a CTE to fetch the top 10 products with the highest average rating.

**Question 3: Probability and Statistical Analysis**

*Scenario:* Different categories of products may receive different average ratings. You want to determine if there's a statistically significant difference between them.

1. Based on the ANOVA assumptions, describe what you would check in the `ProductReviews` table before conducting the test.
2. If three product categories are "Electronics", "Books", and "Clothing", derive the mathematical equation to perform ANOVA.
3. Implement the above calculation using Python to get the result.

**Question 4: Product & Business Sense**

*Scenario:* The end of the quarter is approaching and the sales team needs an estimate of potential sales for top products based on customer behavior trends.

1. Describe how you would use the `CustomerBehavior` table to forecast potential sales for the next quarter.
2. Once you have these insights, list down potential stakeholders within Amazon who might benefit from this data.