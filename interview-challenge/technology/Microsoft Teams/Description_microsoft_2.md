# Business Problem Statement

As Microsoft Teams continues to experience exponential growth, the integration of Office 365 products like Word, Excel, PowerPoint, and OneNote within the Teams environment becomes pivotal. To further enhance user collaboration and productivity, there's a need to understand users' behavior and preferences when using these integrated features. Our goal is to offer tailored features, boost real-time collaboration, and predict potential challenges that could hinder user satisfaction and efficiency.


## Data Tables

| Table Name | Column Name | Description | Feature Type |
|------------|-------------|-------------|--------------|
| `user_activity` | `user_id` | Unique identifier for each user | Categorical |
|  | `timestamp` | Time of the activity | Datetime |
|  | `document_type` | Type of document accessed (Word, Excel, PowerPoint, OneNote) | Categorical |
|  | `activity_type` | Type of activity (Opened, Edited, Commented, Closed) | Categorical |
|  | `duration` | Time spent on the document (in minutes) | Numeric |
|  | `collaborated_next_month`  | user will engage in collaboration on a given Office 365 document within Teams in the next month | Categorical  |
| `document_collaboration` | `document_id` | Unique identifier for each document | Categorical |
|  | `user_id` | ID of the user accessing the document | Categorical |
|  | `collaborators_count` | Number of collaborators on the document | Numeric |
|  | `comments_count` | Number of comments on the document | Numeric |


---

## Questions

1. **Predicting User Activity and Collaboration**: Based on historical data from `user_activity` and `document_collaboration`, can you build a model that predicts if a user will engage in collaboration on a given Office 365 document within Teams in the next month (`collaborated_next_month`)? Please consider the factors that might affect this, such as the type of document most commonly accessed or the typical activity type. Describe your approach and the steps you would take to solve this problem.


2. **Exploratory Analysis for User Collaboration**: Consider the dataset `document_collaboration`. What is the probability that a document with more than 5 comments will have more than 3 collaborators? Please approach this problem by simulating a random draw of documents and calculating the probability over 100 such draws.


3. **Optimizing User Experience**: From the `user_activity` table, let's imagine the duration on each document type is a sequence. Your goal is to determine the subsequence where users spent the maximum time continuously, which might give insights into which workflows are the most engaging. Describe your approach.

  
4. **Real-time Collaboration Enhancement**: Considering the `document_collaboration` table, if a document has a higher number of collaborators, can you build a system to recommend other users that might be interested in collaborating on it? Describe the metrics and algorithms you'd employ.