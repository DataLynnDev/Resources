# **Business Problem Statement:**

QuickBooks, as Intuit's flagship accounting software, constantly seeks to provide more efficient and intelligent services to its vast clientele of small to medium-sized businesses. Recently, the platform noticed an increased churn rate amongst its users. To tackle this, the team wants to understand the behavior of its users, identify potential issues, and predict users who are likely to churn so that targeted interventions can be made. The analysis would also assist in feature enhancements and overall product improvement.

## **Data Tables:**

| Table Name   | Column Name     | Description                                               | Feature Type   |
|--------------|-----------------|-----------------------------------------------------------|----------------|
| users        | user_id         | Unique identifier for each user                           | Categorical    |
|              | signup_date     | Date when the user signed up                              | Date           |
|              | last_login      | Last date the user logged in                              | Date           |
|              | subscription    | Type of subscription (Basic, Premium, etc.)               | Categorical    |
| activity     | user_id         | Unique identifier for each user                           | Categorical    |
|              | feature_used    | The specific feature of QuickBooks used by the user       | Categorical    |
|              | usage_time      | Total time spent on that feature                          | Numeric (mins) |
| transactions | user_id         | Unique identifier for each user                           | Categorical    |
|              | transaction_amt | Amount of the transaction                                 | Numeric ($)    |
|              | transaction_date| Date of the transaction                                   | Date           |

### **Questions:**

1.  Given the user engagement trends on QuickBooks, we've realized that feature interaction might be a predictor of long-term user retention. Using the `activity` table:

 - Identify the top 3 most used features by the users.
 - For each of these features, determine the median time spent by users in the last month.
 - Analyze if there's a correlation between the frequency of a feature's use and the time spent on it. Does a frequently used feature necessarily mean more time is spent on it?
 - Propose a possible segmentation of users based on both feature frequency and time spent. How might these segments help in understanding user behavior and predicting churn?

2.  Our product team is keen on understanding which subscription type brings in the highest transaction amounts, and how they've evolved over time. Using the `users` and `transactions` tables, design a SQL query to retrieve the average transaction amount for each subscription type on a monthly basis.

3. To predict user churn, we're considering using machine learning models. Given the features in the provided tables, which additional features would you derive or suggest to make this prediction more accurate? Further, considering the constraints, which model would you choose, and why?

4. (Optional) As part of our customer retention strategy, we're introducing a rewards system. If a user engages with a feature once, they get a certain number of points. But if they engage with three different features and spend a significant time on at least two of them, they get bonus points. Based on user behavior, estimate the probability of users achieving these bonus points in the next month.

Remember, the goal here is to understand user behavior, enhance feature offerings, and reduce churn. Ensure that your techniques align with these objectives.