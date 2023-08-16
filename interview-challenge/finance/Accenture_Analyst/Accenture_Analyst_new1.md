# Business Problem Statement

"Accenture is serving a multinational corporation that produces a wide range of electronic devices. The corporation is currently facing a significant challenge with its supply chain. High lead times are causing frequent stockouts of key components, leading to production disruptions and negatively impacting customer service levels. Meanwhile, some warehouses are experiencing an overstock of certain items, leading to increased holding costs.

Your task, as a supply chain analyst, is to analyze the provided data sets, identify bottlenecks, forecast future demand accurately, and design a balanced inventory policy that will minimize stockouts and overstock situations.

Your primary objectives are:

- To predict which products are most likely to experience stockouts in the next quarter, based on sales trends and current inventory levels.
- To identify products which are being overstocked and thus, leading to high holding costs.
- To propose an optimal inventory policy that aligns with the demand patterns, lead times, and minimizes total costs.

You are also expected to provide data-backed justifications for your recommendations and to outline a plan for implementing the suggested changes in the supply chain process."

## Data Tables

**Product Inventory**


| Column name           | Description                                                          |
|-----------------------|----------------------------------------------------------------------|
| Product_ID            | Unique identifier for each product                                    |
| Product_Name          | Name of the product                                                   |
| Product_Category      | Category the product belongs to                                       |
| Product_Cost          | Cost to produce one unit of the product                                |
| Current_Stock_Level   | Current stock level of the product                                    |
| Safety_Stock_Level    | Minimum stock level that should be maintained to avoid stockouts       |
| Lead_Time             | Time taken to restock the product from the date of order               |


**Sales Records**


| Column name    | Description                                              |
|----------------|----------------------------------------------------------|
| Sales_ID       | Unique identifier for each sales transaction             |
| Product_ID     | Identifier of the product sold, corresponds to the        |
|                | Product_ID in the Product Inventory table                |
| Quantity_Sold  | Quantity of the product sold in this transaction         |
| Date_of_Sale   | Date when the product was sold                           |
| Sales_Region   | The geographical region where the product was sold        |
| Sales_Price    | Selling price of the product           

## Questions

**Question 1: Basic SQL Knowledge**

Write an SQL query to find the 'Product_Category' that had the most sales ('Quantity_Sold') in each 'Sales_Region'. Also include the total sales price for that category in each region.


**Question 2: Cost-Based Risk Metric - Validation**

Assume that a stockout event's cost is proportional to the Product_Cost but inversely proportional to the Lead_Time (more lead time means a lesser impact as we have more time to react). At the same time, the cost of holding excess inventory is a function of Product_Cost and Current_Stock_Level. Given these conditions, define a cost-based risk metric that balances both stockouts and overstock situations. How would you validate this metric using historical data?


**Question 3: Time to Stockout Forecasting - Time Series Analysis**

Given the historical sales data and current stock levels, design a method to forecast the time to stockout for each product using a time series analysis approach. How would you account for both macro trends and seasonality in sales in your model? Furthermore, given the uncertainty in future sales, how would you calculate a confidence interval for your time to stockout forecast?


**Question 4: Category-Wise Price Volatility - Feature Engineering**

Besides capturing the trend and volatility of the Sales_Price, suppose you notice that certain Product_Categories are more prone to price changes than others. How would you create a feature that encapsulates this category-wise price volatility? What potential challenges do you foresee, and how could you validate this new feature's usefulness for your model?

**Question 5: Hierarchical Model - Design and Optimization**
Given that the data exhibits both temporal (time-series) and cross-sectional (across regions) variations, how would you design a hierarchical model to capture these dynamics? Discuss a strategy for optimizing such a model. How would you ensure that your model isn't overfitting to certain temporal or regional characteristics?

