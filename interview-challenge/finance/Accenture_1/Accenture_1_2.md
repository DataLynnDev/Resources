## 1. Business Problem Statement

An e-commerce company has commissioned Accenture to help them predict customer review scores, specifically identifying customers who are likely to give high scores and those who are likely to give low scores. This information will enable the company to intervene and take appropriate actions to encourage low-scoring customers to provide higher ratings.

Your task is to develop a predictive model that can accurately classify customers as high-scoring or low-scoring based on their review behavior. The model should provide insights to help the company identify and target low-scoring customers, encouraging them to improve their ratings and overall satisfaction.

The challenge requires you to work with two data sets provided below:



## 2. Data Challenge Table

### Table 1: Customer Orders (`orders.csv`)

| Column Name   | Description                                          |
|---------------|------------------------------------------------------|
| OrderID       | Unique ID for each order                             |
| CustomerID    | Unique ID for each customer                          |
| ProductID     | Unique ID for each product                           |
| OrderDate     | The date when the order was placed                   |
| DeliveryDate  | The date when the order was delivered to the customer|
| Quantity      | The number of items in the order                     |



### Table 2: Product Reviews (`reviews.csv`)

| Column Name   | Description                                          |
|---------------|------------------------------------------------------|
| ReviewID      | Unique ID for each review                            |
| CustomerID    | Unique ID for each customer                          |
| ProductID     | Unique ID for each product                           |
| ReviewDate    | The date when the review was posted                  |
| ReviewScore   | The score given by the customer (1-5)                |


## 3. Questions for the Data Challenge

### 1. Data Manipulation

#### 1.1 **Question**: 
In the `orders.csv` table, for each customer, can you find out the total number of orders placed by them and also rank these customers based on the total quantity of items they've ordered? Consider using a window function to achieve this.

**Answer:**

To find out the total number of orders placed by each customer and rank these customers based on the total quantity of items they've ordered, you might use the SQL query below. This query uses `GROUP BY` to aggregate orders by `CustomerID` and `SUM` to calculate total quantity. The window function `RANK()` is used to rank customers based on total quantity:

#### 1.2 **Question**: 

We have a hypothesis that customers who order in larger quantities might give lower review scores due to heightened expectations or increased likelihood of issues with larger orders. Can you explore this by segmenting customers based on the total quantity of their orders and comparing the average review scores in each segment?

**Answer:**

 To explore the hypothesis that customers who order in larger quantities might give lower review scores, you might need to link data from both the `orders` and `reviews` tables, then segment customers based on their total order quantity, and finally compare average review scores within each segment. The SQL code could be:

In this code, common table expressions (CTEs) are used to break down the problem into several subproblems, making the code more readable and easier to debug. The `CASE` statement is used to divide customers into 'Low Quantity', 'Medium Quantity', and 'High Quantity' segments based on the total quantity of their orders. The final result shows the average review score within each of these segments.



### 2. Feature Engineering

#### 2.1 **Question**: 

Based on the `ReviewScore`, we might categorize customers into different satisfaction levels. How would you create this new categorical feature from the `ReviewScore`? What are the potential implications and uses of this new feature for our marketing efforts?

**Answer:**

This new feature, `SatisfactionLevel`, can be used to segment customers based on their satisfaction levels. These insights can be used to improve customer service, product quality, and overall customer experience.

#### 2.2 **Question**: 

How could we quantify the customer's purchasing frequency? What kind of feature engineering would you propose to create a feature that represents this information? What potential insights could this feature offer?

**Answer:**

`OrderFrequency` column in customer_orders_df DataFrame represents the number of orders placed by each customer. This feature can give insights into customer loyalty and identify potential high-value customers.

#### 2.3 **Question**: 

Our dataset includes dates of order placement, delivery, and review submission. Can you think of ways to transform these raw dates into useful features that might affect a customer's review score? For instance, could the time taken for delivery or the time gap between delivery and review submission have an impact on the customer's satisfaction?

**Answer:**

First, let's generate some assumptions or hypotheses about how these features might impact the review score:

1. Delivery time: The time taken from order placement to delivery could influence customer satisfaction. Customers are likely to be more satisfied if their orders are delivered promptly.

2. Review delay: The gap between the delivery date and the date of review submission could also provide some insights. For instance, a customer who had a negative experience might be more likely to leave a review immediately after receiving their order.

With these hypotheses, we can create new features:

1. Delivery duration: This will be calculated as the difference between the delivery date and the order date.

2. Review delay: This is the difference between the review date and the delivery date.

Let's go ahead and implement these in Python.

### 3. Machine Learning Modeling

#### 3.1 Question

 In the case that our review scores are heavily skewed, with far more high-scoring reviews than low-scoring ones, this can create challenges in training a model. How would you tackle this issue during model selection and optimization? Please discuss potential strategies and their implications.

**Answer:**

Handling imbalanced datasets is a critical step in machine learning model selection and optimization. There are a few strategies that can be used:

1. **Resampling techniques**: These can be either under-sampling the majority class, over-sampling the minority class, or a combination of both. One common method is Synthetic Minority Over-sampling Technique (SMOTE), which synthesizes new examples in the minority class.

    - Pros: It can help to balance class distribution and provides more data for the model to learn.
    - Cons: Over-sampling can lead to overfitting if synthetic examples are too close. Under-sampling can result in loss of data.

2. **Cost-sensitive training**: This is a method where you assign a higher cost to misclassification of the minority class. Many algorithms have a parameter to weigh classes such as `class_weight` in sklearn models.

    - Pros: It can achieve good performance without losing information.
    - Cons: It can introduce bias as we give more importance to a specific class.

3. **Ensemble methods**: Ensemble methods, such as Random Forest or Gradient Boosting, can be less sensitive to class imbalance.

4. **Evaluation metrics**: Since accuracy can be misleading when classes are imbalanced, it's often more appropriate to use metrics like Precision, Recall, F1-score, ROC AUC, etc.

For the given dataset, a potential strategy could be using SMOTE for over-sampling and training a cost-sensitive Random Forest classifier. The code below is an example of how to do this with Python's imbalanced-learn and sklearn libraries:

#### 3.2 Question

The model seems to have difficulty in correctly classifying classes 1, 2 and 3. What do you think could be contributing to this issue? How would you go about investigating the causes?

**Answer:**

There could be several reasons why the model is having difficulty classifying classes 1, 2 and 3:

1. **Class Imbalance**: Even though SMOTE was used to oversample minority classes, it might not be enough or effective for the specific data distribution of our problem. SMOTE creates synthetic samples which may not fully represent the nuances of the minority classes.

2. **Feature Representation**: It's possible that the features we are using do not contain enough discriminative information to distinguish between classes 1, 2 and 3.

3. **Model Complexity**: Random Forest, while powerful, might not be the optimal model for this task. It could be the case that the decision boundaries between these classes are not as simple and a more complex model could be needed.

To investigate the causes, we could:

1. **Inspect the Feature Importance**: Random Forest provides a way to measure feature importance. We can inspect the most influential features in our model and check if they make sense intuitively.

2. **Check the Distribution of Classes**: By checking the distribution of classes in the dataset, we might find some patterns or imbalances that could be addressed.

3. **Evaluate Other Models**: If the data and features seem fine, maybe Random Forest isn't the optimal model for this task. Trying out different models (like SVM, XGBoost or neural networks) and comparing their performance might provide some insight.

Here's some sample Python code to carry out these steps:

### 4. Business Insight

#### 4.1 Question

Assuming the machine learning model has identified some customers as potentially valuable, how would you suggest the marketing team to leverage this information for optimizing marketing efforts?

**Answer:**

The marketing team can leverage this information to optimize marketing efforts by implementing personalized marketing strategies for these valuable customers. Some suggestions include:

- Developing targeted marketing campaigns: Create tailored marketing messages and offers specifically designed to appeal to the identified valuable customers. This can be based on their preferences, past purchase behavior, or other relevant factors.

- Implementing loyalty programs: Offer exclusive benefits or rewards to incentivize valuable customers to continue their engagement and increase their loyalty. This can encourage repeat purchases and foster long-term relationships.

- Upselling and cross-selling: Identify complementary products or services that align with the valuable customers' interests or needs and promote them strategically. This can increase the average order value and maximize the customer's lifetime value.

- Personalized communication: Use customer segmentation techniques to segment the valuable customers based on their characteristics or behaviors. Deliver personalized messages through targeted email campaigns, social media ads, or other communication channels to enhance engagement and conversion rates.

Explanation:
By identifying valuable customers through the machine learning model, the marketing team can customize their marketing efforts to specifically target and engage these customers. This approach helps to maximize the effectiveness of marketing campaigns, increase customer satisfaction, and drive business growth.

#### 4.2 Question

The model has determined that certain consulting services are highly valued by clients, leading to higher satisfaction scores. How would you suggest the consulting team leverage this information to improve client relations and service offerings?

**Answer:**

To leverage this information and improve client relations and service offerings, the consulting team can consider the following steps:

- Strengthening expertise in high-value services: Allocate resources to enhance the team's expertise and capabilities in the consulting services that are highly valued by clients. This can involve training programs, knowledge sharing sessions, or hiring experts in those domains.

- Tailoring service offerings: Develop customized service packages that highlight the high-value consulting services and address specific client needs. Offer these packages as premium options to clients who prioritize those services, providing them with a differentiated and tailored experience.

- Case studies and success stories: Showcase successful projects and client outcomes related to the high-value consulting services. Use these case studies and success stories to demonstrate the value and impact of these services, building trust and confidence among potential clients.

- Client feedback and satisfaction monitoring: Continuously collect and analyze client feedback and satisfaction scores related to the high-value consulting services. Identify areas for improvement and proactively address any issues or concerns raised by clients to maintain high satisfaction levels.

Explanation:
The consulting team can leverage the insight that certain consulting services are highly valued by clients to focus their efforts and resources on those areas. By strengthening expertise, tailoring service offerings, highlighting success stories, and actively monitoring client satisfaction, the team can enhance client relations, deliver exceptional service experiences, and drive client loyalty and retention.

#### 4.3 Question

Our model found that clients who utilized a combination of services tend to have higher satisfaction scores. How can this information be used to cross-sell our services and improve overall client satisfaction?

**Answer:**

To cross-sell services and improve overall client satisfaction based on the insight that clients who utilize a combination of services tend to have higher satisfaction scores, the following strategies can be implemented:

- Service bundling: Create service bundles that combine complementary services based on the identified patterns. Offer these bundles as value-added options to clients who are already utilizing one service, promoting the benefits of a holistic and integrated approach.

- Personalized recommendations: Analyze client usage patterns and preferences to generate personalized recommendations for additional services that are likely to enhance their overall experience. This can be achieved through targeted emails, personalized landing pages on the website, or account managers providing tailored suggestions.

- Collaborative approach: Foster collaboration and communication between different service teams to ensure a seamless experience for clients who are utilizing multiple services. Encourage cross-functional knowledge sharing and coordination to deliver a unified and cohesive service offering.

- Client education: Proactively educate clients about the benefits and value of utilizing a combination of services. Share success stories and case studies showcasing the positive outcomes achieved by clients who have taken advantage of integrated service offerings.

Explanation:
By leveraging the insight that clients who use a combination of services have higher satisfaction scores, cross-selling strategies can be implemented to encourage clients to explore and utilize additional services. These strategies aim to enhance the client experience, provide holistic solutions to their needs, and improve overall satisfaction levels.

