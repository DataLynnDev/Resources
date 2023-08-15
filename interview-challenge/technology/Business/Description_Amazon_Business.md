# **Business Problem Statement:**

Amazon Business aims to optimize procurement and supply chain efficiencies for businesses of all sizes. The current challenge is to identify areas in the supply chain that can be improved to reduce costs and delivery time, as well as to enhance bulk pricing strategies and detect potential fraud or anomalies. An experienced data scientist will need to dive into the data to uncover insights, create predictive models, and provide actionable recommendations.

---

## **Data Tables:**

*Table 1: Orders*

| Column Name | Description                                       | Feature Type   |
|-------------|---------------------------------------------------|----------------|
| order_id    | Unique identifier for an order                    | Categorical    |
| product_id  | Identifier for the product purchased              | Categorical    |
| quantity    | Number of units purchased                         | Numerical      |
| price       | Price per unit                                    | Numerical      |
| vendor_id   | Identifier for the vendor supplying the product   | Categorical    |
| timestamp   | Timestamp of the order                            | Datetime       |

*Table 2: Products*

| Column Name   | Description                              | Feature Type   |
|---------------|------------------------------------------|----------------|
| product_id    | Unique identifier for a product          | Categorical    |
| category      | Category of the product                  | Categorical    |
| bulk_discount | Discount applicable on bulk purchase     | Numerical      |

*Table 3: Vendors*

| Column Name | Description                 | Feature Type   |
|-------------|-----------------------------|----------------|
| vendor_id   | Unique identifier for vendor| Categorical    |
| region      | Region of the vendor        | Categorical    |

---

## **Questions:**

1. **Scenario:** The management wants to analyze the relationship between bulk discounts, categories, and vendors to identify potential pricing strategies. Using the data tables provided:

    a) Merge Tables 1 and 2 on `product_id`, and Table 3 on `vendor_id`. Describe different JOIN operations you utilized.

    b) Identify the categories that significantly benefit from bulk discounts. How would you handle categorical variables such as `category` and `region` in this analysis?

    c) What statistical methods would you apply to determine if bulk discount significantly impacts sales?


2. **Scenario:** Amazon Business is planning to forecast the sales for different product categories.

    a) Use Tables 1 and 2, and perform time series analysis on the monthly sales data for different product categories. Explain different time series models you can use other than Arima.

    b) If you find a sudden spike in sales for a specific category, how would you use hypothesis testing to validate whether the spike is statistically significant?
    
    c) Based on the results from the time series analysis, explain how you would modify bulk discount strategies for specific product categories.

