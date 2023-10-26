# Business Problem Statement:

**How can we optimize user engagement by understanding the Gmail feature usage patterns?**

In an attempt to improve user experience and engagement, the User Engagement & Features Usage team at Google Gmail wants to identify which features are being frequently used, which are being ignored, and any potential correlations between user segments and feature usage. The goal is to provide actionable insights to the product team and drive strategies for user education and product improvements.

## Data Tables:

**Table: Users**

| Feature Name | Description                  | Data Type | Comments              |
|--------------|------------------------------|----------|-----------------------|
| user_id      | Unique identifier for a user | int      | Primary Key            |
| user_name    | Name of the user             | varchar  |                       |
| user_type    | Type of the user             | enum     | Options: Free, Premium |

**Table: FeatureUsage**

| Feature Name   | Description                                      | Data Type | Comments              |
|----------------|--------------------------------------------------|----------|-----------------------|
| usage_id       | Unique identifier for a feature usage entry     | int      | Primary Key            |
| user_id        | Identifier for a user                           | int      | Foreign Key (Users)    |
| feature_name   | Name of the Gmail feature being used            | varchar  |                       |
| usage_count    | Number of times the feature was used in a month | int      |                       |
| usage_date     | Date of the feature usage                       | date     |                       |


## SQL Questions:

### Question 1:

**Topics and Operations**: Joining tables, Aggregating data, Ordering results

**Scenario**: The product team wants to have a high-level view of which features are the most and least used across all users. This will help them identify popular features and those that may require more user education or improvements.

**Task**: Write an SQL query to retrieve the top 5 most used and least used Gmail features in the last month, along with their usage count. The result should show the feature name and total usage count.

### Question 2:

**Topics and Operations**: Joining tables, Conditional logic, Aggregating data, Filtering data

**Scenario**: Premium users are of high value to Gmail. The product team wants to know if there are any specific features that Premium users use more frequently compared to Free users. This can guide potential upselling strategies.

**Task**: Write an SQL query to find out which Gmail features are used more by Premium users than Free users in Sep. 2023. The result should show the feature name, total usage count by Premium users, and total usage count by Free users.

### Question 3:

**Topics and Operations**: Joining tables, Aggregating data, Having clause, Grouping data

**Scenario**: The User Engagement team suspects that some users might be using certain features in combination (e.g., using 'feature A' and 'feature B' in the same day). Identifying these patterns can provide insights into user workflows and potential areas for feature integration.

**Task**: Write an SQL query to identify any Gmail features that are frequently used together by the same user on the same day. The result should show pairs of feature names and the number of users who used both features on the same day in the Sep. 2023.