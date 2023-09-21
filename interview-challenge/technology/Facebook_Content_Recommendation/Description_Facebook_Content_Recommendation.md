# **Business Problem Statement:**
Given the role of the Facebook Content Recommendation Systems team, the business problem revolves around optimizing content recommendations for users. With millions of posts being made on Facebook daily, ensuring users receive the best content tailored for them is crucial. The challenge lies in understanding and analyzing how users are interacting with recommended content, discerning patterns, preferences, and potential areas of improvement.

**More Detailed Statement:**
"User engagement with recommended content has shown some anomalies in the past quarter. There's a need to deep dive into the data, identify the type of content that's seeing reduced engagement, understand user preferences, and check if the recommendation engine is functioning as expected. Furthermore, we need to identify any potential factors influencing these anomalies and devise strategies to enhance our recommendation engine's efficiency."

## **Data Tables:**

1. **Table Name**: UserInteractions

| **Column Name** | **Description**     | **Feature Type** |
|-------------|----------|-----|
| userID        | Unique identifier for users | Integer |
| postID        | Unique identifier for posts | Integer |
| interactionType | Like, Share, Comment, Ignore | String |
| timestamp     | Time of interaction | Datetime |
| contentType   | Type of content - Video, Image, Text, Link | String |


2. **Table Name**: PostDetails

| **Column Name** | **Description**     | **Feature Type** |
|:-------------|:----------|:-----|
| postID        | Unique identifier for posts | Integer |
| contentCategory | News, Entertainment, Sport, etc. | String |
| postTimestamp | When the post was made | Datetime |
| authorID      | User ID of the post author | Integer |

## Question

**1. Data Cleaning & Exploration Question**

**Scenario**:
You've been given the UserInteractions table which contains a timestamp of user interactions. Before deep diving into analysis, understanding the data distribution is crucial.

**Task**:
Find the median timestamp of interactions and identify the first day with the least number of user interactions.


**2. SQL Queries Question**

**Scenario**:
The recommendation engine focuses on both user and content. By understanding which content categories are most interacted with, we can discern patterns and potentially enhance our recommendations.

**Task**:
Using the UserInteractions and PostDetails tables, list the top 3 contentCategories with the most 'Like' interactions.

**3. Probability and Statistical Analysis Question**

**Scenario**:
A preliminary analysis suggests that user interactions with 'Sport' content and 'Entertainment' content are independent of each other.

**Task**:
Using the UserInteractions table, calculate the probability that a randomly selected interaction is both a 'Sport' content and has a 'Like' interaction. Then, validate if the two events are indeed independent.


**4. Product & Business Sense Question**

**Scenario**:
The metrics from last month show a 10% drop in user engagement with recommended 'News' content, even though the overall interactions with 'News' content remained constant.

**Task**:
Considering your previous findings, propose reasons for this drop and suggest potential strategies to improve engagement with the 'News' content recommendations.
