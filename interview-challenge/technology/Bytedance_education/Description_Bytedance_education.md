# Business Problem Statement
Tiktok's Education Business Group is focusing on enhancing the user engagement and effectiveness of its educational platforms and tools. The challenge lies in identifying optimal strategies for content delivery, user retention, and collaboration between content providers and users. The goal is to analyze user behavior, identify patterns, and implement models to predict user preferences and needs, allowing for personalized content recommendations, targeted marketing, and performance improvement.

## Data Tables
**Table 1: Users**

| Column Name  | Description                                     | Feature Type |
|--------------|-------------------------------------------------|--------------|
| user_id      | Unique identifier for the user                  | Categorical  |
| age          | Age of the user                                 | Numerical    |
| education    | Education level of the user                     | Categorical  |
| join_date    | Date when the user joined the platform          | Date         |
| last_login   | Date of the user's last login                   | Date         |

**Table 2: Content**

| Column Name  | Description                                     | Feature Type |
|--------------|-------------------------------------------------|--------------|
| content_id   | Unique identifier for the content               | Categorical  |
| subject      | Subject of the content                          | Categorical  |
| difficulty   | Difficulty level of the content                 | Numerical    |
| author_id    | ID of the author who created the content        | Categorical  |
| creation_date| Date when the content was created               | Date         |

**Table 3: User_Content_Interaction**

| Column Name  | Description                                     | Feature Type |
|--------------|-------------------------------------------------|--------------|
| user_id      | Unique identifier for the user                  | Categorical  |
| content_id   | Unique identifier for the content               | Categorical  |
| interaction_date | Date of the interaction                     | Date         |
| rating       | User rating of the content (1-5)                | Numerical    |
| completion   | Whether the content was completed (0 or 1)      | Binary       |

## Questions

1. **Analyze User Behavior and Content Preference:**
   - Using data from the `Users`, `Content`, and `User_Content_Interaction` tables, determine the correlation between user's education level, content difficulty, and rating. What insights can you infer about user behavior and preferences? Can these insights help in content optimization?


2. **Optimize Marketing Strategies:**
   - Given a marketing budget $10,000 and targeting a specific age group between 18 and 30, write an SQL query to find users who have not logged in during the last month but have previously shown interest in a particular subject. How would you use this data to design targeted marketing campaigns?


3. **Performance Improvement through A/B Testing:**
   - Design an A/B testing strategy to test a new feature aiming to increase user engagement. What metrics would you monitor, and how would you analyze the results to decide whether the feature is successful?

