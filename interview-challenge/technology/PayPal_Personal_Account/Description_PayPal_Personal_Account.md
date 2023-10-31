# Business Problem Statement:
Identify and analyze transaction patterns of PayPal Personal Account users to enhance user experience, detect potential fraudulent activities, and suggest new features based on spending behaviors.

## Data Tables:

**Table: Transactions**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| transaction_id | Unique identifier for each transaction | int | Primary Key |
| user_id | Identifier for the user | int | Foreign Key |
| transaction_date | Date of the transaction | date | |
| transaction_amount | Amount involved in the transaction | float | |
| transaction_type | Type of transaction (e.g., online purchase, money sent, money received) | varchar | enum: ['Online Purchase', 'Money Sent', 'Money Received'] |
| payment_method | Method used for the transaction (e.g., bank account, credit card, debit card) | varchar | enum: ['Bank Account', 'Credit Card', 'Debit Card'] |

**Table: Users**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| user_id | Unique identifier for each user | int | Primary Key |
| user_name | Name of the user | varchar | |
| account_creation_date | Date when the user created their PayPal account | date | |
| country | Country of the user | varchar | |

## Questions

### SQL Question 1:
**Topics and Operations:** Percentage Calculation

**Scenario:**
PayPal wants to understand the proportion of transactions where users are making online purchases compared to other transaction types to gauge the popularity of online shopping.

**Task:**
Calculate the percentage of transactions that are of type 'Online Purchase', rounded to 2 decimal places.

### SQL Question 2:
**Topics and Operations:** Aggregation and Ordering

**Scenario:**
To understand user engagement and potential areas of improvement, PayPal wants to identify users who are most active in terms of transaction frequency.

**Task:**
Find the name of the user who has made the greatest number of transactions. In case of a tie, return the lexicographically smaller user name.

### SQL Question 3:

**Topics and Operations:** Joining Tables, Filtering, and Aggregation

**Scenario:**
PayPal is interested in identifying users who consistently have transactions within a certain range (neither too high nor too low) to target them for specific promotions or features.

**Task:**
Report the users (user_id, user_name) who have never made a transaction below $10 and never above $1000. Return the result table ordered by user_id.
