## **Business Problem Statement**
As a data scientist in our e-Commerce team, one of the significant challenges we're facing is product recommendation and customer segmentation. We need to improve our recommendation system to increase sales while also better understanding our customer behavior to tailor our services to their needs. Our current algorithms are based on transactional data, but we believe incorporating more features, including the time-series aspect of the data, could improve our results.

## **Data Tables**

1. **Table: Customer_Info**
   - CustomerID: Unique ID of the customer
   - Gender: The gender of the customer (M/F)
   - Age: The age of the customer
   - Income: Yearly income of the customer
   - Location: The customer's location

2. **Table: Transactions**
   - TransactionID: Unique ID of the transaction
   - CustomerID: Unique ID of the customer who made the transaction
   - ProductID: Unique ID of the purchased product
   - TransactionTime: Timestamp of the transaction
   - PurchaseAmount: The amount spent on the transaction

## **Questions**

1. **How can you segment the customers based on their purchasing behavior over time, considering features such as frequency, recency, and monetary value? What are some insights you can gather from this analysis?** *(Data Analysis - k-means clustering; Time Series Analysis)*

2. **Given the customer and transactions tables, write a SQL query to find the top 5 products in terms of sales for each customer segment identified in Question 1.** *(Data Manipulation - SQL JOIN and aggregation)*

3. **Build a predictive model to forecast the monthly total sales for the next six months. Justify the choice of your model and discuss how you validated its performance.** *(Time Series Analysis - ARIMA/LSTM; Machine Learning - Model selection and validation; Statistics - Cross-validation)*

4. **A/B testing is often used in e-commerce to test changes to user interfaces and products. If we were to run an A/B test on a new recommendation algorithm, how would you design this test? What metrics would you use to evaluate the results? What is your understanding of the p-value in this context?** *(Statistics - Hypothesis Testing, p-value, A/B Testing)*

