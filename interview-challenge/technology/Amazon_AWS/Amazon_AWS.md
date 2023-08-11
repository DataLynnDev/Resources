## **Business Problem Statement**
Our company, Amazon Web Services (AWS), is exploring the feasibility of a new service called "AWS Data Insights". This service aims to provide real-time data insights for online businesses, enabling them to optimize their operations based on consumer behavior patterns. We have been collecting data from a sample of online businesses including information about transactions, customers' interactions with their platforms, and customers' demographic details. The data science team is tasked with developing predictive models to uncover insights and provide recommendations to these businesses.

## **Data Tables**

1. **Table: Transactions**
   - `transaction_id`: Unique identifier for the transaction
   - `customer_id`: Unique identifier for the customer
   - `purchase_date`: Date of the purchase
   - `purchase_amount`: The amount of the purchase
   - `product_category`: Category of the product purchased

2. **Table: Customer_Interactions**
   - `interaction_id`: Unique identifier for the interaction
   - `customer_id`: Unique identifier for the customer
   - `interaction_date`: Date of the interaction
   - `interaction_type`: Type of interaction (view, click, add_to_cart, etc.)
   - `product_category`: Category of the product interacted with

3. **Table: Customer_Details**
   - `customer_id`: Unique identifier for the customer
   - `gender`: Gender of the customer
   - `age`: Age of the customer
   - `location`: Location of the customer
   - `profession`: Profession of the customer

## **Questions**
1. Customers are more likely to purchase a product if they have interacted with it more than 3 times in the past month. Write an SQL query to find the probability of purchase for each product category in the `Transactions` table given the conditions in the `Customer_Interactions` table. Explain how you use Bayes theorem in this context.

2. Assume we want to predict if a customer is likely to make a purchase in the next seven days based on their interaction data. Develop a supervised machine learning model using the features you think would be most relevant from the `Customer_Interactions` and `Customer_Details` tables. Explain your feature selection, the machine learning algorithm you chose and why.

3. Some products show a strong seasonal trend. Develop a time series model to forecast the transaction amount for each product category in the next month. Also, provide a confidence interval for your forecasts. Explain your model selection and how you evaluated its performance.

4. Develop a recommendation system to suggest products to customers based on their past interactions and purchases. The system should also consider the demographic details of the customers. Implement your model using Python and explain how you validated the results. Provide an SQL query to showcase the top 5 recommendations for a customer.

