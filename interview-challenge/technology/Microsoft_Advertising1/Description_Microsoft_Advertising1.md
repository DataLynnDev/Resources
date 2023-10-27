# **Business Problem Statement:**
Microsoft's Advertising team is looking to optimize its ad placement strategies based on historical ad performance metrics. The team wants to understand which ads perform best in terms of user engagement and conversion rates, and how these metrics vary by different user demographics and ad characteristics. This will help the team make informed decisions on ad placements, pricing, and targeting.

## **Data Tables:**

**Table: AdPerformance**

| Feature Name | Description                                      | Data Type | Comments                        |
|--------------|--------------------------------------------------|-----------|---------------------------------|
| ad_id        | Unique identifier for each ad                    | int       | Primary Key                     |
| ad_type      | Type of the ad (e.g., banner, video, pop-up)     | varchar   |                                 |
| impressions  | Number of times the ad was displayed             | int       |                                 |
| clicks       | Number of times the ad was clicked               | int       |                                 |
| conversions  | Number of times the ad led to a sale/conversion  | int       |                                 |
| ad_cost      | Cost of the ad per impression                    | float     |                                 |

**Table: UserDemographics**

| Feature Name | Description                                      | Data Type | Comments                        |
|--------------|--------------------------------------------------|-----------|---------------------------------|
| user_id      | Unique identifier for each user                  | int       | Primary Key                     |
| age_group    | Age group of the user (e.g., 18-24, 25-34, etc.) | varchar   | Enum: 18-24, 25-34, 35-44, etc.|
| gender       | Gender of the user                               | varchar   | Enum: Male, Female, Other       |
| ad_id        | Ad that the user interacted with                 | int       | Foreign Key referencing AdPerformance |

## Questions

**Question 1:**

*Topics and Operations:* Grouping, Counting, Sorting

*Scenario:* The Advertising team wants to understand the overall performance of different types of ads. This will help in allocating budget and resources to the most effective ad types.

*Task:* Write an SQL query to find the total impressions, clicks, and conversions for each ad type. Order the result by the number of conversions in descending order.

**Question 2:**

*Topics and Operations:* Joining Tables, Grouping, Counting, Filtering

*Scenario:* The team has observed that user demographics play a crucial role in ad engagement. They want to target ads more effectively based on age and gender.

*Task:* Write an SQL query to find the ad type that has the highest conversion rate for each age group and gender combination. Only consider ad types that have more than 1000 impressions for each demographic group.

**Question 3:**

*Topics and Operations:* Calculations, Grouping, Sorting

*Scenario:* To maximize the return on investment (ROI), the team wants to understand which ads provide the best value for money. The ROI is calculated as `(conversions * average sale value - ad_cost * impressions) / (ad_cost * impressions)`.

*Task:* Write an SQL query to calculate the ROI for each ad type. Assume an average sale value of $100. Order the result by ROI in descending order, and filter out ad types with an ROI less than 0.1.
