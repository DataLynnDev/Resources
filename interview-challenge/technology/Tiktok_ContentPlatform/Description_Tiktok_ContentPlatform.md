# Business Problem Statement
TikTok's User-Generated Content Platform team is responsible for managing and moderating a massive volume of user-generated content. This moderation ensures that the content adheres to community guidelines, copyright laws, and various international regulations. However, maintaining this level of scrutiny across billions of videos is highly challenging and requires continuous optimization.

The business problem here revolves around enhancing the content moderation process through data-driven decisions. The goal is to create a sophisticated system that effectively identifies and filters inappropriate content while ensuring that authentic and engaging content reaches the audience without delay.

## Data Tables
#### Table 1: Video_Details
| Column Name   | Description                                         | Feature Type   |
|---------------|-----------------------------------------------------|----------------|
| video_id      | Unique identifier for each video                    | Categorical    |
| uploader_id   | Unique identifier for the uploader                  | Categorical    |
| content_type  | Type of video content (e.g., comedy, educational)   | Categorical    |
| upload_date   | Date and time of the video upload                   | Timestamp      |
| flag_status   | Moderation status (e.g., approved, flagged)         | Categorical    |

#### Table 2: User_Actions
| Column Name   | Description                     | Feature Type   |
|---------------|---------------------------------|----------------|
| user_id       | Unique identifier for the user  | Categorical    |
| video_id      | Unique identifier for the video | Categorical    |
| action_type   | Type of user action (e.g., view, like, report) | Categorical |
| action_date   | Date and time of the action     | Timestamp      |

## Questions
#### Question 1:
**Scenario:** As a part of content moderation, it is important to identify potential patterns of inappropriate content. You are tasked with identifying trends in flagged content over time.

* Using Table 1, write an SQL command to find the number of flagged videos by content_type per month. Can you identify any seasonal trends or patterns that might suggest automated uploads of inappropriate content?


#### Question 2:
**Scenario:** TikTok wants to optimize its 'For You' feed to better understand how users engage with different types of content.

* Using Tables 1 and 2, how would you design an experiment to understand the correlation between content_type and user engagement (e.g., views, likes)? What challenges might arise due to high correlation between different types of engagement?


#### Question 3:
**Scenario:** Based on the insights from Question 1, your next task is to create a machine learning model to detect suspicious patterns that may indicate automated uploads of inappropriate content.

* Describe a machine learning model to detect this specific behavior. What features would you consider, and what evaluation metric (such as Recall) would be most appropriate here? How might the insights from Question 1 inform your feature engineering?



