# **Business Problem Statement:**
PayPal's Risk Management team is focused on building a robust system that accurately gauges the risk levels of users and merchants. By analyzing transaction histories, credit scores, user feedback, and other critical data, we aim to minimize potential losses while ensuring smooth transaction experiences for our clients. The data scientist's role is to delve into this data, uncover insights, and develop models to predict and manage these risks.


## **Data Table**:

**UserRiskProfile**

Column Name|	Description|	Feature Type
---------------|--------|----------
`UserID`|	Unique identifier for the user	|Categorical
`CreditScore`|	User's credit score	|Continuous
`TransactionHist`	|Past transaction amounts (in USD)	|Time series
`LoanOffered`|	Amount of loan offered to the user (in USD)	|Continuous
`FeedbackScore`	|User feedback score (1-5)	|Ordinal
`ChargebackHist`|	Number of past chargebacks by the user	|Continuous
`MerchantRating`|	Rating of merchant by other users (1-5)	|Ordinal
`ThirdPartyData`|	External data score (e.g., from credit bureaus)	|Continuous
`LoanDefaulted`|	Whether a user defaulted on a loan (0/1)|	Binary
`TransactionDate`|	Date of the transaction|	Date



## **Questions:**

1. **Historical Data Analysis:** Given the UserRiskProfile table, can you identify patterns or anomalies in the TransactionHist over the last six months that might correlate with users who have a history of chargebacks (ChargebackHist)?

2. **Loan Default Prediction:** Based on the data provided in UserRiskProfile, build a model to predict the LoanDefaulted target variable.

  *Which features were the most influential in your model's prediction? How would you handle TransactionHist as it's a time series feature in this context?*

3. **Product Recommendation:**
Considering that PayPal might want to introduce new financial products or adjustments to existing offerings, use the UserRiskProfile data to segment users. Can you suggest targeted product offerings or policies for each segment based on their risk profile? For instance, users with a certain CreditScore range might benefit from a different loan offering.

4. **Risk Evaluation through External Data:**
Often, ThirdPartyData might have a different scale or might be evaluated differently than CreditScore. Design a strategy to normalize these features and determine how much weightage should be given to internal (CreditScore) vs external (ThirdPartyData) scores when evaluating user risk. Implement this and identify users that might have been perceived as high-risk by PayPal's internal data but are considered low-risk by external data and vice versa.