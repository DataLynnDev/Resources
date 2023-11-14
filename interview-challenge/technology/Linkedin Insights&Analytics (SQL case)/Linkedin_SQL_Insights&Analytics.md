# **Business Problem Statement:**

LinkedIn is keen on delivering enriched insights to both individual and corporate users to aid them in understanding their engagement and reach on the platform. There's a need to analyze vast amounts of data pertaining to user interactions, post engagements, profile visits, and other related metrics to generate insightful reports. This data can help in enhancing the LinkedIn Insights and Analytics feature, which is crucial for users to measure and understand their impact on the platform.

## **Data Tables:**

Table 1: `UserInteractions`

| Feature Name     | Brief Feature Description                  | Feature Data Type | Comments                              |
|------------------|--------------------------------------------|-------------------|---------------------------------------|
| interaction_id   | Unique ID for the interaction              | int               | Primary Key                           |
| user_id          | ID of the user involved                    | int               |                                       |
| post_id          | ID of the post interacted with             | int               |                                       |
| interaction_type | Type of interaction (like, share, comment) | enum              | Options: like, share, comment         |
| interaction_date | Date of interaction                        | date              |                                       |
| interaction_time | Time of interaction                        | time              |                                       |

Table 2: `PostMetrics`

| Feature Name      | Brief Feature Description       | Feature Data Type | Comments           |
|-------------------|---------------------------------|-------------------|--------------------|
| post_id           | Unique ID for the post          | int               | Primary Key        |
| user_id           | ID of the user who posted       | int               | Foreign Key        |
| post_date         | Date the post was made          | date              |                    |
| post_time         | Time the post was made          | time              |                    |
| views             | Number of views on the post     | int               |                    |
| engagement_score  | Engagement score of the post    | float             | Calculated Metric  |

## Questions

**SQL Questions:**

1. - **Topics and Operations**: Aggregation, Group By, Derived Metrics
   - **Scenario**:
   To provide meaningful insights, LinkedIn needs to calculate the engagement score for each post. The engagement score is calculated as the total number of interactions (likes, shares, comments) per post divided by the total number of views on that post.
   - **Task**:
   Write a SQL query to calculate the engagement score for each post and order the result by engagement score in descending order.

2. - **Topics and Operations**: Window Functions, Rolling Averages, Date Operations
   - **Scenario**:
   LinkedIn wants to analyze the rolling 7-day average engagement score for each user to understand user engagement trends over time.
   - **Task**:
   Write a SQL query to calculate the rolling 7-day average engagement score for each user. Display the user_id, date, and rolling 7-day average engagement score. Order the result by user_id and date in ascending order.

3. - **Topics and Operations**: Join Operations, Filtering, Percentage Calculation
   - **Scenario**:
   LinkedIn is interested in identifying the percentage of posts that received interactions (likes, shares, comments) within the first hour of posting, as this is a crucial metric for user engagement.
   - **Task**:
   Write a SQL query to find the percentage of posts that received interactions within the first hour of posting for each user. Display the user_id and the percentage of posts. Order the result by percentage in descending order.