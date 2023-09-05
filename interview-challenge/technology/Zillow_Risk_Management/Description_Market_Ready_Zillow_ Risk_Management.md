# **Business Problem Statement:**
With the introduction of Zillow Offers, where Zillow buys homes directly, renovates, and then resells them, accurate property evaluations are crucial to ensure profitability and minimize risk. The Risk Management team's main challenge is to use data-driven approaches to optimize our home buying decisions, anticipate renovation costs, and predict potential sale prices accurately.

## **Data Table:**

**info_data**

| Column Name       | Description                                        | Feature Type       |
|-------------------|----------------------------------------------------|--------------------|
| propertyID        | Unique identifier for the property                 | Categorical        |
| locationState     | The state in which the property is located         | Categorical        |
| lastSoldPrice     | The price at which the property was last sold      | Numeric            |
| numberOfRooms     | Number of rooms in the property                    | Numeric            |
| propertyAge       | Age of the property in years                       | Numeric            |
| renovationCost    | Estimated cost to renovate the property            | Numeric            |
| predictedSalePrice| Projected price at which the property can be sold  | Numeric (Target)   |
| savedDate         | Date when the property was saved in Zillow Offers  | Date               |
| squareFeet        | Total area of the property                         | Numeric            |
| propertyType      | Type of property (e.g., Condo, Single Family)      | Categorical        |

## **Questions:**

1. As part of the risk management strategy, it is crucial to understand the correlation between the `renovationCost` and the potential profit that can be gained (difference between `predictedSalePrice` and `lastSoldPrice`). For properties saved in the last 6 months, how does the renovation cost relate to the potential profit?

2. It's noticed that certain states have a high variance in the `predictedSalePrice`. For each state, calculate the percentage variance in `predictedSalePrice`. Additionally, for states with more than a 20% variance, list the most common `propertyType`.

3. A potential risk factor for Zillow is overestimating the `predictedSalePrice` for older properties. Build a regression model to predict the `predictedSalePrice` based on `propertyAge`, `squareFeet`, and `numberOfRooms`. Once the model is trained, evaluate its performance on properties older than 50 years and compare the predicted vs actual sale prices.


4. You have a hypothesis that the renovation costs might significantly differ for different property types, potentially affecting the profitability for Zillow Offers. For the given dataset, apply a statistical test to check if the variance in `renovationCost` is significantly different among various `propertyTypes`. If so, which `propertyType` generally requires the highest renovation costs?