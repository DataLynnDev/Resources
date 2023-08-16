# Business Problem Statement

Amazon Fresh aims to optimize the efficiency and quality of its grocery delivery and pickup services, particularly focusing on timely delivery, reducing wastage, personalized shopping experience, and predicting demand in different localities. The goal of the data challenge is to test the candidate's ability to utilize data to provide actionable insights that could directly impact and improve these areas.

## Data Tables

#### Table 1: `orders`
| Column Name   | Description                       | Feature Type |
|---------------|-----------------------------------|--------------|
| order_id      | Unique identifier for the order   | Nominal      |
| customer_id   | Unique identifier for the customer| Nominal      |
| location      | Delivery location                 | Nominal      |
| delivery_time | Time taken for delivery           | Continuous   |
| order_date    | Date of the order                 | Date         |
| total_amount  | Total amount of the order         | Continuous   |
| status        | Status of the order (delivered, pending) | Nominal |

#### Table 2: `products`
| Column Name   | Description                  | Feature Type |
|---------------|------------------------------|--------------|
| product_id    | Unique identifier for product| Nominal      |
| category      | Category of the product      | Nominal      |
| price         | Price of the product         | Continuous   |
| stock_level   | Stock level in the warehouse | Continuous   |
| expiration_date | Expiration date of the product | Date    |

#### Table 3: `customer_preferences`
| Column Name   | Description                  | Feature Type |
|---------------|------------------------------|--------------|
| customer_id   | Unique identifier for the customer | Nominal |
| preference    | Preferred product category   | Nominal      |
| frequency     | Shopping frequency (weekly, monthly) | Nominal |

## Questions

1. **Scenario**: Amazon Fresh wants to understand the factors affecting delivery time for its orders. Using the `orders` and `customer_preferences` tables,

    **Q**: Build a regression model to predict the delivery time based on customer preferences, location, order amount, and date. How would you handle multicollinearity in this model? Please also provide an explanation of the assumptions made in your chosen regression model.


2. **Scenario**: Amazon Fresh has observed that certain products often run out of stock or are left unsold nearing their expiration date. Using the `products` table,

    **Q**: Write Python Pandas code to identify products that have stock levels below a certain threshold or are nearing expiration within a week. Then, using this output, what tree-based model would you use to predict which products will need a restock and why? Include how you would deal with imbalanced data in this model.


3. **Scenario**: Amazon Fresh is interested in predicting demand in different localities to ensure efficient delivery and inventory management. Using the `orders` and `products` tables,

    **Q**: What time series model would you use to forecast demand for specific product categories in different localities? Explain the model and how you would interpret the results. Also, write an SQL query to find the correlation between the price of the products and the total amount of orders in each locality.



