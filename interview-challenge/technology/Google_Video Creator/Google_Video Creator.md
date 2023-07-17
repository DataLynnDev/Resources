# Business Problem Statement:
In the world of YouTube, retaining video creators who consistently generate high-quality content is key to maintaining a dynamic and engaged audience base. Our challenge is to predict whether a creator will be successful enough to continue creating content on YouTube (and thereby avoid "churn"). This classification problem is to determine whether a video creator will earn enough revenue to continue their content creation on YouTube.

# Data Tables
### 'VideoData' Table:

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


### 'CreatorBehaviorData' Table:

| Feature Name         | Description                                          |
|----------------------|------------------------------------------------------|
| CreatorID            | Unique identifier for each creator                   |
| TotalUploads         | Total number of video uploads by the creator         |
| AvgUploadFrequency   | Average frequency of video uploads by the creator    |
| AvgResponseTime      | Average time taken by the creator to respond to comments  |
| CollaborationCount   | Number of collaborations the creator has done with other creators |
| AvgVideoDuration     | Average duration of the creator's videos             |

### 'RevenueData' Table:

| Feature Name              | Description                                     |
|---------------------------|-------------------------------------------------|
| CreatorID                 | Unique identifier for each creator              |
| MonthlyAdRevenue          | Monthly revenue earned by the creator from ads  |
| MonthlySubscriptionRevenue| Monthly revenue earned by the creator from premium subscriptions |
| TotalRevenue              | Total revenue earned by the creator             |
| RevenueChange             | Change in the revenue compared to the previous month |

### 'ContentTypeData' Table:

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

### 'UserChurn' Table:

| Feature Name  | Description                                              |
|---------------|----------------------------------------------------------|
| CreatorID     | Unique identifier for each creator                       |
| ChurnStatus   | Binary indicator (1 - Churn, 0 - Not Churn) showing whether the creator left YouTube or not |




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

# Question 1

To investigate the observable trends or patterns in the 'VideoData' and 'RevenueData' that might contribute to a creator's revenue, we can calculate correlations between different variables such as 'ViewCount', 'LikeCount', 'DislikeCount', 'CommentCount' from the 'VideoData' table and 'TotalRevenue' from the 'RevenueData' table. Correlation analysis measures the extent to which two variables move in relation with each other.

For this task, I will use Python and the library pandas for data handling and manipulation, and seaborn for data visualization. I will also use the scipy library to calculate the correlation coefficient.

The steps I'm going to follow are:

1. Merge 'VideoData' and 'RevenueData' tables on 'CreatorID'.
2. Calculate the sum of 'ViewCount', 'LikeCount', 'DislikeCount', 'CommentCount' for each 'CreatorID' to have an overall representation of their YouTube activities.
3. Calculate correlations between 'TotalRevenue' and each of the columns 'ViewCount', 'LikeCount', 'DislikeCount', 'CommentCount'.
4. Visualize these correlations using a heatmap.

Now let's write down the Python code for this:

**code block 1**

In this code, we first merge 'VideoData' and 'RevenueData' DataFrames on 'CreatorID' to create the 'merged_data' DataFrame. We then aggregate the 'ViewCount', 'LikeCount', 'DislikeCount', 'CommentCount' by 'CreatorID' and take the mean of 'TotalRevenue' per 'CreatorID' to create the 'grouped_data' DataFrame.

The 'correlations' DataFrame is then created by calculating the correlation between 'ViewCount', 'LikeCount', 'DislikeCount', 'CommentCount' and 'TotalRevenue' columns of 'grouped_data' DataFrame.

Finally, we print the 'correlations' DataFrame and display a heatmap of these correlations using seaborn's heatmap function. This will visually illustrate which video engagement metrics have the strongest correlation with 'TotalRevenue'.

# Question 2

When assessing creator engagement on YouTube, several key behaviors from the 'CreatorBehaviorData' table can be considered:

1. 'TotalUploads': The number of videos a creator has uploaded could indicate their consistency and commitment.
2. 'AvgUploadFrequency': This shows how regularly the creator posts new content, which might impact viewer engagement and channel growth.
3. 'AvgResponseTime': Quick response times to viewer comments might suggest an engaged creator who values their community.
4. 'CollaborationCount': Frequent collaborations can suggest a creator who is actively networking and seeking new ways to reach wider audiences.
5. 'AvgVideoDuration': Longer videos might show a creator's willingness to invest significant time and effort into their content.

One way to classify these behaviors could be to normalize these features and then add them together to get an engagement score for each creator. For example, we could score each of the factors on a scale of 0-1 (with 1 being the best), and then add the scores together.

To handle different scales and units, I'll use Min-Max Normalization, which will transform all the features values between 0 and 1.

Here is a Python script that accomplishes this:

**code block 2 & 3**

In this code, `MinMaxScaler()` is a function from the `sklearn.preprocessing` module. It scales and translates each feature individually such that it is in the given range on the training set, i.e., between zero and one.

The `EngagementScore` is calculated as the sum of these scaled features, giving us a single metric that combines all the selected engagement behaviors.

Remember that this is just one of many possible ways to generate a new feature to represent the level of creator engagement. Depending on the specific context or objectives, you might want to use different features, apply different transformations, or even use more sophisticated techniques, such as Principal Component Analysis (PCA) or clustering.

# Question 3

Tracking trends over time for something like creator earnings requires historical data with timestamps, however, from the provided 'RevenueData' table, it appears we only have access to a snapshot of the current month's revenue.

Despite this, we can still calculate the percentage change in total revenue from the previous month using the 'RevenueChange' column provided, which presumably provides the percentage change in revenue from the previous month. But, ideally, to track and visualize revenue trends, we would prefer data containing creator earnings per month over a certain period.

Assuming we had a more detailed 'RevenueData' table containing monthly data, we could use a Python script using pandas DataFrame to calculate the revenue change month over month as follows:

**code block 4, 5 & 6**

# Question 4

From the 'ContentTypeData' table, we can observe that creators produce a variety of content types: Vlog, Tutorial, Review, Entertainment, Gameplay, Music, and News. The popularity of these types may vary and have a different impact on a creator's performance.

One way to analyze the impact of content type on a video's performance is to calculate a creator's majority content type and then examine how that type correlates with performance measures like 'ViewCount', 'LikeCount', 'DislikeCount', 'CommentCount' from 'VideoData' table, and revenue data from 'RevenueData' table.

We could propose the following steps:

1. Determine the majority content type for each creator from the 'ContentTypeData' table.
2. Merge this information with 'VideoData' and 'RevenueData' tables using 'CreatorID'.
3. Calculate average performance metrics (views, likes, dislikes, comments, total revenue) for each majority content type.
4. Compare these averages to see if certain content types tend to have higher performance.

Here's a Python script that implements this using pandas:

**code block 7**

This script first calculates the majority content type for each creator and then merges this data with the video and revenue data. It then calculates the average performance metrics for each content type. The resulting DataFrame gives an overview of how different content types perform on average.

To visualize the result, you could add:

**code block 8**

# Question 5

Synthesizing the findings from previous tasks involves analyzing data from 'CreatorBehaviorData' (where we have the 'EngagementScore'), 'VideoData' (performance metrics like 'ViewCount', 'LikeCount', etc.), and 'RevenueData' (where we have 'TotalRevenue' and 'RevenueChange').

Here's a proposed approach to find a connection:

1. Merge 'EngagementScore' from 'CreatorBehaviorData' with 'VideoData' and 'RevenueData' using 'CreatorID'.
2. Calculate correlation coefficients among 'EngagementScore', performance metrics, 'TotalRevenue', and 'RevenueChange' to see if any strong relationships exist.

Here's a Python script using pandas and seaborn for heatmap visualization:

**code block 9**

This script first merges the relevant data from 'CreatorBehaviorData', 'VideoData', and 'RevenueData'. It then calculates a correlation matrix among 'EngagementScore', performance metrics, 'TotalRevenue', and 'RevenueChange'.

The heatmap helps visualize these correlations: darker colors represent stronger correlations. By observing the heatmap, we can deduce whether there's a connection between a creator's engagement level, their videos' performance, and the trend in their earnings.

Again, please note that this code assumes 'CreatorID' is the unique identifier in each DataFrame and there's only one record per creator in the 'CreatorBehaviorData' DataFrame. If there are multiple records for each creator, this code needs to be adapted accordingly.

# Question 6

Predicting a creator's 'ChurnStatus' is a binary classification problem since a creator can either churn (1) or not churn (0). Therefore, algorithms like Logistic Regression, Decision Trees, Random Forest, Gradient Boosting, and Support Vector Machines can be used. However, for this case, we'll opt for a Random Forest Classifier due to its robustness to overfitting and capability to handle a mix of binary and continuous variables.

Here's the general approach we can take:

1. Merge the 'EngagementScore', 'VideoData', 'RevenueData', and 'ContentTypeData' tables on 'CreatorID'.
2. Create dummy variables for categorical features like 'MajorityContentType'.
3. Split the data into a training set and a test set.
4. Fit a Random Forest Classifier on the training set.
5. Predict 'ChurnStatus' for the test set and calculate the model's performance metrics.

Here's how to do this in Python using pandas and scikit-learn:

**code block 10 & 11**

The `classification_report` will provide precision, recall, f1-score, and support for both classes, and the `confusion_matrix` will indicate true positives, false positives, true negatives, and false negatives.

Based on the findings from this model, if we notice certain features (like low 'EngagementScore' or decreasing 'TotalRevenue') are significant predictors of churn, YouTube could focus on these areas to improve their creator retention strategy. For example, they could implement initiatives to boost creator engagement or provide additional revenue-generating opportunities for creators.

Remember, it's critical to conduct a proper exploratory data analysis, feature engineering, and model tuning to maximize the performance of the model. The script provided above is a simplified example of a machine learning pipeline, and in a real-world scenario, each step would require careful consideration and potentially much more complexity.









