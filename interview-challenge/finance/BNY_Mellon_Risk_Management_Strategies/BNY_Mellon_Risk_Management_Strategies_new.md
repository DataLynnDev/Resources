# Business Problem Statement

As BNY Mellon, we continuously strive to optimize our portfolio risk management strategies. A critical part of this process is to predict potential credit default risks for our customers. To improve our predictive capabilities, we need to leverage our extensive customer and transaction data to build a machine learning model that accurately forecasts the probability of default for each customer.

Your task is to develop a model using the provided datasets, taking into account static customer attributes and dynamic transaction data.

## Data Challenge Table

**Table 1: Customers**

|Column Header|	Description |
|---------------|---------------------------------------------------|
| customer_id |	Unique identifier for each customer|
| age |	Age of the customer|
| job |	Type of job of the customer|
|marital_status|	Marital status of the customer|
|education_level|	Highest level of education attained by the customer|
|default_history|	Whether the customer has a history of credit default (Yes, No)|
|housing_loan_status|	Whether the customer has a housing loan (Yes, No)|
|personal_loan_status	| Whether the customer has a personal loan (Yes, No)|
|credit_score |	Credit score of the customer, range from 300-850|

**Table 2: Transactions**

|Column Header|	Description |
|---------------|---------------------------------------------------|
|transaction_id |	Unique identifier for each transaction|
|customer_id |	Unique identifier for each customer|
|date |	Date of the transaction|
|transaction_amount |	The amount of the transaction|
|transaction_type	| The type of the transaction (Deposit, Withdrawal)|
|balance_after_transaction|	The balance of the customer's account after the transaction|

## Questions

**1. Data Manipulation**

Suppose you find that some customers have transactions recorded before their account creation date. How would you address this discrepancy?

**2. Metric Selection**

 Imagine you are presenting your model to stakeholders who are not data scientists. They are interested in the model's performance but find traditional classification metrics hard to interpret. How would you quantify the model's performance in a more intuitive way?

**3. Feature Engineering**

- Our stakeholders believe that customers' banking behavior may exhibit certain patterns during different times of the year. How would you engineer the 'date' feature to capture this?

- Given the transaction data, propose three creative features that might predict a customer's default risk. Explain why you expect them to be useful.

**4: Model Selection**

Predict potential credit default risks for our customers considering dynamic transaction data?

**5: Model Optimization**

Let's say your model's performance has room for improvement. Can you think of a non-traditional approach you could take to enhance your model, leveraging the specific context of our data or problem?

