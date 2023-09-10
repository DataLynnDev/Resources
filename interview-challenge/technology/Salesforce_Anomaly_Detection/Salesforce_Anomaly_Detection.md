# **Business Problem Statement:**  
Given the vast sea of data that Salesforce processes daily, anomalies can potentially signify system failures or security breaches that might compromise the integrity of the data. Alternatively, they might signify unique business opportunities that were hitherto unexplored. Your task is to delve deep into this data, find these anomalies, and figure out their potential impact on the business.

## **Data Table:**
**Transactions**  

| Column Name      | Description                                       | Feature Type     |
|------------------|---------------------------------------------------|------------------|
| `transaction_id`   | Unique ID for each transaction                    | Categorical      |
| `customer_id`      | ID for each customer                              | Categorical      |
| `transaction_date` | Date of the transaction                           | Date             |
| `transaction_amt`  | Amount in $ of the transaction                    | Numerical        |
| `product_id`       | ID for each product bought                        | Categorical      |
| `region`           | Region where transaction occurred                 | Categorical      |
| `payment_mode`     | Mode of payment used (Credit, Debit, Cash)        | Categorical      |
| `system_response`  | System response time in seconds                   | Numerical        |
| `transaction_type` | Type of transaction (Purchase, Refund, Inquiry)   | Categorical      |
| `feedback`         | Feedback given by customer (Scale 1-5)            | Ordinal          |

## **Questions:**  

1. **SQL/ Data Manipulation:**  
   - **Scenario:** Recently, there have been reports of unusually high-value transactions coming from specific regions. We suspect these could be outliers or anomalies.  
   - **Question:** Using SQL, identify the regions with transaction amounts that are two standard deviations above the mean transaction amount in the last six months. Additionally, provide a count of how many such transactions have occurred in each region.

2. **Probability and Statistics:**  
   - **Scenario:** We have noticed that certain regions consistently have high feedback scores associated with the transactions.  
   - **Question:** Determine if there's a statistically significant difference in feedback scores between two regions of your choice. Use the appropriate statistical test to justify your answer.

3. **Machine Learning & Modeling:**  
   - **Scenario:** We are concerned that the prolonged system response times could lead to transaction failures or customer dissatisfaction.  
   - **Question:** Construct a model to predict `system_response` based on other features in the `Transactions` table. Clearly identify your target variable, and provide metrics to validate your model's performance.

4. **Product Design & Analytics:**  
   - **Scenario:** There have been an increased number of inquiries (transaction type: Inquiry) from a specific region which might signal a potential new market or some system issues that customers are not clear about.  
   - **Question:** Analyze the transactions of type 'Inquiry' from this region over the last three months. Based on the data, provide a business recommendation: Is this signaling a potential market opportunity or do we need to investigate a potential system issue?