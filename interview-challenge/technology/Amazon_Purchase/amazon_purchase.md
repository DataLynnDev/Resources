# Amazon Data Scientist Mock Interview
The goal of this data challenge is to assess the candidate's skills in data manipulation, feature preprocessing and engineering, classification modeling, and extracting business insights. The candidate will be asked to answer a series of questions using SQL and Python. 

## Business Problem: 
In the e-commerce industry, it is important to know whether a customer would purchase a product. With this information, we can make business decisions such as recommend products for customers or determine the stock of a product. In this interview challenge, we will predict if customers would buy a product based on their characteristics and behaviors.

## Questions Roadmap
    - Data Manipulation
        - Feature Preprocessing
        - Data Manipulation in SQL
        - Feature Engineering
    - Machine Learning Model
        - Modeling
        - Model Improvement
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

## Solution Overview
### Q1
#### 1.1 
This is a simple question. We only need to merge the three datasets together on 'Customer_Id' and 'Product_Id'. 

#### 1.2
Missing Data: The first step is to identify if there's any missing data. We can do this by checking if any column in the dataframe has any null or NaN values. Here's how to do it:

Once you've identified columns with missing data, you need to decide how to handle them. There are a few strategies you can use:

Remove: If the column has a significant number of missing values, it might be best to drop the entire column. You can also drop rows with missing values but this would lead to loss of data.

Impute: If only a few values are missing, you can fill in the missing values with the mean, median or mode of the column. 

#### Impute numerical missing values:
If the data is missing completely at random, we can fill in the missing values with the mean, median, or mode. In this case, we are filling the missing values with the mean.

We can also use ML algorithms like K-Nearest Neighbors to predict and impute missing values. 

#### Impute categorical missing values:
If the data is missing at random and the missing ratio is very low, we can fill in the missing values with the most frequent category. This approach is simple and fast

**Duplicates:** Duplicates can be easily handled by dropping duplicate rows. 

### Q2
#### 2.1
- **SELECT category, brand, AVG(rating) as avg_rating**: This part of the query is selecting the category, brand, and the average of the rating column. It is naming the average rating column as avg_rating.
- **FROM product**: This is specifying that the data is coming from the product table.
- **GROUP BY category, brand**: This is instructing the SQL engine to group the selected data by category and brand. In other words, for each unique combination of category and brand, it will calculate the average rating.
- **ROW_NUMBER() OVER(PARTITION BY category ORDER BY AVG(rating) DESC) as rank**: This is a window function that assigns a unique row number to each row within the partition of a result set. The partition is defined by the PARTITION BY category clause, and the ordering is defined by ORDER BY AVG(rating) DESC. So within each category, it assigns a unique row number in descending order of average rating. This rank is then stored in a new column called rank.
- The outer query SELECT category, brand, avg_rating WHERE rank <= 3 is selecting category, brand, and avg_rating where the rank is less than or equal to 3. This ensures that only the top three brands in terms of average rating are selected for each category.

#### 2.2
- **SELECT Customer_Id, COUNT(DISTINCT CASE WHEN Purchased = 1 THEN Product_Id END) as purchase_count, COUNT(DISTINCT CASE WHEN Clicked = 1 THEN Product_Id END) as click_count, COUNT(DISTINCT CASE WHEN Added_to_Cart = 1 THEN Product_Id END) as add_to_cart_count FROM customer_behavior GROUP BY Customer_Id**: This portion of the subquery calculates three different count metrics for each unique Customer_Id in the customer_behavior table:

    - **purchase_count** counts the distinct products that the customer has purchased.
    - **click_count** counts the distinct products that the customer has clicked on.
    - **add_to_cart_count** counts the distinct products that the customer has added to their cart.
- The **CASE WHEN clause within each COUNT(DISTINCT)** function allows us to count only those records that meet specific criteria. Here, it's used to count only products that were purchased, clicked, or added to cart. The results are then grouped by Customer_Id.

- **SELECT cb.Customer_Id FROM (...) cb WHERE cb.click_count >= 1 AND cb.add_to_cart_count >= 1 AND cb.purchase_count = 0**: The outer query then filters the results of the subquery to only include customers who clicked on at least one product (cb.click_count >= 1), added at least one product to their cart (cb.add_to_cart_count >= 1), but didn't purchase any products (cb.purchase_count = 0).

### Q3
#### 3.1 
1. **'Click_To_Add_Ratio'**: This feature is created to understand how often a user adds a product to the cart after clicking on it. If the ratio is high, it means that the user typically adds a product to the cart after clicking on it, indicating a higher likelihood of purchasing the product. It helps in identifying decisive customers who are likely to make a purchase.

2.
* **'Avg_Session_Duration_per_Year'**: This feature is created to get a sense of how long a user spends on the site per year, taking their tenure into account. This could provide insights into user engagement over the years. Higher values might indicate more interest or involvement in the site's offerings, potentially leading to more purchases.

* **'Purchases_per_Year'**: This feature scales the number of purchases based on the user's tenure. It's essentially a rate of purchases, which might be more informative than the raw number of purchases. It allows us to compare purchasing behavior across customers with different tenures.

* **'Tenure_to_Age_Ratio'**: This feature represents the proportion of a user's life that they have been a customer of the site. This could be useful for identifying long-term, loyal customers, as a higher ratio suggests a longer relationship with the platform relative to the customer's age. This could potentially indicate a higher likelihood of future engagement and purchases.

3. **'Avg_Price_Brand'**: Capturing pricing differences across brands is a valuable element for modeling, as it could potentially affect customer purchasing behavior. In this case, we could create a new feature that captures the average price of each brand's products. This would provide a single value representation of a brand's overall pricing policy.

#### 3.2
One-hot encoding is an easy and useful method in handling categorical variables. When working with categorical variables, we often encounter ordinal and nominal data. One-hot encoding does not impose any ordinality on nominal data.

## Machine Learning Model
### Q4
#### 4.1
F1-score is the weighted average of Precision and Recall, and it tries to find the balance between precision and recall.

#### 4.2
The Random Forest model is trained and evaluated using 5-fold cross-validation. The F1-score is calculated for each of the 5 iterations, and the mean and standard deviation are reported. The model is then fitted on the training set and predictions are made on the testing set. The F1-score on the test set is then calculated and printed.

It is important to compare the F1-scores from the cross-validation and the test set. If the cross-validation scores are high but the test score is significantly lower, this may suggest that the model is still overfitting the training data and might require further tuning or a simpler model. Conversely, if both scores are similar and satisfactory, it suggests the model generalizes well to unseen data.

### 4.3
We use seaborn barplot to show the importance of the feature in a descending order. 

### 4.4
The code demonstrates the use of ensemble learning, specifically a Stacking Classifier, to combine the strengths of multiple models and potentially improve the predictive power of the machine learning system.

Ensemble learning is a machine learning paradigm where multiple models (often called "base models" or "base learners") are trained to solve the same problem and combined to get better results. The main hypothesis is that when weak models are correctly combined we can obtain more accurate and/or robust models.

In the case of a stacking classifier, the individual models are trained based on a complete training set, then the meta-model is fitted based on the outputs or the predicted values of the individual models to make the final prediction. The base models are often different and the idea is to take advantage of their different areas of strength.

In the provided code, a Stacking Classifier is used with two base models - a Random Forest Classifier and a Logistic Regression model.

1. The Random Forest is a bagging-based ensemble model known for its robustness and ability to avoid overfitting.
2. Logistic Regression, on the other hand, is a simpler, linear model which can sometimes offer better interpretability and faster training times.
3. The "meta-model" used to combine the base learners' predictions is an XGBoost Classifier, a gradient boosting model known for its high performance in a wide range of prediction tasks.

StandardScaler is used to standardize features by removing the mean and scaling to unit variance. This is important because many machine learning algorithms do not perform well if the features are not on relatively similar scales.

The idea behind using stacking is to explore a space of different models for the same problem. The benefit is that the stacking model can smooth out some of the weaknesses of the individual base models while retaining their strengths, leading to a potentially more robust and accurate prediction.

### Q5
#### 5.1
* Added_to_cart: This being a highly important feature makes sense because a customer adding a product to their cart is a strong indicator of their interest in purchasing. Customers usually add items to their cart as a precursor to making a purchase, so it's not surprising that this feature plays a significant role in predicting purchase behavior.

* Click_to_add_ratio: This is a feature we engineered, which indicates the ratio of the number of products a customer clicked on to the number of products they added to their cart. If a customer is adding a high proportion of the items they click on to their cart, it might suggest that they are in a buying mode, which could potentially increase the likelihood of them purchasing a recommended product.

These insights can certainly help improve the current recommendation system. For instance, products that a customer has clicked on or added to their cart in the past can be given higher priority in the recommendation system. Furthermore, Amazon could look into improving the user experience to make adding items to the cart more seamless, or highlighting the 'add to cart' button more prominently, as these actions seem to be strongly correlated with purchasing.

Also, since the click-to-add ratio is important, the system could recommend products that similar users often add to their cart after clicking.

#### 5.2
* False positives, in this case, would mean that our model predicted a customer would purchase a product when in reality, they did not. This could lead to potentially misallocated resources, as Amazon may overstock based on the prediction that certain products will be sold.

* False negatives, on the other hand, mean that the model predicted a customer would not purchase a product when in reality, they did. This could lead to missed opportunities, as the product may not be sufficiently stocked and the customer might turn to a competitor.

Balancing these considerations involves understanding the costs associated with each type of error. If the cost of false positives (overstocking) is higher, then the model should be tuned to be more conservative with its predictions (increase the prediction threshold). If the cost of false negatives (missed opportunities) is higher, the model should be tuned to be more liberal with its predictions (decrease the prediction threshold). Tuning the model in this way could be accomplished using a ROC curve to find the optimal threshold that balances the tradeoff between false positives and false negatives.