# **Business Problem Statement:**
As the lead for the Content Recommendation Systems at Facebook, our ultimate goal is to optimize user experience on the News Feed. With billions of posts generated every day, determining which content is most relevant to a user while also fostering positive community engagement is a challenging task. We are aiming to refine our recommendation system by understanding various aspects of user engagement and the characteristics of content that goes into their feed.

## Data Tables

**User Feed**

| Column Name | Description                                     | Feature Type      |
|-------------|-------------------------------------------------|-------------------|
| user_id     | Unique identifier for the user                  | Categorical       |
| post_id     | Unique identifier for the post                  | Categorical       |
| timestamp   | Timestamp of when the post appeared in feed     | DateTime          |
| interaction | Type of interaction (like, share, comment, etc.)| Categorical       |



**Posts**

| Column Name    | Description                                     | Feature Type      |
|----------------|-------------------------------------------------|-------------------|
| post_id        | Unique identifier for the post                  | Categorical       |
| content_type   | Type of content (image, text, video, etc.)      | Categorical       |
| creator_id     | Unique identifier for the content creator       | Categorical       |
| post_timestamp | Timestamp of when the post was created          | DateTime          |
| is_sponsored   | Whether the post is sponsored (0/1)             | Binary            |



**User Info**

| Column Name  | Description                                | Feature Type      |
|--------------|--------------------------------------------|-------------------|
| user_id      | Unique identifier for the user             | Categorical       |
| age_group    | Age group of the user                      | Categorical       |
| country      | Country of the user                        | Categorical       |
| last_active  | Last time user was active                  | DataTime |


## **Questions:**

1. **Scenario:** We've noticed a surge in the interaction with posts that are videos.

 Determine which age group and country combo has the highest interaction rate with video content in the past month. This will help us understand our demographic better. How would you approach this?


2. Given that the News Feed algorithm's goal is to prioritize the most relevant content, consider the following: If we have information that a certain user (please use 'user_100' in this question) frequently interacts with posts from a particular creator and this creator has posted new content within "2023-08-17" and "2023-08-18", how would you design a SQL query to fetch such posts? Also, ensure that sponsored posts get a slightly higher priority.

3. **Scenario:** A recent A/B test suggested that users who engage with text-based posts spend more time on the platform than others.

 Based on this, compute the average time difference between a user's last interaction with a text post and their last active timestamp. Would this information be a compelling case for the algorithm to prioritize text posts for these users? Justify.


4. One of the complexities in curating the News Feed is managing sponsored content. How would you approach the balance between showing users sponsored content while maintaining a high level of user engagement? Taking into consideration the provided data, construct a model to predict the likelihood of a user interacting with a sponsored post. What features would be significant for this model?

