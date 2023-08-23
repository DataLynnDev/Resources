# **Business Problem Statement**
In the dynamic landscape of TikTok's content platform, the aim is to build a state-of-the-art Personalized Content Recommendation System. The primary objective is to curate a video feed that aligns seamlessly with individual user preferences, ensuring that each user gets a tailored experience that keeps them engaged and active. To achieve this, we are looking for an experienced data scientist who can leverage the vast amount of user interaction data, video metadata, and sophisticated algorithms to enhance our recommendation model's accuracy and efficiency.

## **Data Tables**
**1. Users Table**

| Column Name  | Description                | Feature Type  |
|--------------|----------------------------|---------------|
| user_id      | Unique identifier for user | Categorical   |
| preferred_genre   | User's genre preference    | Categorical   |
| last_active  | Last date user was active  | Date          |

**2. Videos Table**

| Column Name  | Description                       | Feature Type |
|--------------|-----------------------------------|--------------|
| video_id     | Unique identifier for the video   | Categorical  |
| genre        | Genre of the video content        | Categorical  |
| upload_date  | Date when video was uploaded      | Date         |

**3. Interactions Table**

| Column Name  | Description                           | Feature Type |
|--------------|---------------------------------------|--------------|
| interaction_id  | Unique identifier for interation    | Integer  |
| user_id      | Unique identifier for user            | Integer      |
| video_id     | Unique identifier for the video       | Integer      |
| watch_time   | Time spent by user watching the video | Numeric      |
| first_click_timestamp  | The first time user view the video | Date  |
| interaction_type       | Type of interaction with the video | Categorical   |
| shares       | Number of shares    | Integer  |

## **Questions**
1. **Scenario**: We've noticed a trend where users with specific preferences are not as active in recent times. Identify the top three genres that saw the most significant drop in watch time from users who favored them in the last month. Which specific users contributed the most to this decline?


2. **Scenario**: : As TikTok aims to better understand content consumption patterns, there's a hypothesis that certain videos might be closely correlated based on user interactions. For instance, if users who watch "Video A" also frequently watch "Video B", those two videos might be related in some manner, perhaps theme, content, or appeal. For each video, find another video that has the highest correlation value, excluding itself. How might this information be utilized to enhance content recommendation?


3. **Scenario**: To understand the effectiveness of our current recommendation system, create a machine learning model to predict the watch time of a video based on user preferences and video genre. Briefly, explain how you would approach this, the features you'd consider, and any potential pitfalls.


4. **Scenario**: We are launching a new feature which will introduce a 'Spotlight' section on the app, showcasing videos from genres that are currently trending among the user base. This is expected to boost the DAU. Design an A/B test to validate the effectiveness of this new feature. Describe how you would structure this test, the metrics you would track, and the success criteria.