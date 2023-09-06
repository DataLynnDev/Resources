# **Business Problem Statement:**  
As the market evolves and customer demands change rapidly, IBM's supply chain optimization team needs to enhance its analytical capabilities. The main challenges include predicting future demand accurately, optimizing inventory levels in various locations, and designing an efficient distribution network. The aim is to achieve swift responses to market changes, minimize operational costs, and maximize customer satisfaction.

## **Data Table:**

**info_data**

| Column Name       | Description                                    | Feature Type       |
|-------------------|------------------------------------------------|--------------------|
| `Product_ID`      | Unique Identifier for each product             | Categorical        |
| `Location`        | Storage location of the product                | Categorical        |
| `Month_Year`      | Month and Year of data recorded                | DateTime           |
| `Units_Sold`      | Number of units sold                           | Numeric            |
| `Units_Received`  | Number of units received in inventory          | Numeric            |
| `Current_Stock`   | Current stock available at location            | Numeric            |
| `Lead_Time`       | Days taken to deliver product from supplier    | Numeric            |
| `Demand_Forecast` | Predicted demand for the upcoming month        | Numeric            |
| `Customer_Rating` | Rating given by the customer (1 to 5 scale)    | Numeric (Ordinal)  |
| `Product_Category`| Category to which a product belongs             | Categorical        |

**Questions:**

1. **Scenario**: Given the importance of demand forecasting for efficient supply chain management, you've been provided with historical sales and stock data. Using the data, determine which product categories are most susceptible to demand fluctuations and require closer monitoring in the upcoming months.


2. **Scenario**: Customers have been providing feedback on products, which is stored in the `Customer_Rating` column. Some patterns suggest that low ratings often result in reduced sales in subsequent months. Investigate this correlation and, if true, provide recommendations for product categories requiring immediate quality enhancement.

3. **Scenario**: Considering the importance of keeping stock levels optimal, analyze the data to determine which product categories and locations have consistently high stock levels, indicating overstocking or low demand. Build a
Machine Learning model for the prediction of the stock.
    - **Target Variable**: `Current_Stock`
    - **Type**: Regression
