# **Business Problem Statement:**
As the LinkedIn "Churn Prediction" team, we're trying to understand which users are most likely to leave our platform in the next month. Our ultimate goal is to tailor our engagement strategies to retain these at-risk users.

## **Data Table:**

**Info_data**

| Column Name   | Description                                             | Feature Type       |
|---------------|---------------------------------------------------------|--------------------|
| user_id       | Unique identifier for a user                            | Categorical        |
| last_login    | Last date the user logged into LinkedIn                 | Date               |
| profile_views | Number of times a user's profile was viewed in last month| Numerical          |
| posts_shared  | Number of posts user shared in the last month           | Numerical          |
| connections_made | New connections made in the last month               | Numerical          |
| avg_session_time | Average time spent on LinkedIn per session in minutes | Numerical          |
| job_applied   | Number of jobs a user applied to in the last month      | Numerical          |
| last_edited_profile | Last date the user edited their profile             | Date               |
| feedback_given | Whether the user gave feedback about the platform      | Binary (Yes/No)    |
| churn_next_month | Whether user will churn in the next month            | Binary (Yes/No)    |

## **Questions:**

1. **Scenario**: The business believes that users who have not edited their profile recently and have lesser profile views than average might be at risk of churning.

    - Using SQL, identify users who have not edited their profiles in the last three months and whose profile_views are below the monthly average. Further, compute the proportion of these users that have churned the following month.
    

2. **Scenario**: The marketing team is curious about the correlation between a user's engagement on the platform (measured by `avg_session_time`) and their likelihood of churning next month.

    - Derive the correlation between `avg_session_time` and `churn_next_month`. If possible, visually represent this relationship.
    

3. **Scenario**: The analytics team has hypothesized that users who've applied to fewer jobs than average but have a higher number of posts shared might be influencers or thought leaders in their domain. However, there's also a belief that some of these users might be at risk of churning.

    - Create a predictive model to determine if these users are likely to churn in the next month. Clearly state the target variable and its type. Assess the performance of your model.

    **Target Variable**: churn_next_month (Binary)

4. **Scenario**: LinkedIn wants to A/B test a new feature targeting users at risk of churning. They believe that showing more relevant job postings might increase engagement for users who have low `profile_views` but have shown interest in job postings by applying to some jobs.

    - Design an A/B test to validate the impact of this new feature on user retention. What metrics will you monitor? And how will you analyze the results?

