# **Business Problem Statement:**
At Salesforce, customer retention is of paramount importance. Understanding and predicting customer churn is crucial for long-term business sustainability. The objective of this challenge is to predict customer churn based on the historical data provided and draw actionable insights to mitigate the churn risk.

## **Data Tables**

**Table 1: CustomerData**

| Column Name      | Description                                         | Feature Type   |
|------------------|-----------------------------------------------------|----------------|
| `CustomerID`       | Unique Identifier for a customer                    | Categorical    |
| `LastActivityDate` | Date of the most recent activity by the customer    | Date           |
| `SignupDate`       | Date when the customer signed up                    | Date           |
| `ProductUsage`     | Score (0-100) representing product usage intensity  | Numerical      |
| `FeedbackScore`    | Score (1-5) indicating customer's feedback          | Ordinal        |
| `SupportTickets`   | Number of support tickets raised by the customer    | Numerical      |
| `PlanType`         | Type of subscription plan                           | Categorical    |
| `ChurnStatus`      | 0 for Active, 1 for Churned                         | Categorical    |


**Table 2: ProductLogs**

| Column Name      | Description                                         | Feature Type   |
|------------------|-----------------------------------------------------|----------------|
| `CustomerID`       | Unique Identifier for a customer                    | Categorical    |
| `ProductID`        | ID of the Salesforce product being used             | Categorical    |
| `UsageDuration`    | Total duration (in hours) product was used          | Numerical      |
| `ErrorCount`       | Count of errors experienced while using the product | Numerical      |


## **Questions:**

1. **Scenario:** Over the years, Salesforce has made changes to its subscription plans. This has resulted in some missing values in the `PlanType` column of the `CustomerData` table.  
  - **Question:** Using the available data, devise a method to impute the missing values in the `PlanType` column, and justify your approach.

2. **Scenario:** The executive team believes that customers who experience a high number of errors in product usage are more likely to churn.  
  - **Question:** Using SQL, determine the top 10% of customers in terms of error counts from the `ProductLogs` table. Compare these customers' churn rates with the average churn rate of all customers in the `CustomerData` table.

3. **Scenario:** There's an organizational push to proactively address potential churn.  
  - **Question:** Build a predictive model to determine the likelihood of a customer churning. Clearly mark `ChurnStatus` as the target variable. Which features contribute most to the prediction? How would you validate the performance of this model?

4. **Scenario:** The product team is interested in understanding product engagement patterns. They believe that higher engagement reduces churn.  
  - **Question:** Using the `ProductLogs` and `CustomerData` tables, analyze the product usage patterns of customers who churned in the last quarter. How do their usage patterns differ from customers who remained active? What actionable insights can you derive for the product team to enhance user engagement and potentially reduce churn?