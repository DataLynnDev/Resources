# **Business Problem Statement**:
Given the rise of fraudulent activity on LinkedIn, the primary goal is to detect anomalies that can indicate fake profiles or spammy behavior. The team is focused on ensuring that the platform remains trustworthy by identifying, flagging, and potentially removing or restricting these malicious accounts. Using data-driven methods, how can we best identify these anomalies?

## **Data Table:**

**Info_data**

| Column Name        | Description                                                  | Feature Type |
|--------------------|--------------------------------------------------------------|--------------|
| user_id            | Unique identifier for a LinkedIn user                        | Nominal     |
| profile_score      | A score given based on profile completeness and activity     | Continuous  |
| last_login         | Last time user logged into LinkedIn                          | DateTime    |
| message_sent_count | Number of messages sent by the user                          | Continuous  |
| message_reply_rate | Proportion of messages that received a reply from the user   | Continuous  |
| feature_on         | Whether certain suspicious features are enabled (1 or 0)     | Binary      |
| connection_count   | Number of connections of the user                            | Continuous  |
| endorsement_count  | Number of endorsements received by the user                  | Continuous  |
| flag_count         | Number of times the user was flagged by other users          | Continuous  |
| job_post_count     | Number of job postings made by the user                      | Continuous  |

## **Questions**:

1. **Data Manipulation & Cleaning**:
   - **Scenario**: Given the `user_id`, `message_sent_count`, and `message_reply_rate`, can you create a SQL query that finds out which users have a suspiciously high message count but a very low reply rate, which might be an indication of spammy behavior?

2. **Probability and Statistics**:
   - **Scenario**: For users with a `profile_score` below the mean, find the variance of the `endorsement_count`. How does this variance relate to the likelihood of a profile being fraudulent?

3. **Machine Learning & Modeling**:
   - **Scenario**: Build a model to predict the `flag_count` for each user based on all other features, considering `flag_count` as a continuous target variable. Describe the steps you would take and the challenges you foresee in using this model for anomaly detection.
   - **Target Variable**: `flag_count` (Continuous)

4. **Product Design & Analytics**:
   - **Scenario**: If you were to design a dashboard for executive-level employees at LinkedIn to monitor the health and trustworthiness of the platform, which metrics from the given table would you include? Elaborate on why each metric is important.
