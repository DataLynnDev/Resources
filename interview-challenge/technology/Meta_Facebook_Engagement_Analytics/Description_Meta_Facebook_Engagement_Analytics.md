# Business Problem Statement:
We want to understand the dynamics behind the user engagement on Facebook to enhance the platform experience, drive more interactions, and reduce user churn. This involves analyzing user behavior concerning various features on the platform, understanding their preferences, and tailoring the Facebook experience according to their interaction patterns.

## Data Tables:

**1. UserActivityLog**

| Column Name | Description                          | Feature Type |
|-------------|--------------------------------------|--------------|
| UserID      | Unique identifier for each user      | Categorical  |
| DateTime    | Timestamp of the activity (2023-8-1 to 2023-8-18)           | Datetime     |
| ActionType  | Type of action (post, like, share)   | Categorical  |
| PostID      | Unique identifier for each post      | Categorical  |

**2. UserDemographics**

| Column Name    | Description                       | Feature Type |
|----------------|-----------------------------------|--------------|
| UserID         | Unique identifier for each user   | Categorical  |
| Country        | Country of the user               | Categorical  |
| AccountAge     | Age of the user's account in days | Numerical    |
| LastActiveDate | Last date the user was active (2023-8-1 to 2023-8-18)    | Datetime     |

## Questions:

1. **Scenario**: Over the past week, you've noticed a decline in the number of daily active users. Using the `UserDemographics`, investigate which countries have witnessed a significant drop in user activity.

    **Question**: Can you identify the top 3 countries with the most substantial decline in daily active users over the last seven days compared to the previous week? Show your results with the percentage drop

2. **Scenario**: Facebook is interested in understanding the pattern behind user's posts to potentially introduce new features to enhance engagement.

    **Question**: Using the `UserActivityLog` table, identify the peak hour (in 24-hour format) during which most users make a post. Also, can you detect any difference in this peak hour between older accounts (more than 1 year old) and newer accounts (less than 1 year old) by referencing the `UserDemographics` table?


3. **Scenario**: There's a hypothesis that users who have been less active in the past might show increased activity if they find more of their posts getting liked or shared by their friends.

    **Question**: From the `UserActivityLog`, calculate the post to like ratio for each user in the last week. Then, correlate this with the increase or decrease in their activity (number of posts) in the current week for users who had less than 5 posts in the previous week. Does a higher post to like ratio correlate with an increase in posting activity?
    

4. **Scenario**: There's been a suggestion to introduce a new feature based on user's account age to re-engage older accounts.

    **Question**: Using the `UserDemographics` table, find the percentage of users who have been inactive for the last two weeks based on their account age. Segment this into three categories: Accounts less than 1 year old, between 1 to 3 years old, and more than 3 years old. Based on this data, which user segment should Facebook target for a potential re-engagement campaign?