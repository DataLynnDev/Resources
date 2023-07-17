# Interview Challenge -- BNY Mellon

## 1. Business Problem Statement

As BNY Mellon, we continuously strive to optimize our portfolio risk management strategies. A critical part of this process is to predict potential credit default risks for our customers. To improve our predictive capabilities, we need to leverage our extensive customer and transaction data to build a machine learning model that accurately forecasts the probability of default for each customer.

Your task is to develop a model using the provided datasets, taking into account static customer attributes and dynamic transaction data.

## 2. Data Challenge Table

### Table 1: Customers
|Column Header|	Description |
|---------------|---------------------------------------------------|
|customer_id |	Unique identifier for each customer|
|age |	Age of the customer|
|job |	Type of job of the customer|
|marital_status|	Marital status of the customer|
|education_level|	Highest level of education attained by the customer|
|default_history|	Whether the customer has a history of credit default (Yes, No)|
|housing_loan_status|	Whether the customer has a housing loan (Yes, No)|
|personal_loan_status	| Whether the customer has a personal loan (Yes, No)|
|credit_score |	Credit score of the customer, range from 300-850|

### Table 2: Transactions
|Column Header|	Description |
|---------------|---------------------------------------------------|
|transaction_id |	Unique identifier for each transaction|
|customer_id |	Unique identifier for each customer|
|date |	Date of the transaction|
|transaction_amount |	The amount of the transaction|
|transaction_type	| The type of the transaction (Deposit, Withdrawal)|
|balance_after_transaction|	The balance of the customer's account after the transaction|

### Load data

## 3. Questions for the Data Challenge

### 3.1 Data Manipulation

- If you notice that certain customer records are missing in the transaction data, how would you modify your data consolidation process to accommodate this? What impact might this have on your analysis?

- Suppose you find that some customers have transactions recorded before their account creation date. How would you address this discrepancy?

**Ans** 3.1.1: If certain customer records are missing in the transaction data, this may mean that these customers have not made any transactions yet. In order to accommodate this in data consolidation, we could perform a left join on the customer data with the transaction data. This way, all customer records will be kept, and for those without transaction data, the transaction fields will be filled with NaN or some other placeholder value.

Here's how you can do this in Python:

**Ans** 3.1.2: If customers have transactions recorded before their account creation date, this seems like a data quality issue. One way to handle this would be to ignore or remove these transactions as they might be errors. Another approach could be to update the account creation date to the date of the first transaction if it's earlier than the current recorded creation date.

Suppose we have 'account_creation_date' column in customers DataFrame, here is a python code snippet demonstrating this approach:

### 3.2 Metric Selection

- Imagine you are presenting your model to stakeholders who are not data scientists. They are interested in the model's performance but find traditional classification metrics hard to interpret. How would you quantify the model's performance in a more intuitive way?

- Consider the imbalance of classes in the 'default_history' variable (assuming more customers have 'No' than 'Yes'). How might this impact the performance metric you chose, and how would you address this issue?

**Ans** 3.2.1: Presenting Model's Performance in an Intuitive Way:

When communicating model performance to non-technical stakeholders, it's crucial to use clear, intuitive and business-oriented terms. Here are a couple of ways to do that:

- Accuracy: We could start by explaining the overall accuracy of the model - i.e., "Our model correctly predicts whether or not a customer will default on their credit 85% of the time." However, accuracy can be misleading if the classes are imbalanced, so it's not the best metric in isolation.

- Confusion Matrix in Layman's Terms: We could break down the performance in terms of True Positives, False Positives, True Negatives, and False Negatives - but using more understandable language. For example, "Out of 100 customers, our model correctly identified 70 customers who were going to default on their credit, and missed 30. However, it also mistakenly identified 10 customers as potential defaulters who actually paid off their credit."

- Cost-Benefit Analysis: We could tie the model's predictions back to business outcomes or costs. For instance, "By using our model, we can reduce the amount of bad debt by 50%, which could save our company $X per year."

**Ans** 3.2.2: Handling Imbalanced Classes in 'default_history':

- Impact on Performance Metrics: The issue with imbalanced classes is that it can cause the model to be biased towards the majority class, and the performance metrics can be misleading. For example, if 95% of customers have 'No' for default history, a naive model that always predicts 'No' will have 95% accuracy, but it is not actually useful.

- Resampling Techniques: We could either oversample the minority class, undersample the majority class, or do a combination of both. This can help to balance the classes and improve model performance on the minority class.

- Use Appropriate Evaluation Metrics: Precision, Recall (Sensitivity), F1-score, and Area under the ROC Curve (AUC-ROC) are better metrics for imbalanced datasets. For instance, recall will tell us how well the model is able to find the positive class, and precision will tell us out of the predicted positive instances, how many of them are actually positive.

- Use Class Weights: Some algorithms allow us to set higher penalties for misclassifying minority classes. This can make our model pay more "attention" to these classes.

In the context of credit default, it is usually more important to correctly identify the customers who will default (True Positives), even if it means wrongly flagging some customers as potential defaulters when they are not (False Positives). The cost to the company of a False Negative (a defaulter going undetected) is usually much higher than that of a False Positive.

As an example, we oversample the minority class and undersample the majority class in the following code.

There is a library in Python called imbalanced-learn which is a popular choice to handle imbalanced datasets. Let's use it to oversample the minority class using the SMOTE (Synthetic Minority Over-sampling Technique) method.

### 3.3 Feature Engineering

- Our stakeholders believe that customers' banking behavior may exhibit certain patterns during different times of the year. How would you engineer the 'date' feature to capture this?

- Given the transaction data, propose three creative features that might predict a customer's default risk. Explain why you expect them to be useful.

**Ans** 3.3.1: To engineer the 'date' feature to capture patterns during different times of the year, you can extract the month and quarter from the date. You might also consider the day of the week, as banking behavior could vary between weekdays and weekends.

Here's the Python code to transform the 'date' feature:

**Ans** 3.3.2: Three creative features that might predict a customer's default risk:

- Transaction Frequency: The number of transactions a customer makes could be indicative of their financial stability. Customers who make transactions more frequently might be more financially active and possibly less likely to default.

- Average Transaction Amount: If a customer's average transaction amount is high, this could indicate that the customer is in a good financial position. Conversely, customers with lower average transaction amounts might have a higher risk of default.

- Monthly Balance Trend: You could create a feature that represents the change in a customer's balance over time (e.g., monthly). If a customer's balance is consistently decreasing, it might suggest that they're spending more than they're earning, which could increase their default risk.

### 3.4 Model Selection

Predict potential credit default risks for our customers considering dynamic transaction data?

**Ans** 3.4:

Meanwhile, we can visualize the model's results with a confusion matrix and a ROC curve.

The confusion matrix visualizes the performance of the model in terms of true positives, true negatives, false positives, and false negatives.

The ROC curve visualizes the trade-off between the true positive rate (sensitivity) and the false positive rate (1-specificity). The area under the ROC curve (AUC) is a summary measure of the model's performance. The closer the AUC is to 1, the better the model's performance.

### 3.5 Model Optimization

Let's say your model's performance has room for improvement. Can you think of a non-traditional approach you could take to enhance your model, leveraging the specific context of our data or problem?

**Ans** 3.5: Given the nature of the data and the problem, ensemble methods could indeed be a good choice. Ensemble methods combine the predictions of several base estimators to improve generalizability and robustness.

Some potential ensemble methods that could be used are:

- Random Forests: This method builds a multitude of decision trees and merges them together to get a more accurate and stable prediction. Random forests are good at handling a mix of numerical and categorical features, and they can also capture non-linear relationships.

- Gradient Boosting: Gradient Boosting builds an additive model in a forward stage-wise fashion; it allows for the optimization of arbitrary differentiable loss functions. Gradient boosting could be particularly useful if your data has complex, non-linear relationships that simpler models like logistic regression can't capture.

- Stacking: Stacking involves training multiple different models and then combining their predictions with another model (the "meta-learner") to make a final prediction. Stacking can be powerful because it can capture the strengths of each individual model.

The choice of ensemble method (or any other model) should ultimately be guided by cross-validation performance, and the trade-offs between model performance, interpretability, and computational efficiency.

The following is an example code demonstrating how to ensemble the above logistic regression model with a random forest classifier.

### 3.6 Model Evaluation and Business Insights

- Assume your model is now in production and making predictions on new customers. How would you set up a system to evaluate whether the model's predictions are remaining accurate over time? Write a Python script demonstrating your approach.

- Discuss how you would set up a system to monitor and update your model over time. What potential issues would you anticipate, and how would you address them?

**Ans** 3.6: Setting up a system to monitor and update models over time involves a few key steps:

- Performance Tracking: Regularly evaluate the model's performance using appropriate metrics. This often involves maintaining a validation dataset that the model has not been trained on. The frequency of evaluation will depend on the nature of the problem, the model, and the rate at which the data changes.

- Anomaly Detection: Set up automated anomaly detection. For instance, if the distribution of predictions or input features changes significantly, this could be a sign of a problem, such as a shift in the input data distribution or a bug in the data pipeline.

- Alerting: Establish a mechanism to alert the team when the model's performance drops below a certain threshold or when anomalies are detected. The alert system should ideally provide enough information to allow the team to diagnose the problem.

- Updating: Have a plan for updating the model, either by retraining it on new data or by replacing it with a new model. This process can also be automated, but it's important to have checks in place to ensure that the new model is actually an improvement.

Potential issues to anticipate:

- Concept Drift: Over time, the relationship between the input features and the target variable may change. This concept drift can reduce the model's performance. This can be addressed by regularly retraining the model or by using techniques specifically designed to handle concept drift.

- Data Quality Issues: Errors may occur in the data pipeline, leading to missing or incorrect data. These issues should ideally be detected and addressed as soon as possible. Setting up data validation checks can help detect such issues.

- Overfitting during Update: When retraining or replacing the model, there's a risk of overfitting to the most recent data. It's important to continue using cross-validation or a separate validation set to ensure that the updated model generalizes well.

- Dependencies on External Systems: If your model training pipeline relies on external systems (e.g., for data storage or compute resources), any changes or outages in those systems could impact your ability to update the model.

- Computational Resource Limitations: Depending on the size of the dataset and the complexity of the model, training the model could be computationally intensive. It's important to plan for these computational needs and ensure that the necessary resources are available when it's time to update the model.

By planning for these potential issues and setting up a robust monitoring and updating system, you can help ensure that your model continues to perform well over time.