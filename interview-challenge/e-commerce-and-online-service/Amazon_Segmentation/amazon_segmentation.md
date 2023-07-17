# Amazon Data Scientist Mock Interview
The goal of this data challenge is to assess the candidate's skills in data manipulation, feature preprocessing and engineering, customer segmentation, and extracting business insights. The candidate will be asked to answer a series of questions using SQL nad Python. 

## Business Problem: 
The marketing team is eager to launch a personalized marketing campaign but currently lacks insights on distinct customer segments. At the same time, they want to develop a way to predict which customers are more likely to make a purchase after clicking on a product, which could significantly help in optimizing our product recommendation system.

## Questions Roadmap
    - Data Manipulation
        - Data Manipulation in SQL
        - Feature Engineering
    - Segmentation
        - Feature Preprocessing
        - Clustering
        - PCA
    - Modeling
      - KNN
      - Class Weight Balacing
    - Business Insights

## Dataset Information:
 Below are the three data tables that we would use in this challenge. The 'Purchased' variable in the customer_behavior data table is the target varaible.

### Customers: 

|Column	| Description |
|--------------|-------------|
 Customer_Id | unique identifier for each customer
 Age | customer age, ranging from 18 to 70
 Gender | gender of the customer, F stands for female and M stands for male
 Location | location of the customer, represented by city A to D
 Tenure |number of years since the customer signed up
 Avg_Session_Duration_min | the average time that each customer spend on each session in minutes
 No_of_Purchases | the total number of purchases this customer has made

### Products: 

|Column	| Description |
|--------------|-------------|
 Product_Id | unique identifier for each product
 Category	| category of the product, including electronics, clothing, beauty and book
 Brand | the brand of this product
 Rating | average customer rating of the product

 ### Customer_behavior:

|Column	| Description |
|--------------|-------------|
Customer_Id | unique identifier for each customer
Product_Id | unique identifier for each product
Clicked | indicator of whether this customer has clicked on the link to this product, meaning that this customer viewed the product
Added_to_Cart | indicator of whether this customer added this product to their shopping cart
Purchased(TARGET VARIABLE) | indicator of whether the customer purchased this product (0 means not purchased and 1 means purchased)

# Solution Overview
### 1. SQL
#### 1.1 
- **SELECT category, COUNT(product_id) as product_count**: This part of the query selects the 'category' column and the count of 'product_id' in each category from the 'products' table. It gives us the number of products in each category. The result of this count is given the alias 'product_count'.

- **(SELECT brand FROM products as p2 WHERE p2.category = products.category GROUP BY brand ORDER BY COUNT(product_id) DESC LIMIT 1) as top_brand**: This is a subquery that is executed for each 'category' in the outer query. For each category, it selects the 'brand' column from a derived table (alias 'p2'), where the 'category' in the derived table matches the 'category' in the outer query. It then groups the records by 'brand', orders them in descending order based on the count of 'product_id' (which gives us the brand with the most products at the top), and takes only the top record using the LIMIT 1 clause. This essentially gives us the brand with the most products in each category. The result of this subquery is given the alias 'top_brand'.

- **GROUP BY category**: This groups the selected data by 'category'. For each unique 'category', the query will return one record in the result set.

#### 1.2 
- **CASE WHEN ... THEN ... END as age_group**: It categorizes the customers into age groups based on their age. The ages are divided into six groups: '18-25', '26-35', '36-45', '46-55', '56-65', and '66 and above'. The resulting age group is labeled as 'age_group'.

- **AVG, MIN, MAX**: calculates the average duration, shortest session and longest session within each age group. 

#### 1.3
- **WITH customer_spent AS (...)**: This section is a common table expression (CTE) that calculates the total amount of money each customer has spent in each product category.

- **ranked_customers AS (...)**: This is another CTE that assigns a row number to each customer within their respective location, sorted by the number of purchases they've made in descending order. The function **ROW_NUMBER() OVER(PARTITION BY location ORDER BY no_of_purchases DESC) as row_num** plays a crucial role here. It generates a unique row number for each customer within their respective location (due to **PARTITION BY location**), in the order of the number of purchases made in descending order **(**ORDER BY no_of_purchases DESC**). As a result, for each location, the customer with the highest number of purchases gets the row number 1, the second highest gets the number 2, and so on.

- **SELECT customer_id, location, no_of_purchases, category, total_spent FROM ranked_customers WHERE row_num <= 5**: In the final step, the query selects only those customers who have a row number of 5 or less. This effectively means we get the top 5 customers (based on the number of purchases) from each location, along with their associated customer ID, location, number of purchases, product category, and total amount spent.

### 2. Feature Engineering

#### 2.1 
The rationale behind this feature is that customers' online shopping behaviors often follow a certain pattern or 'funnel.' Initially, a customer may click on multiple products while browsing, indicating a general interest. However, a more committed intent to purchase is signified when the customer adds a product to the cart. By taking the ratio of these two actions (number of items added to the cart over the number of items clicked), we create a numerical representation of this pattern.

#### 2.2
The goal here is to develop a deeper understanding of each customer's product preferences by identifying the product categories they engage with most frequently. These preferences are inferred from their browsing habits, specifically the product categories they click on the most.

To achieve this, the customer_behavior and products datasets are merged together, providing a comprehensive view of each customer's interactions with different product categories.

By incorporating this feature, we are better equipped to understand and anticipate customer preferences, which can significantly inform and enhance personalization strategies, targeted marketing campaigns, and product recommendations.

#### 2.3
This is a simple question. We only need to merge the two datasets together on 'Customer_Id'. 

### 3. Customer Segmentation
#### 3.1 
**Standardization:** K-means is sensitive to the scales of the features. Therefore, it's important to standardize the features so that they have a similar scale. This is typically done by subtracting the mean and dividing by the standard deviation.

**Convert Categorical Variables:** K-means operates in a Euclidean space, and as such, it's not directly applicable to categorical variables. We need to convert them to numerical format, typically via one-hot encoding.

#### 3.2
The silhouette score is a measure of how close each point in one cluster is to the points in the neighboring clusters. In our case, we compute silhouette scores for different numbers of clusters to guide us in choosing the optimal number of clusters. A plot of silhouette scores against the number of clusters can help us visually select the number of clusters where the silhouette score starts to decrease or level off. This is often referred to as the "elbow method". Therefore, silhouette scores offer a balanced approach that considers both the compactness of clusters (how similar the data points within each cluster are) and the separation between clusters (how distinct each cluster is from others). This balance helps us avoid scenarios where we have too many insignificant clusters or one large cluster encompassing all data points, neither of which would be particularly useful.

#### 3.3

The linkage parameter specifies the method used to calculate the distance between clusters when merging them. In this case, linkage='average' indicates that the average distance between all pairs of instances from different clusters is used. It is a popular choice as it can handle clusters of varying sizes and tends to produce more balanced and evenly sized clusters. It considers the overall similarity between clusters rather than just the distance between their closest or farthest instances.

The affinity parameter defines the distance metric used to measure the similarity or dissimilarity between instances. In this case, affinity='manhattan' specifies the Manhattan distance (also known as the L1 distance).

#### 3.4
Here, we use the PCA function from sklearn.decomposition library to reduce the dimensionality of the data to two components. The cluster labels obtained from hierarchical clustering are added as a new column. The clusters are visualized in a scatter plot using the two principal components. Each cluster is assigned a unique color from the rainbow colormap. The scatter plot displays the data points in the transformed PCA space, with each point labeled according to its assigned cluster.

### 4. Modeling
#### 4.1 
We perform a simple merge of the three tables, and merge that table with the table that contains the clusters. 

#### 4.2
To ensure that all features are compatible with the concept of feature similarity in the K-NN (K-Nearest Neighbors) model, we need to address two main considerations: scaling numerical features and encoding categorical features.

- If the numerical features have different scales or units, it can affect the distance calculations and bias the model. To address this, it is important to standardize or normalize the numerical features. StandardScaler class from scikit-learn is used to standardize numerical features.

- K-NN calculates the similarity between data points based on their feature values. However, categorical features cannot be directly used in their raw form since they don't have inherent numerical distances or magnitudes. To incorporate categorical features into the K-NN model, we need to convert them into a numerical representation. We can use one-hot encoding to convert the categorical features. 

#### 4.3
The approach outlined here uses grid search with cross-validation to systematically evaluate different values of the number of neighbors (n_neighbors) and select the optimal value based on the best performance. Cross-validation helps to estimate the model's generalization ability by splitting the data into multiple folds and evaluating performance on each fold. Grid search exhaustively searches the parameter grid to find the best combination of parameters that yields the highest cross-validated performance.

#### 4.4
The approach outlined here allows for the evaluation of the K-NN model's performance on unseen data by splitting the dataset into training and test sets. The model is trained on the training set, and its performance is assessed by comparing the predicted labels (y_pred) with the actual labels (y_test) using classification metrics. The performance of the K-NN model is evaluated using the classification_report function from scikit-learn. This function calculates various classification metrics, such as precision, recall, F1-score, and support, and generates a report that summarizes the model's performance on the test data. The report provides insights into the model's accuracy and its ability to correctly classify different classes.

#### 4.5
**SMOTE:** 
SMOTE is chosen as it is a popular and effective technique for handling imbalanced datasets. It creates synthetic samples by interpolating the feature space between minority class instances, thereby addressing the class imbalance problem. SMOTE is widely used because it not only duplicates minority class instances but also generates new synthetic instances that are plausible representations of the minority class. By oversampling the minority class, SMOTE helps in creating a more balanced dataset. This allows the predictive model to learn and generalize better, leading to improved performance, especially for the minority class. It prevents the model from being biased towards the majority class and provides a more accurate representation of the underlying data distribution.

**ADASYN:**
ADASYN is chosen as an alternative oversampling technique to SMOTE. While SMOTE generates synthetic samples by interpolating between existing minority class instances, ADASYN goes a step further by adaptively adjusting the sampling density based on the local density of instances. ADASYN takes into account the imbalance ratio and the distribution of the minority class to create synthetic samples.

#### 4.6: 
Under-sampling reduces the number of instances in the majority class to match the number of instances in the minority class. This combination of over-sampling the minority class and under-sampling the majority class helps to address the class imbalance problem effectively.

The Pipeline class from imblearn.pipeline is utilized to construct a pipeline that sequentially applies the over-sampling and under-sampling steps. In this case, the over-sampling step uses SMOTE or ADASYN to increase the representation of the minority class, while the under-sampling step randomly selects instances from the majority class to balance the data. We chose to use SMOTE since it performs better in our case. 






