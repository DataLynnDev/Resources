# **Business Problem Statement:**
Meta Facebook's User Recommendation Team is keen on enhancing user engagement and satisfaction by suggesting more relevant content and connections. However, there have been recent concerns about the efficiency of the recommendation algorithms. The team believes that by analyzing user interactions with the recommended content and connections, they can derive insights to refine the recommendation strategies. The primary goal is to understand user preferences and behaviors concerning the recommendations and use this data to improve the recommendation engine.

## **Data Tables:**

**Table: UserInteractions**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| user_id      | Unique identifier for each user | int | Primary Key |
| content_id   | Unique identifier for recommended content | int | |
| interaction_date | Date when the user interacted with the content | date | |
| interaction_type | Type of interaction (view, like, share, etc.) | enum | Options: 'view', 'like', 'share', 'comment', 'ignore' |
| duration     | Time spent on the content in seconds | float | |
| connection_id | Unique identifier for recommended connections | int | |

**Table: ContentDetails**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| content_id   | Unique identifier for each content | int | Primary Key |
| content_type | Type of content (post, video, article, etc.) | enum | Options: 'post', 'video', 'article', 'photo' |
| content_date | Date when the content was posted | date | |
| author_id    | User ID of the content creator | int | |

## Questions

**Question 1:**
- **Scenario:** The team believes that the duration a user spends on a piece of content is a strong indicator of its relevance to the user. They want to understand the average time users spend on different types of content.
- **Task:** Write a SQL solution to calculate the average duration users spend on each content type (post, video, article, photo). Return the content_type and its corresponding average duration, rounded to 3 decimal places.


**Question 2:**
- **Scenario:** The team is interested in understanding the depth of user engagement with the recommended content. They believe that users who interact with the content in multiple ways (like, share, comment) are more engaged.
- **Task:** Write a SQL solution to find out how many users interacted with the content in multiple ways during a single visit. Specifically, calculate the number of unique interaction types per content for each user and return the content_id, user_id, and the count of unique interaction types (Only find for the first three user).


**Question 3:**
- **Scenario:** The team wants to understand the retention rate of users with the recommended content. Specifically, they are interested in knowing how many users return to view the same content multiple times.
- **Task:** Write a SQL solution to calculate and find the retention rate greater than 0 for each content_id. The retention rate is defined as the number of users who viewed the content more than once divided by the total number of unique users who viewed the content, rounded to 2 decimal places. Return the content_id and its corresponding retention rate.

