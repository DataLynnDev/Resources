# **Business Problem Statement:**
To enable PayPal to continue its leadership in the fintech landscape, there's an increasing demand to forecast transaction volumes, revenue streams, and market trends. Leveraging time-series analysis, deep learning, and trend prediction, we aim to generate insights and predictive models for strategic growth and planning.

## **Data Table:**
**Data_Info**

| Column Name | Description                                         | Feature Type |
|-------------|-----------------------------------------------------|--------------|
| date        | Transaction date                                    | Date         |
| trans_id    | Unique identifier for each transaction              | Categorical  |
| user_id     | Unique identifier for the user                      | Categorical  |
| amount      | Amount of the transaction                           | Numerical    |
| currency    | Type of currency used for the transaction            | Categorical  |
| country     | Country where the transaction was originated        | Categorical  |
| category    | Transaction category (e.g., shopping, bills, etc.)  | Categorical  |
| status      | Status of transaction (e.g., success, failed)       | Categorical  |
| channel     | Mode of transaction (e.g., mobile, web)              | Categorical  |
| revenue     | PayPal's revenue from the transaction                | Numerical    |

## **Questions:**

1. **Data Exploration & Cleaning:**
   Given a random sample of transactions, identify any missing values or outliers within the 'amount' feature. What possible impact could these outliers have on overall revenue trend predictions?

2. **Probability and Statistics:**
   Given historical transaction data over the past year, calculate the probability that a user from a specific country will make a transaction exceeding $500 in the next month. Furthermore, conduct a Z-test to determine if the mean transaction amount in this country is significantly different from the global average. What conclusions can you draw from the P-value?

3. **Machine Learning & Modeling:**
   Develop a predictive model to forecast PayPal's revenue for the upcoming quarter based on historical transaction data. Specify which features you consider as predictors and clearly mark 'revenue' as the target variable. Upon finalizing your model, how would you validate its performance considering the possibilities of overfitting?

4. **Product Design & Analytics:**
   Imagine a new feature in PayPal's application where users can tag their transactions for personal bookkeeping (e.g., 'holiday shopping', 'business expense'). Analyze transaction data to identify potential categories that are popular but not yet recognized in PayPal's current 'category' feature. How might this inform product design decisions and user experience?
