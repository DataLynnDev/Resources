
## 1.Business Problem Statement


"Accenture is serving a multinational corporation that produces a wide range of electronic devices. The corporation is currently facing a significant challenge with its supply chain. High lead times are causing frequent stockouts of key components, leading to production disruptions and negatively impacting customer service levels. Meanwhile, some warehouses are experiencing an overstock of certain items, leading to increased holding costs.

Your task, as a supply chain analyst, is to analyze the provided data sets, identify bottlenecks, forecast future demand accurately, and design a balanced inventory policy that will minimize stockouts and overstock situations.

Your primary objectives are:

- To predict which products are most likely to experience stockouts in the next quarter, based on sales trends and current inventory levels.
- To identify products which are being overstocked and thus, leading to high holding costs.
- To propose an optimal inventory policy that aligns with the demand patterns, lead times, and minimizes total costs.

You are also expected to provide data-backed justifications for your recommendations and to outline a plan for implementing the suggested changes in the supply chain process."

## 2. Dataset Description:
### 2.1 Data Table 1: Product Inventory

Column Descriptions:

| Column name           | Description                                                          |
|-----------------------|----------------------------------------------------------------------|
| Product_ID            | Unique identifier for each product                                    |
| Product_Name          | Name of the product                                                   |
| Product_Category      | Category the product belongs to                                       |
| Product_Cost          | Cost to produce one unit of the product                                |
| Current_Stock_Level   | Current stock level of the product                                    |
| Safety_Stock_Level    | Minimum stock level that should be maintained to avoid stockouts       |
| Lead_Time             | Time taken to restock the product from the date of order               |


### 2.2 Data Table 2: Sales Records

Column Descriptions:

| Column name    | Description                                              |
|----------------|----------------------------------------------------------|
| Sales_ID       | Unique identifier for each sales transaction             |
| Product_ID     | Identifier of the product sold, corresponds to the        |
|                | Product_ID in the Product Inventory table                |
| Quantity_Sold  | Quantity of the product sold in this transaction         |
| Date_of_Sale   | Date when the product was sold                           |
| Sales_Region   | The geographical region where the product was sold        |
| Sales_Price    | Selling price of the product           


To solve this challenge, you will need to apply data analysis techniques to identify patterns and correlations, utilize time-series forecasting to anticipate future demands, and use optimization methods to propose a balanced inventory policy.

## Generate Synthetic Data

## 3. Questions for the Data Challenge##

### 3.1 Basic SQL Knowledge
Write an SQL query to find the 'Product_Category' that had the most sales ('Quantity_Sold') in each 'Sales_Region'. Also include the total sales price for that category in each region.

#### **Answer 3.1**

The given SQL query is designed to find the product category that had the most sales (highest quantity sold) in each sales region, along with the total sales price for that category in each region. Let's break down the steps involved in solving this problem.

1. The query uses two common table expressions (CTEs) to perform the required calculations.

2. The first CTE, "sales_totals," aggregates the sales records by sales region and product category. It calculates the total quantity sold and the total sales price for each combination.

3. The second CTE, "ranked_sales," builds on the results of the "sales_totals" CTE. It uses the RANK() function to assign a rank to each product category within each sales region based on the total quantity sold. The highest-selling category within each region will have a rank of 1.

4. The final SELECT statement retrieves the desired information from the "ranked_sales" CTE. It selects the sales region, product category, total quantity sold, and total sales price. The WHERE clause filters the results to only include rows where the rank is 1, indicating the category with the highest sales in each region.

5. The query is executed using the pd.read_sql_query() function from the pandas library, which reads the SQL query result into a pandas DataFrame for further analysis.

Overall, the query joins the "sales_records_df" and "product_inventory_df" tables on the common "Product_ID" column, groups the data by sales region and product category, calculates the total quantity sold and sales price for each category in each region, ranks the categories within each region based on quantity sold, and finally selects the category with the highest sales in each region. The result is a DataFrame called "Most_Sale_df" containing the desired information.

## 3.2 Cost-Based Risk Metric - Validation (Python/SQL)
Assume that a stockout event's cost is proportional to the Product_Cost but inversely proportional to the Lead_Time (more lead time means a lesser impact as we have more time to react). At the same time, the cost of holding excess inventory is a function of Product_Cost and Current_Stock_Level. Given these conditions, define a cost-based risk metric that balances both stockouts and overstock situations. How would you validate this metric using historical data?

#### **Answer 3.2**

## 3.3 Time to Stockout Forecasting - Time Series Analysis (Python)
Given the historical sales data and current stock levels, design a method to forecast the time to stockout for each product using a time series analysis approach. How would you account for both macro trends and seasonality in sales in your model? Furthermore, given the uncertainty in future sales, how would you calculate a confidence interval for your time to stockout forecast?

#### **Answer 3.3**


 Choose a specific product for which you want to forecast the time to stockout. In the given code, the product ID is obtained from the 'sales_records_df' DataFrame.

Retrieve the historical sales data for the selected product from the 'sales_records_df' DataFrame. Filter the DataFrame to only include records for the chosen product.

Ensure that the sales data is sorted chronologically by the date of sale.

Convert the 'Date_of_Sale' column to a datetime format to enable time series analysis.

Set the 'Date_of_Sale' column as the index of the DataFrame to perform time-based operations.

Resample the sales data to the desired frequency (e.g., daily) to obtain the total sales quantity for each time period.

Decompose the time series into its constituent components, including trend, seasonality, and residuals. This step helps visualize the patterns and identify any underlying trends and seasonality in the sales data.

Fit a SARIMA (Seasonal Autoregressive Integrated Moving Average) model to the resampled sales data. SARIMA models are suitable for analyzing time series data that exhibit both trend and seasonality. In the given code, an SARIMA model with an order of (1, 1, 1) and a seasonal order of (1, 1, 1, 12) is used.

Use the fitted SARIMA model to predict sales for the next desired time period. In the given code, sales forecasts are generated for the next 30 days.

Retrieve the current stock level for the selected product from the 'product_inventory_df' DataFrame.

Estimate the time to stockout by dividing the current stock level by the forecasted sales quantity for the first time period. This assumes that sales will continue at the forecasted rate.

Print the estimated time to stockout for the chosen product.

By applying these steps, you can leverage time series analysis techniques, such as SARIMA modeling, to forecast the time to stockout for a given product. It incorporates historical sales data, captures trends and seasonality, and provides an estimate of the remaining time until the product stock runs out.

## 3.4 Category-Wise Price Volatility - Feature Engineering (Python/SQL)
Besides capturing the trend and volatility of the Sales_Price, suppose you notice that certain Product_Categories are more prone to price changes than others. How would you create a feature that encapsulates this category-wise price volatility? What potential challenges do you foresee, and how could you validate this new feature's usefulness for your model?

#### **Answer 3.4**

To create a feature that encapsulates category-wise price volatility, you can follow these steps:

1. Group the product_inventory_df DataFrame by the Product_Category.

2. Calculate a measure of price volatility for each category. One common measure is the standard deviation of the Product_Cost within each category. You can use the std() function to calculate the standard deviation.

3. Merge the calculated volatility measure back into the product_inventory_df DataFrame using the Product_Category as the key.

This will add a new column named Price_Volatility to the product_inventory_df DataFrame, representing the category-wise price volatility.

1. Potential challenges and considerations for validating the usefulness of this new feature for your model include:

2. Feature interpretation: Ensure that the category-wise price volatility feature aligns with your domain knowledge and makes intuitive sense. It should capture meaningful differences in price volatility between product categories.

3. Feature correlation: Check for correlations between the category-wise price volatility feature and other features in your dataset. High correlation with existing features may indicate redundancy or multicollinearity.

4. Feature importance: Assess the importance of the category-wise price volatility feature in predicting the target variable. You can use feature importance techniques such as permutation importance or feature importance from a trained model to evaluate its contribution.

5. Model performance: Evaluate the impact of including the category-wise price volatility feature on the performance of your model. Compare model performance metrics (e.g., accuracy, precision, recall, or mean squared error) with and without the feature to determine if it improves the model's predictive power.

6. Cross-validation: Perform cross-validation to ensure that the observed performance improvement is consistent across different subsets of the data and not a result of overfitting to a specific training set.

7. Business validation: Finally, assess the usefulness of the category-wise price volatility feature from a business perspective. Consult with domain experts or stakeholders to validate whether the feature aligns with their understanding of category-wise price volatility and if it provides valuable insights for decision-making.

By considering these challenges and validating the feature using a combination of statistical analysis, model evaluation, and business validation, you can assess its usefulness and determine whether to include it in your model.

#### **Answer 3.5**

Traditional regression models, such as linear regression, may fall short in this context for several reasons:

- Assumption of Linearity: Traditional regression models assume a linear relationship between the independent and dependent variables. However, this is often not the case in real-world datasets, especially in cases where there are complex, non-linear relationships between variables.

- Interaction Effects: Regression models typically do not handle interaction effects well unless explicitly specified in the model. In other words, if the effect of one feature on the target variable changes depending on the value of another feature, this relationship may not be captured accurately by a traditional regression model.

- High Dimensionality: If there are a large number of features, traditional regression models can become complex and difficult to interpret. Additionally, they can suffer from issues such as multicollinearity (where features are highly correlated with each other) which can adversely impact the model's performance.

For example, in contrast, a machine learning approach such as a Random Forest could be a better fit for this problem for the following reasons:

- Non-Linearity and Interaction Effects: Random Forest is a type of ensemble learning model that creates a 'forest' of decision trees and aggregates their outputs. It can capture complex, non-linear relationships between features and also handle interaction effects naturally.

- Handling Categorical Variables: Random Forest can handle both numerical and categorical variables without the need for one-hot encoding, which can increase dimensionality.

- Interpretability: While Random Forest is often considered a "black box" model, techniques such as feature importance can provide insights into which features are most influential in the model's predictions.

- Robustness: Random Forests are relatively robust to outliers and do not make strong assumptions about the distribution of the target variable, unlike linear regression models.

In summary, while both traditional regression models and machine learning models like Random Forest have their strengths and weaknesses, a Random Forest may be a better choice in this context due to its ability to handle non-linearities, interaction effects, and mixed data types (numerical and categorical variables).

## 3.6 Hierarchical Model - Design and Optimization (Python)
Given that the data exhibits both temporal (time-series) and cross-sectional (across regions) variations, how would you design a hierarchical model to capture these dynamics? Discuss a strategy for optimizing such a model. How would you ensure that your model isn't overfitting to certain temporal or regional characteristics?

#### **Answer 3.6**

A hierarchical model, in this context, would aim to model both the time-series variation (temporal variation) and variation across regions (cross-sectional variation) in a hierarchical manner.

Here's a high-level design of such a model:

- Base Level: At the base of the model, fit separate models for each region's time series data. For example, use an ARIMA model, a state-space model, or even an LSTM neural network, depending on the complexity of the time series.

- Middle Level: Create models to estimate parameters for each region's time series model based on regional characteristics. These could be linear models, decision trees, or any other model that works well with your data.

- Top Level: Use a global model that shares information across regions. The model at this level could be used to estimate parameters in the middle-level models.

This hierarchical structure allows the model to capture both temporal dynamics and cross-sectional variations in the data.

To optimize such a model:

1. Model Selection: Choose an appropriate model for each level. This will involve trial and error, as well as domain knowledge about the data and the problem at hand.

2. Hyperparameter Tuning: Tune the hyperparameters of each model using methods such as grid search or random search. For each model, you'll want to use cross-validation to get an unbiased estimate of the model's performance.

3. Regularization: Regularize the models to prevent overfitting. This is especially important for the models at the top of the hierarchy, which have the potential to overfit to the global data.

To ensure that the model isn't overfitting to certain temporal or regional characteristics, it's important to validate the model using out-of-sample data. This could be done using techniques like cross-validation. For example, you could use time series cross-validation for the base models, and k-fold cross-validation for the middle and top level models.

Also, include regularization terms in your model to prevent overfitting. Regularization methods such as L1 or L2 regularization add a penalty term to the loss function, which helps to control the complexity of the model.

Interpretability can be a challenge with hierarchical models, particularly if the models at each level are complex. Therefore, choose simpler models when interpretability is a crucial factor. For instance, linear models or decision trees might be more interpretable than a complex neural network.

Furthermore, you may want to perform a feature importance analysis to understand which regional characteristics are most predictive of the target variable.

## 3.7 Model Performance - Interpretability and Business Recommendations
Assume you have built your model and found that its performance varies across product categories and sales regions. How would you leverage methods like SHAP (SHapley Additive exPlanations) or other model interpretability techniques to understand why this is the case? How could these insights be used to provide specific recommendations for different regions or product categories? Additionally, how might these insights inform your strategy for data collection or feature engineering in the future?

* Hint:SHAP (SHapley Additive exPlanations) is a game theory approach to explain the output of any machine learning model. It connects optimal credit allocation with local explanations using the classic Shapley values from cooperative game theory and their related extensions.

#### **Answer 3.7**

If your model performance varies across product categories and sales regions, SHAP values can help you understand the contribution of each feature to the prediction for each sample. This can provide an understanding of why specific regions or product categories have different performance metrics.

Here is how you could leverage SHAP or other model interpretability techniques in this scenario:

- Identify Important Features: SHAP values can identify which features are most influential in driving predictions. For example, if a certain region consistently has high SHAP values for a certain feature, that might suggest the feature is particularly important in that region.

- Understand Interactions: SHAP can also help in understanding feature interactions. For example, a certain product category might have strong performance only when combined with a specific region.

- Analyze Outliers: SHAP can help you understand why certain observations are outliers. By inspecting the SHAP values for these outliers, you might be able to identify unexpected feature values or relationships that are leading to these unusual predictions.

Once you have these insights, you can make specific recommendations for different regions or product categories. For example, if you find that the model's performance is lower in a certain region due to lack of data, you might recommend increasing data collection in that region.

If a certain product category is showing strong performance due to specific features, you might recommend focusing on those features when developing new products in that category.

Going forward, these insights can inform your strategy for data collection and feature engineering. If certain features are particularly influential in driving predictions, you might focus on collecting more detailed or accurate data for those features. If you find that feature interactions are important, you might engineer new features that capture these interactions.

In summary, interpretability techniques like SHAP can provide valuable insights into your model's behavior, guiding you in making data-driven decisions and improving your model's performance over time.
