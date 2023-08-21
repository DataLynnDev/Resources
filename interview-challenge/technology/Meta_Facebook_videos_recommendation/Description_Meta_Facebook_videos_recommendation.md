# **Business Problem Statement:**
Meta is keen on understanding the user engagement and the effectiveness of its recommendation system for videos on Facebook Watch. The primary goal is to ensure that users view and engage with content that they find relevant and interesting. Additionally, Meta wants to provide value to its content creators by providing insights on viewer demographics and their content's engagement metrics.


## **Data Tables**:

**1. `user_activity`**

| Column Name | Description                                        | Feature Type |
|-------------|----------------------------------------------------|--------------|
| user_id     | Unique identifier for the user                     | Numeric      |
| video_id    | Identifier for the video watched                   | Numeric      |
| watch_time  | Total time user watched the video (in seconds)     | Numeric      |
| liked       | Whether the user liked the video (1 if yes, 0 no)  | Binary       |
| shared      | Whether the user shared the video (1 if yes, 0 no) | Binary       |
| date        | Date when the video was watched                    | Date         |

**2. `video_metadata`**

| Column Name    | Description                          | Feature Type           |
|----------------|--------------------------------------|------------------------|
| video_id       | Unique identifier for the video      | Numeric                |
| genre          | Genre of the video content           | Categorical            |
| uploaded_date  | Date when the video was uploaded     | Date                   |
| creator_id     | Unique identifier for the content creator | Numeric             |

**3. `user_demographics`**

| Column Name | Description                       | Feature Type           |
|-------------|-----------------------------------|------------------------|
| user_id     | Unique identifier for the user    | Numeric                |
| age         | Age of the user                   | Numeric                |
| gender      | Gender of the user (M, F, Other)  | Categorical            |
| location    | Geographic location of the user   | Categorical            |



## **Questions:**

1. **Scenario:** Meta wants to optimize the recommendation system. To do this, it's essential to understand which genres are trending and resonate more with the users. Using the data tables provided, analyze the user engagement patterns and identify the top 3 genres that have the highest average watch time over the last month.


2. **Scenario:** Meta believes there's a strong correlation between user engagement metrics (like watch time, likes, and shares) and the demographics of a user. Given the data provided, can you determine if users in a particular age group or gender are more likely to engage with specific genres of content?


3. **Progressive Scenario:** Content creators have expressed interest in understanding their content's reach. Taking the top genre identified in Question 1, determine which content creator has the most reach (measured by unique viewers) within that genre. Additionally, for this content creator, provide insights into the demographics of their viewership (age distribution, gender distribution).


4. **Scenario:** There's a hypothesis that older videos (more than 6 months old) on Facebook Watch see a decline in user engagement. To validate or refute this, calculate the average watch time of videos based on their age (freshness since upload).

