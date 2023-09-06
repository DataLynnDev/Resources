# **Business Problem Statement:**
At Intuit's Tax Prediction team, our goal is to simplify the complex tax world for our users. With the evolving financial landscape and the plethora of financial activities that each user engages in, we believe that by analyzing these activities, we can preemptively provide accurate predictions on potential deductions, tax liabilities, or refund amounts. This approach will not only help our users in seamless tax filings but will also ensure they reap the maximum benefits.

## **Data Table: TaxUserData**

| Column Name | Description                            | Feature Type     |
|-------------|----------------------------------------|------------------|
| user_id     | Unique identifier for a user           | Categorical      |
| income      | Annual income of the user              | Continuous       |
| expenses    | Annual deductible expenses             | Continuous       |
| investments | Value of investments made during the year | Continuous     |
| deductions  | Value of deductions claimed in previous years | Continuous |
| prev_refund | Refund amount received in the previous year | Continuous  |
| marital_status | Marital status of the user (Single, Married, etc.) | Categorical |
| employment_status | Type of employment (Full-time, Part-time, etc.) | Categorical |
| liabilities     | Pending liabilities or loans           | Continuous      |
| tax_paid_prev_year | Amount of tax paid in the previous year | Continuous |

## **Questions:**

1. **SQL & Data Cleaning**: Given the `TaxUserData` table, a colleague suggests that the `user_id` can be null in some entries and claims it won't affect analyses.
    - **a.** Write a SQL query to identify and count such rows.
    - **b.** Describe any potential challenges these null values might present in further analysis.
   
2. **Probability and Statistics**: Intuit is considering offering a new tax-saving scheme, where if a user has `liabilities` between a certain range, they can avail certain deductions. For a subset of data:
    - **a.** What is the probability distribution of `liabilities`?
    - **b.** If the user decides to go with this scheme, what's the probability they would have at least $5000 in deductions? Use the Binomial theorem with previous `deductions` data as a basis.
  

3. **Machine Learning & Modeling**: Based on user financial activities, we want to predict the possible `deductions` a user might have for the coming year.
    - **a.** Describe how you would preprocess this data and select features for a predictive model.
    - **b.** Using the above data, choose between a decision tree and logistic regression for this prediction task. Justify your choice.
    
    **Target Variable**: `deductions` (Continuous)
  

4. **Product Design & Analytics**: Intuit wants to create a feature ranking system for its dashboard, to show users which factors most impact their potential deductions.
    - **a.** Using the `TaxUserData` table, design a system that ranks features based on their impact on potential deductions.
    - **b.** Based on the designed system, which features should be highlighted to the user as top contributors?