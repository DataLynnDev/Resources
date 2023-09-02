# **Business Problem Statement:**
Zillow's Demand Prediction team aims to optimize property listing times and pricing strategies by forecasting market demand fluctuations. This is achieved by leveraging a blend of historical sales data, economic indicators, and the inherent seasonality of the real estate market.

## **Data Table Specification:**

**info_data**

| Column Name          | Description                                         | Feature Type          |
|----------------------|-----------------------------------------------------|-----------------------|
| `Property_ID`        | Unique identifier for properties                     | Categorical           |
| `Listing_Date`       | Date when the property was listed                    | Date                  |
| `Economic_Indicator` | A metric indicating economic health (e.g., GDP)      | Numerical             |
| `Historical_Sale`    | Historical sale data for the property                | Numerical             |
| `Season`             | Season when the property was listed (e.g., Spring)   | Categorical           |
| `Listing_Price`      | Price at which property is listed                    | Numerical             |
| `Sale_Date`          | Date when the property was sold (if sold)            | Date                  |
| `Sale_Price`         | Price at which property was sold (if sold)           | Numerical             |
| `Region_Type`        | Rural or Urban                                       | Categorical           |
| `Demand_Score`       | A calculated score indicating market demand          | Numerical             |

## **Questions:**

1. **Scenario**: A stakeholder is interested in understanding the effect of economic indicators on the listing price of properties. From the data provided, can you ascertain a relationship between the `Economic_Indicator` and the `Listing_Price`? Also, are there certain seasons where this relationship is stronger?

2. **Scenario**: Recently, there's been a discrepancy in the historical sale data. Using statistical methods, can you identify potential outliers or anomalies in the `Historical_Sale` data, especially when compared against the `Economic_Indicator`?

3. **Scenario**: Zillow wants to create a predictive model to forecast the `Demand_Score` for a property. Using the provided features, design a predictive model. Ensure you highlight the steps taken to prevent overfitting and validate the model's accuracy. Please identify the target variable and its type.
    - **Target Variable**: `Demand_Score`, **Type**: Numerical


4. **Scenario**: Stakeholders have observed that properties in different regions (Rural or Urban) have varying demand scores. Given this observation, can you perform a statistical test to determine if the mean `Demand_Score` is significantly different between the two `Region_Type`? Also, provide insights on how this could influence Zillow's strategy.