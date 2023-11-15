# **Business Problem Statement**
**Problem:** The Amazon Marketplace platform has noticed an uptick in potential fraudulent seller activities. Some of these sellers list high-demand products but don't deliver on time or sometimes even at all, impacting customer trust and experience.

**Description:** The fraudulent activity mainly manifests in sudden spikes in sales for new sellers, high return rates, and low customer ratings. Detecting such sellers early on would help Amazon take preventive measures and maintain the platform's credibility.

## **Data Tables**

Table Name: **Sellers**

| Column Name | Description | Feature Type |
| --- | --- | --- |
| seller_id | Unique ID for each seller | Numeric |
| join_date | Date the seller joined | Date |
| total_sales_last_month | Total sales of the last month | Numeric |
| return_rate | Percentage of products returned | Numeric |
| avg_customer_rating | Average rating given by customers | Numeric |

Table Name: **Sales**

| Column Name | Description | Feature Type |
| --- | --- | --- |
| transaction_id | Unique ID for each sale | Numeric |
| seller_id | ID of the seller | Numeric |
| product_id | ID of the product sold | Numeric |
| sale_date | Date of the sale | Date |
| sale_amount | Amount for the sale | Numeric |
| is_returned | Whether the product was returned | Boolean |

## Questions

### 1. **Data Cleaning & Exploration Questions**

**Scenario:** You're presented with the sales data for the last year. There have been multiple complaints from customers regarding certain sellers. To understand this better, you decide to begin by cleaning and exploring the data.

**Task:** Identify and handle any missing values and outliers in the `Sales` table, especially focusing on `sale_amount`. Use visual tools to help you explore patterns. What insights can you derive regarding the sale amounts and return rates?

### 2. **SQL Queries Questions**

**Scenario:** You've been informed that some sellers might be listing their products under multiple IDs to manipulate sales numbers. You decide to explore this by diving into the sales data.

**Task:**
Using the `Sales` and `Sellers` tables, identify sellers who have more than one product ID associated with a high return rate. Combine the information of these sellers and products, ensuring there are no duplicates. Finally, join the tables in a way to highlight these sellers and their associated product IDs, focusing on those who joined in the last year.

### 3. **Probability and Statistical Analysis Questions**

**Scenario:** To better understand the behavior of new sellers, you hypothesize that sellers who join the platform and immediately have high sales are more likely to be involved in fraudulent activities.

**Task:**
Calculate the probability that a new seller (joined in the last month, now is 09/2023) will have sales in the top 10% of all sellers in their first month. Validate your hypothesis using the appropriate statistical tests on the `Sellers` table, making sure to consider potential over-fitting. Code the calculation to obtain the result.


### 4. **Product & Business Sense Questions**

**Scenario:** Recently, the platform predicted that the revenue from the marketplace will increase by 15%, but the actual revenue increased by only 5%.

**Task:**
Using the `Sales` and `Sellers` tables, analyze the data to pinpoint potential reasons for this discrepancy. Identify key metrics (like return rate, average customer rating, etc.) that might have influenced this difference. Based on your analysis, what recommendations can you provide to bridge the gap between the predicted and actual revenue in the future?
