# **Business Problem Statement:**

The Facebook Engagement Analytics team has observed a recent decline in user engagement metrics for a newly released feature on the platform. We need a comprehensive analysis to understand the core reasons behind this decline and potential interventions.


## **Data Tables:**

**Table Name: UserEngagement**

| Column Name | Description | Feature Type |
|-------------|-------------|--------------|
| user_id     | Unique Identifier for each user | Numerical |
| login_date  | Date of user's login | Date |
| feature_usage | Count of times the user engaged with the new feature | Numerical |
| total_time_spent | Total time spent on the platform (in minutes) | Numerical |
| region      | Geographical region of the user | Categorical |

**Table Name: UserFeedback**

| Column Name | Description | Feature Type |
|-------------|-------------|--------------|
| user_id     | Unique Identifier for each user | Numerical |
| feedback_date | Date of feedback submission | Date |
| feedback_text | Textual feedback given by the user | Text |
| feature_rating | Rating given to the new feature (1-5 scale) | Numerical |

## Questions

1. **Question 1: Data Cleaning & Exploration**

**Scenario:** You've received the `UserEngagement` table which contains logs of user activities. Before diving deep, ensure the data integrity.

**Task:** Identify any users in the `UserEngagement` table with multiple login dates on the same day. Report the `user_id` and the date of the anomaly.

Certainly. Let's make the SQL query challenge more intricate.

2. **Question 2: SQL Queries**

**Scenario:** The Facebook Engagement Analytics team is curious about how user engagement metrics correlate with feedback, particularly among those users who frequently engaged with the new feature.

**Task:** Using the `UserEngagement` and `UserFeedback` tables, write an SQL query to:
1. Identify users whose cumulative `feature_usage` is above the 90th percentile.
2. From this filtered subset, retrieve those users who have also provided feedback.
3. Rank these users based on their `feature_rating` and return the top 10 users (with the highest ratings). Your output should include `user_id`, cumulative `feature_usage`, and `feature_rating`.


3. **Question 3: Probability and Statistical Analysis**


**Scenario:** The team is interested in identifying outlier users whose feature usage behavior differs significantly from the general user base.

**Task:** Calculate the z-scores for `feature_usage` in the `UserEngagement` table. Identify users with a z-score greater than 2 or less than -2 as outliers.

4. **Question 4: Product & Business Sense**

**Scenario:** Upon observing the `UserFeedback` table, it seems some users have given low ratings to the new feature.

**Task:** Propose a strategy to deep-dive into the feedback from users who gave a rating of 2 or less. Consider both quantitative and qualitative data points from the provided tables to aid in this investigation. How would you prioritize which feedback to act upon first?