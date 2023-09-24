# **Business Problem Statement**:
There has been a significant increase in fraudulent activities on Facebook, causing financial losses and undermining user trust. The primary goal is to identify potential fraudulent activities by analyzing patterns and detecting any anomalies, ensuring the maintenance of platform integrity.

## **Data Tables**:

**Table Name**: Transactions

| **Column Name**   | **Description**                                      | **Feature Type**|
|-------------------|-----------------------------------------------------|-----------------|
| user_id           | Unique identifier for the user                      | Numerical       |
| transaction_id    | Unique identifier for each transaction              | Numerical       |
| amount            | Amount involved in the transaction                  | Numerical       |
| date_time         | Timestamp of the transaction                         | DateTime        |
| transaction_type  | Type of transaction (e.g. Payment, Refund)          | Categorical     |
| is_flagged        | Flag indicating suspicious activity (0 or 1)        | Categorical     |

**Table Name**: UserProfile

| **Column Name**   | **Description**              | **Feature Type**|
|-------------------|-----------------------------|-----------------|
| user_id           | Unique identifier for the user| Numerical       |
| account_created   | Account creation date        | DateTime        |
| last_login        | Last login timestamp         | DateTime        |
| user_location     | User's current location      | Categorical     |

## Questions

1. **Question 1: Data Cleaning & Exploration**

**Scenario**:
You have been given a dataset of transactions, and there's a need to prepare it for exploratory analysis and fraud detection models.

**Task**:
Identify and handle any missing values in the 'amount' column and unify the 'date_time' column format to "YYYY-MM-DD HH:MM:SS".

2. **Question 2: SQL Queries**



**Scenario**:
In order to get a comprehensive view of the user's activities, the transactions need to be combined with the user profile information.

**Task**:
Write an SQL query to join the 'Transactions' table with the 'UserProfile' table on 'user_id'. Further, group the results by 'user_location' and filter out locations having a total transaction amount greater than 100,000.

3. **Question 3: Probability and Statistical Analysis**

**Scenario**:
The fraud detection team is trying to estimate the probability of a transaction being flagged as suspicious, given that the amount is above a certain threshold.

**Task**:
Firstly, derive an equation to calculate the probability of a transaction being flagged as suspicious (from the 'is_flagged' column) given that the transaction amount is above 1,000. After deriving the equation, implement the calculation using any programming language to obtain the result.

4. **Question 4: Product & Business Sense**

**Scenario**:
Facebook recently introduced a new security feature, and there's an interest in understanding its impact on user trust and reducing fraudulent activities.

**Task**:
How would you measure the success of this new security feature in terms of reducing fraudulent activities? Also, propose a plan on how you can migrate users who have been affected by fraud in the past to utilize this new feature.