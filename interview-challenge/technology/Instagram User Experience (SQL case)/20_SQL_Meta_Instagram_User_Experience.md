# **Business Problem Statement:**
Instagram is planning to launch a new feature called “Story Poll”, allowing users to post polls on their stories. This feature aims to increase user engagement on the Instagram platform. Before rolling out to all users, Instagram wants to conduct an A/B test to evaluate the effectiveness of the “Story Poll” feature. The Data Analyst needs to analyze the A/B test data to understand how the new feature affects user engagement and interaction.

## **Data Tables:**

1. **Table: Users**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| user_id      | Unique identifier for each user | INT | Primary Key |
| join_date    | The date when the user joined Instagram | DATE | - |
| variant      | The variant the user is exposed to (Control or Treatment) | ENUM | Options: ‘Control’, ‘Treatment’ |
| engagement_score | The user's engagement score before the A/B test | INT | - |

2. **Table: Story_Events**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| story_id     | Unique identifier for each story | INT | Primary Key |
| user_id      | ID of the user who posted the story | INT | Foreign Key (references Users.user_id) |
| event_date   | The date when the story was posted | DATE | - |
| poll_posted  | Whether a poll was posted in the story or not | BOOLEAN | - |
| interactions | Number of interactions (views, replies, etc.) the story received | INT | - |

## Questions

**Question 1:**
- **Topics & Operations:** Aggregation, Group By, Order By
- **Scenario:** You need to understand the baseline engagement level of both groups before the test. This will help you in understanding any significant changes in user engagement after the implementation of the new feature.
- **Task:** Calculate the average engagement score for users in both the Control and Treatment groups before the A/B test starts. Return the result with variant and average engagement score, ordered by average engagement score in descending order.

**Question 2:**
- **Topics & Operations:** Join Operations, Conditional Filtering, Aggregation
- **Scenario:** To evaluate the impact of the “Story Poll” feature, you need to analyze how many stories with polls are posted by the users in the Treatment group compared to the Control group (who can’t post polls).
- **Task:** Count the number of stories with polls posted by users in both groups. Return the result with variant and the count of stories with polls.

**Question 3:**
- **Topics & Operations:** Join Operations, Aggregation, Conditional Aggregation, Group By, Having
- **Scenario:** To understand the effectiveness of the “Story Poll” feature in driving user engagement, you want to analyze the interaction with stories having polls and those without polls in the Treatment group.
- **Task:** For the Treatment group, calculate the average number of interactions for stories with polls and without polls. Return the variant, average interactions for stories with polls, and average interactions for stories without polls.