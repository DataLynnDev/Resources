# **Business Problem Statement:**
Intuit's Credit Scoring team aims to devise an advanced credit scoring model that takes advantage of both traditional credit data and alternative data sources like transaction histories or business cash flows in QuickBooks. The end goal is to accurately predict the creditworthiness of individuals or businesses, helping in better financial decision-making. To achieve this, we need a data scientist who can provide insights, strategies, and models based on the given data.

## **Data Tables**

**Credit Table:**

| Column Name | Description                          | Feature Type       |
|-------------|--------------------------------------|--------------------|
| userID      | Unique identifier for the user       | Categorical        |
| creditScore | Traditional credit score             | Numerical          |
| debtAmount  | Amount of debt                       | Numerical          |
| age         | Age of the user                      | Numerical          |

**Transactions Table:**

| Column Name | Description                          | Feature Type       |
|-------------|--------------------------------------|--------------------|
| userID      | Unique identifier for the user       | Categorical        |
| txAmount    | Amount of the transaction            | Numerical          |
| txType      | Type of transaction (debit/credit)   | Categorical        |
| date        | Date of the transaction              | Datetime           |

**QuickBooks Table:**

| Column Name | Description                          | Feature Type       |
|-------------|--------------------------------------|--------------------|
| userID      | Unique identifier for the business   | Categorical        |
| cashFlow    | Monthly business cash flow           | Numerical          |
| revenue     | Monthly business revenue             | Numerical          |

## **Questions:**

1. **(Data Manipulation & Cleaning)** From the `Credit` table, a stakeholder mentioned there were some users with NULL credit scores, which they believe is an error. Could you identify such instances and suggest a strategy to handle them while ensuring the integrity of the data?


2. **(Probability and Statistics)** Given the `Transactions` table, assume a user is deemed financially healthy if they have more credit transactions than debit over a month. If we randomly select a user, what is the probability \( p \) of them being financially healthy based on the past 3 months data? If you were to create a game where the user wins if they are financially healthy 2 out of 3 times in consecutive months, what's the probability of a user winning?

3. **(Machine Learning & Modeling)** Using the `Credit`, `Transactions`, and `QuickBooks` tables, build a model to predict the `creditScore` of a user. Make sure to detail any features you engineer and your reasoning behind choosing them. Specify any strategies you employ to avoid model overfitting.

    *Target Variable: `creditScore` (Numerical)*

4. **(Product Design & Analytics)** Based on the data in the `Transactions` and `QuickBooks` tables, design a ranking system to rank users by their financial health. Provide a rationale for your system, and detail how you would use it to provide insights to stakeholders.