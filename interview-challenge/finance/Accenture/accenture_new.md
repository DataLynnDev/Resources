# **Business Problem Statement**

Accenture is working with a client in the banking industry who is looking to improve their customer retention rate. They believe that by leveraging data science and machine learning techniques, they can better understand customer behavior and predict which customers are most likely to churn. The client has provided two datasets: one containing customer demographic and account information (`CustomerInfo`) and another containing transaction history (`TransactionHistory`).

## **Data Tables**

1. **Table: CustomerInfo**

| Column Name | Description |
|-------------|-------------|
| CustomerID  | Unique identifier for each customer |
| Age         | Age of the customer |
| Gender      | Gender of the customer |
| AccountType | Type of account the customer holds |
| Tenure      | How long the customer has been with the bank |
| Balance     | Current account balance |
| NumProducts | Number of products the customer has with the bank |
| IsActiveMember | Whether the customer is an active member |
| EstimatedSalary | Estimated salary of the customer |
| Exited      | Whether the customer has churned |

2. **Table: TransactionHistory**

| Column Name | Description |
|-------------|-------------|
| TransactionID | Unique identifier for each transaction |
| CustomerID  | Unique identifier for each customer |
| TransactionDate | Date of the transaction |
| TransactionAmount | Amount of the transaction |
| TransactionType | Type of transaction (Deposit, Withdrawal, etc.) |

## Questions:

1. Using the `CustomerInfo` table, perform an exploratory data analysis to understand the characteristics of customers who have churned (`Exited` = 1) versus those who have not. What insights can you draw from this analysis?

2. Based on your exploratory data analysis, build a logistic regression model to predict customer churn. What are the key features influencing customer churn according to your model? How would you validate the performance of this model?

3. Using the `TransactionHistory` table, create a new feature in the `CustomerInfo` table that represents the average transaction amount for each customer over the past 6 months. How does this new feature influence your logistic regression model?

4. Suppose your logistic regression model suggests that customers with a higher number of products are more likely to churn, but the bank's business team believes that selling more products to customers should increase customer loyalty. How would you resolve this conflict? Can you think of a new data science project that could help clarify this issue?

