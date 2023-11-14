# **Business Problem Statement:**
Spotify's User Engagement and Retention Team is keen on understanding the behavior of its users. The primary goal is to identify patterns that lead to increased user engagement and reduce churn. By analyzing user activity, session lengths, and feature interactions, the team aims to make data-driven decisions to enhance the user experience and ensure Spotify remains the top choice for music streaming.

## **Data Tables:**

**Table: UserActivity**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| user_id      | Unique identifier for each user | int | Primary Key |
| session_id   | Unique identifier for each session | int | |
| activity_date| Date of the activity | date | |
| activity_type| Type of activity performed | enum | Options: 'play_song', 'skip_song', 'add_to_playlist', 'share_song' |
| session_length | Duration of the session in minutes | float | |

**Table: UserFeatures**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| user_id      | Unique identifier for each user | int | Primary Key, Foreign Key (references UserActivity.user_id) |
| feature_id   | Unique identifier for each feature | int | |
| feature_name | Name of the feature | varchar(255) | |
| feature_interaction_date | Date when the feature was interacted with | date | |
| interaction_count | Number of times the feature was interacted with on a given date | int | |

## Questions

**Question 1:**
- *Topics and Operations:* Aggregation, Date Operations, Filtering
- *Scenario:* The team wants to understand the daily user engagement for the past month. This will help in identifying any specific days with spikes or drops in user activity.
- *Task:* Write an SQL query to calculate the Daily Active Users (DAU) for the last 30 days from a given date, say '2023-10-23'. The result should display the activity date and the count of unique users for that date.


**Question 2:**
- *Topics and Operations:* JOIN, Filtering, Sorting
- *Scenario:* Spotify has recently introduced a new feature, and the team is interested in understanding its adoption rate. Knowing which features are popular can help in prioritizing further enhancements.
- *Task:* Using the UserFeatures table, identify the top 3 features that have the highest interaction count in the last 30 days from '2023-10-23'. Display the feature name and the total interaction count for each.

**Question 3:**
- *Topics and Operations:* Date Operations, Filtering, Window Functions
- *Scenario:* Session length is a critical metric to understand user engagement. A user who spends more time is likely more engaged. However, it's also essential to see how this metric evolves over time.
- *Task:* Calculate the weekly average session length for the past 12 weeks from '2023-10-23'. Display the start date of the week, end date of the week, and the average session length for that week. The result should be ordered by the start date of the week.