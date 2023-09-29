# **Business Problem Statement:**
As the user engagement and growth team at Instagram, we've noticed that some features and content types might be more engaging than others. Identifying these features and content types is crucial to strategize our growth. As an analyst, we need you to help us understand and predict the user engagement patterns based on the data we have.

## **Data Tables:**

1. **UserActivity**

| Feature Name             | Description                                      | Data Type | Comments                                          |
|--------------------------|--------------------------------------------------|----------|---------------------------------------------------|
| user_id                  | Unique identifier for the user                   | int      | Primary Key                                       |
| activity_date            | Date when the user was active                    | date     |                                                   |
| feature_used             | Feature of Instagram used by the user            | enum     | Options: 'Posts', 'Stories', 'Reels', 'IGTV'      |
| content_type             | Type of content the user engaged with            | enum     | Options: 'Video', 'Image', 'Text', 'Mixed Media'  |
| time_spent_in_minutes    | Time spent by the user on the given feature      | int      |                                                   |

2. **UserDetails**

| Feature Name             | Description                                      | Data Type | Comments                                          |
|--------------------------|--------------------------------------------------|----------|---------------------------------------------------|
| user_id                  | Unique identifier for the user                   | int      | Primary Key & Foreign Key (from UserActivity)     |
| registration_date        | Date when the user registered on Instagram      | date     |                                                   |
| country                  | Country of the user                              | varchar  |                                                   |
| age_group                | Age group the user falls under                   | enum     | Options: '13-17', '18-24', '25-34', '35-44', '45+'|

## Questions

1. **Question 1** Aggregation and Joining tables
  
  *Scenario:* Instagram wants to know the average time users from different age groups spend on each feature.

> Using the given tables, generate a report which shows the average time users from different age groups spend on each Instagram feature. The report should display the age_group, feature_used, and average time spent.

2. **Question 2** Filtering and Aggregation

  *Scenario:* There's a hypothesis that users engage more with videos regardless of the feature. We want to understand if this is true across all age groups.

> For each age group, find out the percentage of users who engage more with 'Video' content compared to other content types. Display the age group and the percentage of such users.

3. **Question 3** Window functions and Ranking

  *Scenario:* We want to identify the top 3 features most used by users in each country, based on the average time spent.

> List down the top 3 features for each country based on the average time spent on each feature by its users. The result should have country, feature_used, and its rank (1 for most used, 2 for second most, and so on).