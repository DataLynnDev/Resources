# **Business Problem Statement:**

The Booking platform has seen a rise in fraudulent activity, which is harming the trust of its users and partners, leading to potential revenue loss. The goal is to build an anomaly detection system that monitors user activities and transactions to identify potential fraudsters, thereby safeguarding the platform's reputation and finances.

## **Data Tables**:

1. **UserActivityTable**

| Column Name | Description                                               | Feature Type      |
|-------------|-----------------------------------------------------------|-------------------|
| UserID      | Unique identifier for the user                            | Categorical       |
| SessionID   | Identifier for the user's session                         | Categorical       |
| DateTime    | Timestamp of the activity                                 | Datetime          |
| ActivityType| Type of activity e.g. 'ViewHotel', 'BookHotel' etc.       | Categorical       |
| DeviceType  | Device used e.g. 'Mobile', 'Desktop'                      | Categorical       |

2. **TransactionsTable**

| Column Name | Description                                               | Feature Type      |
|-------------|-----------------------------------------------------------|-------------------|
| TransactionID| Unique identifier for the transaction                     | Categorical       |
| UserID      | Unique identifier for the user                            | Categorical       |
| DateTime    | Timestamp of the transaction                              | Datetime          |
| Amount      | Amount of the transaction                                 | Numeric (float)   |
| PaymentMethod| e.g. 'CreditCard', 'PayPal' etc.                         | Categorical       |


## **Questions**:

1. **Fraudulent Activity Patterns:**
   Using the `UserActivityTable`, identify patterns of user activities that could indicate potential fraudulent behavior. For instance, a rapid sequence of high-value bookings in a short period of time from different devices.
   
2. **Predictive Model for Fraud Detection:**
   Describe a predictive model using the `TransactionsTable` where the target variable is a binary label indicating if the transaction is fraudulent or not (you are given this label for historical data). Describe which features you would engineer from the available data, and why you would choose them. Also, explain the potential pitfalls of the model and how you would evaluate its performance.
   
   *Target Variable*: Fraudulent (binary: 0 for genuine transaction, 1 for fraudulent transaction)
   

3. **A/B Testing for New Anomaly Detection System:**
   Suppose the new anomaly detection system you proposed in the previous question has been implemented. Design an A/B test to measure the impact of the new system on reducing the number of fraudulent transactions, ensuring that you don't disrupt the genuine user experience. Mention the groups, metrics, and potential challenges in the test.


4. **Tagging Suspicious Accounts:**
   Using the combined information from `UserActivityTable` and `TransactionsTable`, propose a method to flag users with suspicious activities. What threshold or criteria would you use, and how would you validate your findings to avoid false positives?

