# Business Problem Statement:
TikTok's User Retention and Growth team is dedicated to understanding user behavior and predicting when users are likely to leave the platform. The aim is to use data-driven approaches to proactively intervene, potentially retaining users and fostering consistent growth.

**The Challenge:**
You've been given a dataset that contains various features regarding users' interactions with TikTok. Your challenge is to dive deep into this dataset, analyze the patterns, and provide insights that will aid in the prediction of user churn and strategies for user retention.


## Data Tables:

#### User Activity Table:
| Column Name        | Description                                         | Feature Type      |
|--------------------|-----------------------------------------------------|-------------------|
| user_id            | Unique identifier for each user                     | Categorical       |
| last_login         | Date of the last login                              | Date              |
| video_uploads      | Number of videos uploaded by the user               | Numeric           |
| avg_watch_time     | Average time a user spends watching videos daily    | Numeric           |
| likes_received     | Number of likes received on their videos            | Numeric           |
| likes_given        | Number of likes given to other users' videos        | Numeric           |
| comments_received  | Number of comments received on their videos         | Numeric           |
| followings_count   | Number of users this user is following              | Numeric           |
| followers_count    | Number of users following this user                 | Numeric           |
| previous_churns    | Number of times user has left and returned to app   | Numeric           |

#### User Demographics Table:
| Column Name        | Description                                         | Feature Type      |
|--------------------|-----------------------------------------------------|-------------------|
| user_id            | Unique identifier for each user                     | Categorical       |
| age                | Age of the user                                     | Numeric           |
| country            | Country where the user is based                     | Categorical       |
| account_duration   | Duration since account creation (in days)           | Numeric           |

#### Churn Prediction Table:
| Column Name        | Description                                         | Feature Type      |
|--------------------|-----------------------------------------------------|-------------------|
| user_id            | Unique identifier for each user                     | Categorical       |
| predicted_churn    | Prediction of whether user will churn (0 or 1)      | Binary            |
| churn probability | Probability of user churn         | float          |


### Revised Questions:

1. **Data Manipulation & Cleaning:**   
    *Scenario*: You've noticed some inconsistencies in the `last_login` column of the User Activity Table, hinting at inactive users.
   - Identify users who haven't logged in for the last 30 days and rank them based on their `followers_count`. Utilizing the Demographics table, what patterns do you observe amongst the top-ranked users in terms of `country` and `account_duration`?
    

2. **Probability and Statistics:**
    *Scenario*: We're diving deeper into patterns of user engagement related to churn.
   - Given the User Activity and Churn Prediction tables, assess the probability that a user with above-average `avg_watch_time` but below-average `likes_received` will churn. Can you draw any statistical correlations between `video_uploads` and the churn probability?


3. **Machine Learning & Modeling:**
    *Scenario*: Past behavior often sheds light on future actions.
   - Construct a model to predict churn using the User Activity and Demographics tables. How does the `previous_churns` feature influence predictions? How would you avoid overfitting and which features would be most influential in the model?


4. **Product Design & Analytics:**
    *Scenario*: Strategies should be backed by data-driven insights.
   - Examining the Churn Prediction table and drawing insights from the User Demographics table, which segment of users, identified by a particular country or age range, seems most likely to churn? Propose a modification or feature targeting this segment to boost retention. How would A/B testing be applied to gauge the new feature's impact?
