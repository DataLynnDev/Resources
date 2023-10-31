# **Business Problem Statement:**
The primary objective is to optimize ad performance on the new ad-supported plan on Netflix. This entails understanding user engagement with ads, determining optimal ad placements, and evaluating the effectiveness of different ad types in promoting user interaction and satisfaction. The data analyst is required to scrutinize user behaviors, ad metrics, and feedback to derive actionable insights that would enhance ad relevancy, placement, and overall user experience.

## **Data Tables:**

**Table 1: UserActivity**

| Feature Name | Feature Description        | Feature Data Type | Comments  |
|--------------|----------------------------|-------------------|-----------|
| user_id      | Unique identifier for user | INT               | PK        |
| show_id      | Unique identifier for show | INT               | FK        |
| ad_id        | Unique identifier for ad   | INT               | FK        |
| timestamp    | Time of the activity       | DATETIME          |           |
| activity_type| Type of activity           | ENUM              | View, Click |

**Table 2: AdsInfo**

| Feature Name    | Feature Description               | Feature Data Type | Comments  |
|-----------------|-----------------------------------|-------------------|-----------|
| ad_id           | Unique identifier for ad          | INT               | PK        |
| ad_type         | Type of ad (video, banner, etc.)  | ENUM              | Video, Banner |
| ad_duration     | Duration of ad in seconds        | INT               |           |
| ad_category     | Category of ad content           | VARCHAR(255)      |           |

## Questions:

**Question 1:**

*Topics and Operations:* Aggregation, Join

*Scenario:* The marketing team wants to know the overall engagement of users with different ad types to plan the future ad content strategy.

*Task:* Write an SQL query to find the total number of views and clicks for each ad type.

**Question 2:**

*Topics and Operations:* Conditional Aggregation, Join

*Scenario:* Understanding user engagement in terms of ad interactions per show is crucial for optimizing ad placements.

*Task:* Write an SQL query to find the total number of views and clicks for each ad type per show, along with the show_id.

**Question 3:**

*Topics and Operations:* Date Functions, Join, Conditional Statements

*Scenario:* The effectiveness of ads may vary during different times. Evaluating ad engagement over time can provide insights into user behavior and ad performance.

*Task:* Write an SQL query to find the total number of views and clicks for each ad type per week, and also find the week with the highest ad engagement (sum of views and clicks).
