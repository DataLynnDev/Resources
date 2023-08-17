# Business Problem Statement

TikTok's Ads Measurement team is intent on uncovering deeper insights into the effectiveness and performance of its advertising campaigns. With a landscape teeming with competition in the digital ad space, it's pivotal for TikTok to provide data-driven evidence that demonstrates the tangible impact of advertisers' campaigns. Your mission is to employ experimental design, causal inference techniques, and analytics to mine invaluable insights that will escalate advertiser value, guide the evaluation of ad campaigns, and fortify ROI on the TikTok platform.

---

## Data Tables

**UserActivity**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| UserId | Unique identifier for each user | Categorical |
| VideoId | Unique identifier for each video watched by user | Categorical |
| AdType | Type of Ad (e.g., Image, Video, Carousel) | Categorical |
| WatchDuration | Duration for which user watched the video/ad (in seconds) | Numerical |
| InteractionType | Type of interaction (e.g., Like, Share, Comment) | Categorical |
| InteractionTimestamp | Timestamp when interaction was made | DateTime |

**AdCampaigns**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| CampaignId | Unique identifier for each ad campaign | Categorical |
| AdType | Type of Ad (e.g., Image, Video, Carousel) | Categorical |
| StartDate | Start date of the campaign | DateTime |
| EndDate | End date of the campaign | DateTime |
| Budget | Total budget for the campaign | Numerical |
| TargetDemographics | Target audience for the ad (e.g., Age 18-24, Female) | Categorical |

**UserPatterns**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| UserId | Unique identifier for each user | Categorical |
| SessionId | Unique identifier for each app session | Categorical |
| AvgScreenTime | Average time spent on screen (in seconds) per session | Numerical |
| Frequency | Number of app launches per day | Numerical |
| LastActivityDate | Last date the user interacted with the app | DateTime |

---

**Questions:**

1. A hypothesis has been posited by the marketing team suggesting that video ads drive more user interactions (likes, shares, comments) and have better performance than other ad types. Using the `UserActivity` table, verify this hypothesis.

2. As the digital advertising space evolves, so does the risk of fraudulent activities. Leveraging the `UserActivity` and `UserPatterns` tables, propose a machine learning model to detect potential anomalies like bots or non-human interactions that could skew ad performance metrics. Specify which features you'd extract, the model's training process, validation strategy, and its potential implications for ad campaign assessments.

3. Now that we have a good fraud model, how can we decrease such activities on the platform? Furthermore, how should we adjust the ad campaign assessment metrics? Provide both the original and adjusted definitions of the metrics you choose.

4. Recently, an advertiser collaborated with TikTok and initiated a hashtag challenge. Please devise a methodology to assess the challenge's effectiveness. How you'd distinguish the influence of the hashtag challenge from organic growth or other factors?
