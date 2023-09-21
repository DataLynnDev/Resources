# Business Problem Statement:
As Amazon's Advertising team, our platform aims to allow advertisers to effectively reach Amazon customers with their product ads. With the surge in the number of advertisers and the volume of ad campaigns, there's an increasing need to measure and optimize ad performance. The core challenge is: **How can we improve our ad placements, better segment our audiences, and subsequently assist advertisers in understanding the return on investment (ROI) of their campaigns?**

## Data Tables:

1. **Table Name:** `AdsPerformance`

| **Column Name** | **Description & Feature Type**                  |
|-----------------|-------------------------------------------------|
| ad_id           | Unique identifier for the ad. (Categorical)     |
| product_id      | Unique identifier for the product. (Categorical)|
| click_count     | Number of clicks on the ad. (Numerical)         |
| view_count      | Number of views for the ad. (Numerical)         |
| purchase_count  | Number of purchases after clicking the ad. (Numerical) |
| date            | Date of the ad performance data. (Date)         |

2. **Table Name:** `AdvertiserInfo`

| **Column Name** | **Description & Feature Type**   |
|-----------------|----------------------------------|
| advertiser_id   | Unique identifier for the advertiser. (Categorical)|
| product_id      | Product being advertised. (Categorical) |
| budget          | Total budget for the ad. (Numerical)    |
| campaign_start  | Start date of the campaign. (Date)  |
| campaign_end    | End date of the campaign. (Date)    |

## Questions

**1. Data Cleaning & Exploration**:

**Scenario**: You've just received the `AdsPerformance` dataset, and upon initial exploration, you've found some discrepancies. You want to ensure the data is clean and standardized before any analysis.

*Question*: Identify and handle missing values, detect any outliers especially in the 'click_count' and 'view_count' columns.


**2. SQL Queries**:

**Scenario**: As the team is diving deeper into ad performance, they want a combined view of the advertisements and the associated advertiser details.

*Question*: Using the `AdsPerformance` and `AdvertiserInfo` tables, create a Common Table Expression (CTE) that joins both tables on 'product_id'. From this CTE, identify the top 5 advertisers (by budget) whose ads have the highest 'click_count' to 'view_count' ratio using an analytic function. Also, using UNION, combine the results with the top 5 advertisers with the highest purchase rate (purchase_count/click_count).


**3. Probability and Statistical Analysis**:


**Scenario**: There's a hypothesis in the team that ads with a higher budget generally have a higher purchase rate (purchase_count/click_count). You've decided to test this hypothesis using the data at hand.

*Question*: State the null and alternative hypotheses for this scenario. Calculate the correlation coefficient between the 'budget' from `AdvertiserInfo` and the purchase rate from `AdsPerformance`. Implement this calculation in a coding language of your choice and interpret the results.


**4. Product & Business Sense**:

**Scenario**: Recently, a particular product's actual revenue has been observed to be 40% lower than its predicted revenue from the ads.

*Question*: Based on the data from the `AdsPerformance` and `AdvertiserInfo` tables, identify potential reasons for this gap in predicted and actual revenue. Additionally, how would you modify the ad strategy or placement to ensure a more accurate sales forecast for future campaigns?
