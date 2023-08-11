# Business Problem Statement:
In the world of YouTube, retaining video creators who consistently generate high-quality content is key to maintaining a dynamic and engaged audience base. Our challenge is to predict whether a creator will be successful enough to continue creating content on YouTube (and thereby avoid "churn"). This classification problem is to determine whether a video creator will earn enough revenue to continue their content creation on YouTube.

## Data Tables
1. **'VideoData' Table:**

| Feature Name   | Description                                    |
|----------------|------------------------------------------------|
| CreatorID      | Identifier linking the video to its creator    |
| CreatorName      |  Creator's account name    |
| VideoID        | Unique identifier for each video               |
| UploadDate     | Date the video was uploaded                    |
| ViewCount      | Number of views for a given video              |
| LikeCount      | Number of likes for a given video              |
| DislikeCount   | Number of dislikes for a given video           |
| CommentCount   | Number of comments on a given video            |


2. **'CreatorBehaviorData' Table:**

| Feature Name         | Description                                          |
|----------------------|------------------------------------------------------|
| CreatorID            | Unique identifier for each creator                   |
| TotalUploads         | Total number of video uploads by the creator         |
| AvgUploadFrequency   | Average frequency of video uploads by the creator    |
| AvgResponseTime      | Average time taken by the creator to respond to comments  |
| CollaborationCount   | Number of collaborations the creator has done with other creators |
| AvgVideoDuration     | Average duration of the creator's videos             |

3. **'RevenueData' Table:**

| Feature Name              | Description                                     |
|---------------------------|-------------------------------------------------|
| CreatorID                 | Unique identifier for each creator              |
| MonthlyAdRevenue          | Monthly revenue earned by the creator from ads  |
| MonthlySubscriptionRevenue| Monthly revenue earned by the creator from premium subscriptions |
| TotalRevenue              | Total revenue earned by the creator             |
| RevenueChange             | Change in the revenue compared to the previous month |

4. **'ContentTypeData' Table:**

| Feature Name        | Description                               |
|---------------------|-------------------------------------------|
| CreatorID           | Unique identifier for each creator        |
| VlogCount           | Number of vlog type videos                |
| TutorialCount       | Number of tutorial type videos            |
| ReviewCount         | Number of review type videos              |
| EntertainmentCount  | Number of entertainment type videos       |
| GameplayCount       | Number of gameplay type videos            |
| MusicCount          | Number of music type videos               |
| NewsCount           | Number of news type videos                |

5. **'UserChurn' Table:**

| Feature Name  | Description                                              |
|---------------|----------------------------------------------------------|
| CreatorID     | Unique identifier for each creator                       |
| ChurnStatus   | Binary indicator (1 - Churn, 0 - Not Churn) showing whether the creator left YouTube or not |


## Data Challenge Questions

1. **"Video Engagement and Revenue Correlation (SQL/Python)"**

   Investigate any observable trends or patterns in the 'VideoData' and 'RevenueData' tables that might contribute to a creator's revenue. Consider aspects such as views, likes, dislikes, and comments. Craft an SQL query or Python script that quantifies these patterns or correlations.

2. **"Unearthing Creator Engagement Levels" (Python)**

   Analyzing the 'CreatorBehaviorData' table, imagine a system to define creators' level of engagement. What behaviors would you focus on and how would you classify these? Provide your rationale and develop a Python script to generate this new feature.

3. **"Tracking Revenue Trends (SQL/Python)"**

   Utilizing the 'RevenueData' table, how would you keep track of the fluctuating creator earnings? Can you conceive of a mechanism to record the change in their income over time? Explain your thought process and devise a Python or SQL script that implements this mechanism.

4. **"Content Type and Its Effect on Performance (Python)"**

   Reviewing the 'ContentTypeData' table, what insights can you draw about the influence of content type on a video's performance? Can you propose any new measures or metrics that could highlight this impact more clearly? Construct a Python script to create these proposed measures.

5. **"Synthesizing Creator Engagement and Revenue Trend (Python)"**

   Integrating the findings from the first three tasks, can you deduce a connection between the creator's engagement level, their videos' performance, and the trend in their earnings? Illustrate this association using Python.

6. **"Anticipating Creator Churn (Python)"**

   Utilizing the features and insights derived from the previous tasks, conceive a system to predict a creator's 'ChurnStatus' as described in the 'UserChurn' table. What machine learning model would you opt for and why? Justify your choices, create a Python script to build this model, and evaluate its performance. Lastly, suggest any potential improvements for YouTube's creator retention strategy based on your findings.