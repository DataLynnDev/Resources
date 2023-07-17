## 1. Business Problem Statement

The Customer Relationship Management (CRM) department of a leading telecommunications company is grappling with high customer churn rates, which are significantly impacting the company's profitability. Despite having a vast database of customer information, the CRM team lacks the necessary tools and expertise to leverage this data for anticipating and mitigating churn effectively. Recognizing the potential of data-driven decision-making, the CRM department's leadership has turned to Accenture for its expertise in advanced analytics. Their goal is to use their existing customer data to identify the customers most likely to churn, which would enable them to implement proactive retention strategies.

The task at hand involves undertaking a comprehensive data analysis exercise to identify indicators of churn. We need to examine these signals across different customer segments, integrate external market trends with churn indicators, and analyze churn patterns over time. Using these insights, we'll engineer features that accurately predict customer churn, build a predictive model, and subsequently, help the CRM department design strategies to enhance customer retention.

## 2. Data Challenge Tables


**Table 1: Customer_Profile**

This table contains the customer demographic data and account information.

| Feature Name | Description |
| ------------ | ----------- |
| Customer_ID | Unique identifier for each customer |
| Age | Age of the customer |
| Gender | Gender of the customer |
| Location | Geographic location of the customer |
| Subscription_Type | The type of plan the customer has subscribed to |
| Tenure | The number of months the customer has stayed with the company |
| Churn | Whether the customer has churned or not |

Sample head:

| Customer_ID | Age | Gender | Location | Subscription_Type | Tenure | Churn |
| ----------- | --- | ------ | -------- | ----------------- | ------ | ----- |
| 1001 | 45 | Male | NY | Plan_A | 24 | No |
| 1002 | 30 | Female | CA | Plan_B | 12 | Yes |
| 1003 | 55 | Female | TX | Plan_A | 36 | No |

**Table 2: Billing_Data**

This table includes the billing and payment information of each customer.

| Feature Name | Description |
| ------------ | ----------- |
| Customer_ID | Unique identifier for each customer |
| Monthly_Charge | Monthly charges for the services provided |
| Total_Charges | The total amount charged to the customer for the entire tenure |
| Payment_Method | The method used by the customer to make payments |
| Late_Payments | The number of late payments made by the customer |

Sample head:

| Customer_ID | Monthly_Charge | Total_Charges | Payment_Method | Late_Payments |
| ----------- | -------------- | ------------- | -------------- | ------------- |
| 1001 | 50 | 1200 | Credit Card | 1 |
| 1002 | 60 | 720 | Electronic Check | 2 |
| 1003 | 50 | 1800 | Bank Transfer | 0 |

**Table 3: Customer_Service_Records**

This table contains the records of the customer interactions with the service team.

| Feature Name | Description |
| ------------ | ----------- |
| Customer_ID | Unique identifier for each customer |
| Total_Calls | The total number of calls made by the customer to the service team |
| Total_Complaints | The total number of complaints logged by the customer |
| Resolved_Complaints | The number of complaints that were resolved |
| Unresolved_Complaints | The number of complaints that are unresolved |

Sample head:

| Customer_ID | Total_Calls | Total_Complaints | Resolved_Complaints | Unresolved_Complaints |
| ----------- | ----------- | ---------------- | ------------------- | --------------------- |
| 1001 | 5 | 2 | 2 | 0 |
| 1002 | 10 | 5 | 2 | 3 |
| 1003 | 3 | 1 | 1 | 0 |

**Table 4: Market_Trends**

This table incorporates the external factors and market trends.

| Feature Name | Description |
| ------------ | ----------- |
| Date | The date of the observation |
| Competitor_Offerings | The number of new offerings launched by competitors |
| Technological_Changes | The number of significant technological changes in the market |

Sample head:

| Date | Competitor_Offerings | Technological_Changes |
| ---- | -------------------- | --------------------- |
| 2023-01-01 | 2 | 1 |
| 2023-02-01 | 1 | 0 |
| 2023-03-01 | 3 | 1 |

## 3. Questions for the Data Challenge

**1. "Identification of Churn Indicators (SQL)"**

Utilizing the 'Customer_Profile', 'Billing_Data', and 'Customer_Service_Records' tables, extract key indicators that could potentially signal customer churn. This might involve metrics like the frequency of service complaints, payment patterns, and changes in usage. How would you utilize SQL to process and analyze these data sets and define churn indicators? Describe the peculiarities you might expect in each churn signal group.

**Answer:**

Using Python, we can utilize the pandas library to merge and analyze the data. For SQL, we can use JOIN and GROUP BY statements to analyze patterns. The primary churn indicators can be total complaints, unresolved complaints, late payments and tenure with the company.

------

Peculiarities:

- More unresolved complaints and late payments could indicate higher churn.
- Lower tenure may suggest a higher likelihood of churn, since customers who've been with the company for a shorter period might be less loyal.



**2. "Analysis of Churn Indicators Across Different Customer Segments (Python)"**

Dive deeper into the customer segments that have high churn rates. Using Python, identify patterns in the churn indicators across different customer demographics like age, location, or subscription type. Discuss your approach in handling cases where some segments have sparse data. Explain how your findings could refine the understanding of customer churn across different segments.

**Answer:**

We can analyze churn indicators across different customer segments (e.g., by location, age, and subscription type). 

------

Handling sparse data: If a certain segment has sparse data, we might need to group categories together or treat them as a separate "Other" category. The key is to ensure we don't make inferences on segments where the sample size is too small to be statistically significant.



**3. "Investigation of the Impact of Complaint Resolution on Churn in High-Tenure Customers (Python)"**

High-tenure customers are generally more valuable for a company. Preserving their loyalty and reducing their churn rate is critical. Assume that you've noticed a higher churn rate amongst high-tenure customers who have unresolved complaints. Using Python, perform an analysis to confirm if unresolved complaints significantly influence the churn rate in high-tenure customers compared to those with resolved complaints.

Moreover, propose an actionable strategy for reducing churn in this specific customer segment based on your findings. Discuss how your findings might shape the company's customer service approach for high-tenure customers and detail how it could potentially improve customer satisfaction and reduce churn in this segment.

**Answer:**

To investigate the impact of unresolved complaints on churn in high-tenure customers, we can first filter the 'Customer_Profile' and 'Customer_Service_Records' tables to focus only on high-tenure customers. High-tenure can be defined based on the business context, but for the purpose of this task, let's consider customers with a tenure greater than the average tenure as high-tenure customers.

Then, we can compute the churn rate for high-tenure customers with unresolved complaints and compare it with the churn rate for high-tenure customers without unresolved complaints.

Based on the churn rates obtained from this analysis, if high-tenure customers with unresolved complaints indeed have a significantly higher churn rate, it would suggest that improving complaint resolution might be an effective strategy for reducing churn in this customer segment.

A potential action plan could be to introduce a priority support program specifically for high-tenure customers. The service team could be alerted to resolve complaints from these customers as quickly as possible. Additionally, regular follow-ups can be conducted to ensure their issues are fully resolved and they are satisfied with the service. This proactive approach might help improve customer satisfaction, leading to a reduction in churn rate.

Also, it is important to track the effectiveness of these measures by monitoring the churn rate of this segment over time after implementing the changes.



**4. "Creating Customer Interaction Graphs (Python)"**

Customers often interact with the telecommunication service in multiple ways - through calling customer service, online chat, billing, service usage, etc. Using Python, construct a graph data structure to map these interactions for a set of customers, specifically focusing on the total number of service calls made by customers. Explore and describe any emergent patterns in this graph that could signal churn. Discuss the implications of densely connected subgraphs, isolated nodes, and loosely connected nodes with respect to their service call behavior.

**Answer:**

The goal of this question is to create a graph where each node represents a customer and edges between nodes represent some form of interaction or common feature between customers. This could be particularly useful in identifying clusters of customers that have similar behavior.

Let's simplify this with an example by using 'Total_Calls' to the service team as an interaction feature and only using a subset of customers to keep the graph manageable. We'll create a graph where an edge between two nodes (customers) exists if their number of calls to the service team is in the same range (for instance, 0-5 calls, 6-10 calls, etc.).

First, we need to categorize 'Total_Calls' into ranges. We can use the pandas cut() function to create these categories. Then, we'll create the graph using NetworkX, a Python package for the creation, manipulation, and study of the structure, dynamics, and functions of complex networks.

------

In this graph, each node is a customer and an edge between two customers indicates that they made a similar number of calls to the service team. By analyzing this graph, we can identify clusters of customers who have similar behavior in terms of service calls.

Here's how to interpret this graph:

1. **Densely Connected Subgraphs (Clusters):** These groups correspond to customers who share similar behavior, in this case, making a similar number of service calls. Analyzing these clusters can reveal common patterns and characteristics. For example, if a significant number of customers from a high churn risk demographic are found in a cluster with high call volumes, it might indicate dissatisfaction and a potential risk of churn.

2. **Isolated Nodes or Loosely Connected Nodes:** These represent customers whose 'Total_Calls' range is not common among the considered dataset. It does not directly indicate satisfaction or dissatisfaction but shows that their service call behavior is unique compared to the analyzed subset of customers.


**5. "Feature Engineering for Churn Prediction (Python)"**

Develop new features such as 'Average_Service_Complaints', 'Payment_Frequency_Change', and 'Usage_Decrease' ratios from the identified churn indicators. Using Python, examine how these engineered features contribute to predicting customer churn. Elaborate on how these newly created features could potentially enhance the predictive power of the churn model.

**Answer:**

1. **Average_Service_Complaints:** We can compute this as the ratio of 'Total_Complaints' to 'Tenure' (assuming 'Tenure' is in months and complaints are logged monthly).

2. **Payment_Frequency_Change:** This feature requires sequential payment data to accurately calculate changes in payment frequency. As it's not available in the current dataset, we can simulate this feature by assuming a direct relationship between 'Late_Payments' and 'Payment_Frequency_Change'.

3. **Usage_Decrease:** This feature typically requires sequential usage data. Without such data, we can use a proxy - for example, if 'Total_Charges' is less than the product of 'Monthly_Charge' and 'Tenure', we can interpret it as a usage decrease. This implies the customer is not fully utilizing the services they're paying for.

------

Now we have a new dataframe, `Customer_Service_Records`, augmented with the features 'Average_Service_Complaints', 'Payment_Frequency_Change', and 'Usage_Decrease'.

When building a predictive model for churn, these new features could enhance the model's performance by providing more nuanced information about customer behavior.

1. **Average_Service_Complaints:** This feature gives an average rate of service complaints per month. Higher values may signal customer dissatisfaction, increasing the likelihood of churn.

2. **Payment_Frequency_Change:** Customers who frequently change their payment method or have late payments might be considered financially unstable or unsatisfied, which could increase the risk of churn.

3. **Usage_Decrease:** If customers are paying for services they're not fully utilizing, they might perceive a lack of value, increasing their likelihood to churn.




**6. "Development and Optimization of Churn Prediction Model (Python)"**

Given the insights and features derived from the previous questions, identify which could be most predictive of customer churn. Noting the presence of imbalanced data, discuss your approach to handle this situation for robust churn prediction. Specifically, try both oversampling and undersampling techniques, and compare their performance. Implement a predictive model in Python using these features and elaborate on how this model will steer proactive customer retention strategies. Validate your model to prevent overfitting and demonstrate how the model's outcomes could be integrated into business strategies to decrease overall churn rates and heighten profitability. Discuss how your handling of imbalanced data affects your model's performance and your interpretation of the results.

**Answer:**

First, we define a grid of hyperparameters that we want to tune in the random forest model. Then, we create an instance of the RandomForestClassifier and a GridSearchCV object, to which we pass the classifier, the parameter grid, and the number of folds for cross-validation.

We fit this GridSearchCV object to the data, which performs cross-validation and hyperparameter tuning. The best parameters and score are then printed out.

The model is then used to predict on the test data, and a classification report is printed to show the precision, recall, f1-score, and support for each class.

Finally, we plot the feature importances. The random forest model allows us to inspect the importance of each feature in predicting churn. This can guide proactive customer retention strategies by focusing on the features that contribute most significantly to churn. For instance, if 'Average_Service_Complaints' is a major contributor, strategies could focus on improving customer service response times or quality. If 'Payment_Frequency_Change' is significant, the company might consider more flexible or varied payment options to retain customers.

------

From the results, you can see that over-sampling with SMOTE produced a model with better overall accuracy, precision, and F1-score on the test set than the under-sampling method. However, it is important to note that the recall for the churned customers (1) was higher in the model trained on the under-sampled data, which might be significant if correctly identifying churned customers is the main priority.

The choice between these two models depends on the specific business context. If it's more important to catch as many churned customers as possible (potentially at the cost of misclassifying some non-churned customers as churned), the model trained with under-sampling might be preferable. However, if overall performance on all metrics is the main goal, the model trained with over-sampling appears to perform better.
