# **Business Problem Statement:**
The Gmail Smart Compose & Reply team has been working diligently to improve user experience. However, user adoption and the success rate of the features vary. We need to understand and analyze where our Smart Compose and Reply features are most effective and where they may need adjustments. By understanding instances where users override or ignore the suggestions, we can inform future improvements. Additionally, by segmenting our analysis based on parameters like language, region, or user type, we can ensure the feature's effectiveness across diverse user bases.

## **Data Tables:**

**Table: UserActivity**

| Feature Name | Description                                          | Data Type | Comments                      |
|--------------|------------------------------------------------------|-----------|-------------------------------|
| user_id      | Unique identifier for each user                      | int       | Primary Key                   |
| region       | Region where the user is located                     | varchar   |                               |
| language     | Preferred language of the user                       | varchar   |                               |
| activity_date| Date when user interacted with the smart feature     | date      |                               |
| compose_used | Whether Smart Compose was used (1 for Yes, 0 for No) | enum      | Options: 0, 1                 |
| reply_used   | Whether Smart Reply was used (1 for Yes, 0 for No)   | enum      | Options: 0, 1                 |
| override     | If user overrode the suggestion (1 for Yes, 0 for No)| enum      | Options: 0, 1                 |

**Table: UserDemographics**

| Feature Name | Description                                          | Data Type | Comments                      |
|--------------|------------------------------------------------------|-----------|-------------------------------|
| user_id      | Unique identifier for each user                      | int       | Primary Key, Foreign Key (UserActivity)|
| user_type    | Type of user (e.g., Student, Professional, etc.)     | varchar   |                               |

## Questions:

**Question 1:**

**Topics and Operations:** Aggregation, Grouping, Counting (Based on the topic from sample question 1)

**Scenario:** To ensure the effectiveness of the Smart Compose and Reply feature, we want to determine which regions have the highest user adoption.

**Task:** Write a SQL query to find the total count of users from each region who used Smart Compose and Smart Reply at least once.

**Question 2:**

**Topics and Operations:** Joining Tables, Grouping, Counting, Filtering (Based on the topic from sample question 2)

**Scenario:** To understand where our features may need adjustment, we want to identify segments of users who override the suggestions most frequently. User type can be a significant factor in this.

**Task:** Write a SQL query to join the UserActivity and UserDemographics tables and find the total number of overrides for each user type. Order the result by the number of overrides in descending order.

**Question 3:**

**Topics and Operations:** Date Functions, Grouping, Aggregation (Based on the topic from sample question 3)

**Scenario:** To inform our improvements, we need to identify if there are any specific months where users tend to override our suggestions more frequently. This can help us identify if certain system updates or external factors led to an increase in overrides.

**Task:** Write a SQL query to extract the month from the activity_date and find out the total number of overrides for each month. Order the result by month in ascending order.
