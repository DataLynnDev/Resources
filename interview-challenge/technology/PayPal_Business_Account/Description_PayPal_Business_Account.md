# **Business Problem Statement**:
PayPal's Business Account Team has observed a fluctuation in the number of transactions and feedback from businesses over the past few months. The team is keen on understanding the patterns of transactions, identifying the most active merchants, and analyzing feedback to enhance the user experience. The primary goal is to ensure that the business account features are being utilized to their maximum potential and to identify areas of improvement.

## **Data Tables**:

**Table: Transactions**

| Feature Name | Description                                  | Data Type | Comments |
|--------------|----------------------------------------------|-----------|----------|
| trans_id     | Unique identifier for each transaction      | int       | Primary Key |
| merchant_id  | Identifier for the merchant                  | int       | Foreign Key |
| trans_date   | Date of the transaction                      | date      | |
| amount       | Amount of the transaction                    | float     | |
| status       | Status of the transaction (Success, Failed)  | enum      | Options: Success, Failed |

**Table: MerchantFeedback**

| Feature Name | Description                                  | Data Type | Comments |
|--------------|----------------------------------------------|-----------|----------|
| feedback_id  | Unique identifier for each feedback          | int       | Primary Key |
| merchant_id  | Identifier for the merchant                  | int       | Foreign Key |
| feedback_date| Date when the feedback was given             | date      | |
| feedback     | Detailed feedback from the merchant          | varchar   | |
| rating       | Rating given by the merchant (1 to 5)        | int       | Range: 1-5 |

## Questions

**Question 1**:

- *Topics and Operations*: Difference in values
- *Scenario*: The team wants to understand the difference in transaction amounts between successful and failed transactions to gauge if higher transaction amounts have a higher failure rate.
- *Task*: Write a SQL solution to calculate the difference between the average transaction amounts of successful and failed transactions. Output the absolute difference in transaction amounts.

**Question 2**:
- *Topics and Operations*: Count and Join
- *Scenario*: To enhance the user experience, the team wants to identify merchants who have provided feedback multiple times, indicating they are active and engaged users.
- *Task*: Write a SQL solution to report the merchants who have given feedback more than once. Return the merchant_id and the number of times they have provided feedback, ordered by merchant_id in ascending order.

**Question 3**:
- *Topics and Operations*: Cumulative Sum

- *Scenario*: The team is interested in understanding the cumulative transaction amounts for each merchant over the past three months to identify the most active merchants.

- *Task*: Write a SQL solution to calculate the cumulative transaction amount for every merchant for the second quarter of 2023. For each month, sum up the transaction amounts in that month and the previous two months. Return the result table ordered by merchant_id in ascending order. In case of a tie, order it by trans_date in descending order. Do not include the 3-month sum for the most recent month.
