# **Business Problem Statement:**
The integrity of content on Facebook is of paramount importance. With billions of pieces of content being shared daily, we need to ensure that we identify, flag, and in some cases, remove content that violates Facebook's community standards, including hate speech, misinformation, or inappropriate content. For this, we are looking for a Data Scientist who can use their skills in SQL, probability and statistics, machine learning, and product sense to help us better manage and moderate content, ensuring a safe environment for all our users.

## **Data Tables:**

**Table: ContentPosts**

| Column Name | Description                        | Feature Type  |
|-------------|------------------------------------|---------------|
| postID      | Unique identifier for the post     | Categorical   |
| userID      | ID of the user who made the post   | Categorical   |
| postText    | Text of the post                   | Text          |
| postDate    | Date and time of the post          | DateTime      |
| flagged     | Whether post was flagged (0/1)     | Binary        |
| category    | Category of the post (text, video, image)  | Categorical   |

**Table: UserActivities**

| Column Name | Description                        | Feature Type  |
|-------------|------------------------------------|---------------|
| userID      | ID of the user                     | Categorical   |
| loginDate   | Date of user's last login          | DateTime      |
| friendCount | Number of friends of the user      | Numerical     |
| likesCount  | Number of posts the user has liked | Numerical     |
| postCount   | Number of posts made by the user   | Numerical     |

## **Questions:**

1. **SQL/Product Sense:** Given the vast amount of posts made daily, it is crucial for us to focus on the more influential or active users who might be spreading inappropriate content. Using the `ContentPosts` and `UserActivities` tables, can you write a SQL query to identify the top 5 users (by friend count) whose posts were flagged more than 5 times in the last month? Describe how this might help in identifying potential harmful spreaders of misinformation.


2. **Probability and Statistics:** Consider a scenario where a flagged post from a user triggers a review of the last 10 posts they've made. Assuming that each of their posts has a 5% independent chance of being inappropriate, what is the probability that at least 3 out of their last 10 posts are inappropriate? How does this insight influence how we should treat frequent violators of community standards?


3. **Machine Learning & Modeling:** The challenge of detecting inappropriate content is a classic problem of classification. Using the `ContentPosts` table, how would you design a machine learning model that predicts whether a post will be flagged? Describe the features you would extract, the model you would choose, and how you would validate its performance.


4. **Product Design & Analytics:** If we were to introduce a new user-reporting feature where users can report posts they find inappropriate, how would you measure its success? Furthermore, how would you determine if this feature reduces the workload of our automated content flagging system? Frame this in a potential A/B test scenario.
