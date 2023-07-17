
##1. Business Problem Statement

Rencently, one of our biggest clients in retail industry has such a problem, "As a retail company, we have recently implemented a loyalty program in a bid to enhance customer retention and increase sales. Our goal now is to leverage data science techniques to identify customer segments and tailor promotions to maximize the effectiveness of this program. We want you to create a predictive model to forecast customers' future purchase behavior based on their historical transactional data and demographic information. The result should help us identify who are our most valuable customers and how to personalize our marketing strategy accordingly."

## 2. Dataset Description:
### 2.1 Table 1: Transactional_Data
+ Transaction_ID (unique identifier of each transaction)
+ Customer_ID (unique identifier of each customer)
+ Product_ID (unique identifier of the product purchased)
+ Transaction_Date (date of the transaction)
+ Units_Sold (number of units sold per transaction)
+ Total_Amount (total amount spent on the transaction)

This table contains historical transaction data for each + customer. Each row represents a unique transaction, and the table records what product was purchased, when, and how much was spent.

### 2.2 Table 2: Customer_Demographics
+ Customer_ID (unique identifier of each customer)
+ Enrollment_Date (date when the customer enrolled in the loyalty program)
+ Age (customer's age)
+ Gender (customer's gender)
+ Location (customer's location, can be further broken down into city, state, country)
+ Income (estimated annual income of the customer)

This table contains demographic data for each customer. It records when they enrolled in the loyalty program, as well as personal demographic information such as age, gender, location, and estimated income.

The key shared column between these two tables is Customer_ID, which will allow you to merge these two datasets. The dynamic variable would be the Transaction_Date and Enrollment_Date, and all other columns would be the static variables.

The challenge involves cleaning, merging and analyzing these datasets, developing an accurate prediction model, and providing actionable insights based on your findings.

## 2. Generate Synthetic Data

## 3. Questions for the Data Challenge##
####3.1 Basic Questions###

- (3.1.1) How would you calculate the transaction density for each customer, defined as the average number of transactions made per month since their enrollment? Would you expect this to be a valuable feature for predicting future purchase behavior? (Transaction Density)

- (3.1.2) Can you generate a new feature called 'Product_Affinity' to reflect how much a customer prefers a specific product? This can be calculated as the number of units of a specific product bought by a customer divided by the total units of all products bought by the same customer. How might this influence our understanding of a customer's preferences?(Product Affinity)

- (3.1.3) How would you classify transactions into different time bins (e.g., morning, afternoon, evening, and night) based on the time related data in this data set if it also includes the time of the transaction? How could this influence our understanding of a customer's shopping habits?

#### **Answer 3.1.1**

#### **Answer 3.1.2**

#### **Answer 3.1.3**

####3.2 Feature Engineering###

- (3.2.1) Write a function to calculate the average number of days between transactions for each customer. If a customer has only one transaction, consider the recency from their first transaction to the latest transaction in the dataset. How might this feature help in identifying churn customers?

- (3.2.2) Compute a feature representing the ratio of unique products bought to the total number of transactions for each customer. This will provide an insight into how diversified the customer's purchases are. Does a higher ratio correlate with more loyal customers?

#### **Answer 3.2.1**

#### **Answer 3.2.2**

####3.3 Metric Selection ###

#### **Answer 3.3.1**

**Hint:**  This code begins by preprocessing the data for modeling, initially by creating several new features that could potentially assist in predicting customer churn:

'Average_Purchase': This feature calculates the average amount spent on each purchase by a customer.
'Purchase_Frequency': It represents the number of purchases a customer has made.
'Days_Since_Last_Purchase': This feature measures the number of days that have passed since a customer's most recent purchase.

These features are generated because they are commonly relevant in churn prediction. Customers who spend more, make purchases more frequently, or have made recent purchases are typically less likely to churn.

Next, the code introduces an 'is_high_income' column to identify customers with high income. High income is defined as an income above the 75th percentile of the income distribution. The dataset is then divided into two separate dataframes based on this income level.

Following this, the code proceeds to define churn. A customer is considered to have churned if they have not made a purchase within a specified period. The length of this period is adjusted until the dataset achieves balance, meaning it contains approximately equal numbers of churners and non-churners. This balance is important because many machine learning models, including logistic regression, tend to perform optimally when the target variable classes are balanced.

Finally, the code oversamples the high-income data, creating additional copies of the high-income instances until they are five times more prevalent than the low-income instances. The rationale behind this is that misclassifying a high-income customer as a non-churner incurs a higher cost compared to misclassifying a low-income customer. By oversampling the high-income data, the model is trained to be more sensitive to these instances and to accurately classify them.

The oversampled data is then divided into a training set and a testing set. A logistic regression model is trained using the training set and subsequently utilized to predict whether the instances in the test set will churn or not. The model's performance is evaluated by comparing these predictions to the actual churn status of the test instances.

Within the context of the business problem, this code aims to predict the customers most likely to churn, with a particular emphasis on high-income customers due to their higher value to the business. The code strives to achieve this goal while minimizing the costs associated with misclassification errors, particularly the cost of false negatives among high-income customers. By considering both the data patterns and the costs linked to different error types, the code provides a solution that is statistically robust and tailored to the specific business context.

#### **Answer 3.3.2**

The imbalance in the cost of misclassification can be addressed using a few different methods. Let's discuss them:

1. **Resampling:** This is the process of creating a balanced dataset by either oversampling the minority class, undersampling the majority class, or a combination of both. A popular method of oversampling is SMOTE (Synthetic Minority Over-sampling Technique), which creates synthetic samples of the minority class. However, oversampling can lead to overfitting if not done correctly. On the other hand, undersampling can cause the model to miss important information.

2. **Cost-Sensitive Training:** This is a method where the cost function used to train the model is modified to assign a higher penalty for misclassifying minority class examples. This would encourage the model to focus more on correctly classifying minority class. The class_weight argument in many Scikit-learn classifiers implements this.

3. **Ensemble Methods:** Methods like Random Forests and Gradient Boosting can handle imbalanced data by constructing a separate model for each class and then combining their predictions. BalancedRandomForestClassifier and EasyEnsembleClassifier in the imbalanced-learn library implement these methods.

4. **Use of different metrics:** Accuracy is not a good metric when dealing with imbalanced classes. Other metrics such as precision, recall, F1 score, and Area Under the Receiver Operating Characteristic curve (AUC-ROC) are more informative and useful in such cases.

5. **Anomaly Detection:** If the minority class represents an anomaly, anomaly detection algorithms like One-Class SVM or Isolation Forest can be used.

Use of Different Algorithms: Some algorithms like Decision Trees and k-Nearest Neighbors can handle imbalanced data better than others.

In addition to these, it's always beneficial to have a good understanding of the data and the business problem. Domain knowledge can sometimes suggest intuitive and effective ways to handle class imbalance. For example, in this case, if high-income customers have certain distinct behaviors, features capturing those behaviors could be helpful.

#### **Answer 3.3.3**

Yes, balancing a dataset can be achieved by resampling. This can be done in two ways:

1. **Oversampling:** This involves increasing the number of instances in the minority class to match the number of instances in the majority class. This can be done by randomly duplicating instances in the minority class. However, a more sophisticated method is to use the Synthetic Minority Over-sampling Technique (SMOTE). SMOTE works by selecting examples that are close in the feature space, drawing a line between the examples in the feature space and drawing a new sample at a point along that line.
Here's a basic example using oversampling in Python:

2. Undersampling: This involves decreasing the number of instances in the majority class to match the number of instances in the minority class. This can be done by randomly removing instances in the majority class.

In both methods, it is important to split your dataset into a training set and a testing set before applying the resampling techniques. Resampling before splitting the data can allow the exact same observations to be present in both the test and training sets. This can allow our model to simply memorize specific data points and cause overfitting and poor generalization to the test data.

Keep in mind that resampling does not always guarantee better results. Undersampling may lead to loss of information if the majority class is undersampled too much. On the other hand, oversampling can lead to overfitting since it makes exact replicas of existing observations. Always validate that your sampling techniques are improving your metrics with cross-validation or hold-out sets.

#### 3.4 Business Insight

#### **Answer 3.4**

Based on your model's findings and your feature engineering efforts, what insights could you offer to our marketing and customer relationship teams to improve their strategies and potentially increase customer retention and sales?

The model's findings and feature engineering can offer various insights to the marketing and customer relationship teams to improve their strategies:

Identify High-Risk Churn Customers: The model can identify customers who are at high risk of churn. These customers can be targeted with personalized marketing campaigns or special offers to encourage them to stay. The reasons for their high churn risk (such as lack of engagement with the product or negative customer service experiences) can inform these campaigns.

- Identify Key Product Features: Feature importance from the model can show what product features are most influential in customer retention. This can guide the marketing team in highlighting these features in their campaigns. It could also be useful for the product development team in focusing their efforts on improving these key features.

- Segment Customers for Targeted Marketing: The model's features can be used to segment the customers into different groups based on their behavior, demographics, product usage, etc. This can enable targeted marketing, where different strategies are used for different customer segments.

- Understand Seasonal Trends: If the model incorporates time-based features, it can help identify seasonal trends in customer behavior. This can guide the timing of marketing campaigns, new product launches, or customer relationship efforts.

- Predict Future Customer Behavior: The predictive nature of the model can give the teams a forward-looking tool to anticipate future customer behavior. This can inform proactive strategies to increase sales or prevent churn before it happens.

- Identify Factors Leading to Customer Satisfaction: The model might identify factors leading to customer satisfaction. Prioritizing these factors can improve customer relationships and increase retention.

Remember, while the model provides statistical insights, these should be used in combination with business knowledge and additional qualitative insights for effective strategy development.

