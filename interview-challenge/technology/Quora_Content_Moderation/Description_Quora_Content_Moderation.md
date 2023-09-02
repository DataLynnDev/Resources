# **Business Problem Statement:**
To maintain the trust and integrity of content on Quora, it's crucial to identify and remove spam, plagiarized content, and potentially harmful advice. With the ever-increasing volume of user-generated content, automating this process becomes vital. The Content Moderation Team seeks to leverage data science to automate the early detection and filtering of inappropriate content. The primary goal is to create algorithms that recognize patterns consistent with spam, plagiarism, and harmful advice.


## **Data Tables:**

**UserPosts**

| Column Name  | Description                                           | Feature Type      |
|--------------|-------------------------------------------------------|-------------------|
| `post_id`    | Unique identifier for each post                       | Categorical       |
| `user_id`    | ID of the user who posted                             | Categorical       |
| `content`    | Text of the post                                      | Text              |
| `timestamp`  | Date and time of the post                             | DateTime          |
| `views`      | Number of views the post received                     | Numerical         |

**UserHistory**

| Column Name         | Description                                           | Feature Type      |
|---------------------|-------------------------------------------------------|-------------------|
| `user_id`           | ID of the user                                        | Categorical       |
| `num_posts`         | Total number of posts by the user                     | Numerical         |
| `num_flagged_posts` | Number of times user's posts were flagged             | Numerical         |

## **Questions:**

1. **Scenario**: Lately, there's been an uptick in potential spammy posts on the platform. Your initial hypothesis is that spam accounts often have a high post-to-flag ratio.
   
   *How would you statistically validate if there's a significant difference in the post-to-flag ratio between the general user population and those users whose posts get flagged more frequently?*
   
2. **Scenario**: You want to implement an algorithm that automatically identifies potentially harmful content based on historical data.

   *Given the `UserPosts` data, can you design a model that predicts whether a post is likely to be flagged as harmful? Clearly mention your target variable and its type.*
   

3. **Scenario**: After your model has been in production for a month, you notice that while it's good at catching harmful content, it's also flagging many benign posts, making the user experience less pleasant.

   *How would you approach this problem? Using the `UserPosts` table, propose a metric that can help gauge the accuracy and effectiveness of your content moderation model.*
   

4. **Scenario**: With the model in place, you also want to give users the power to report harmful content. However, not all users' reports are equally reliable.

   *Based on the `UserHistory` data, can you propose a way to weigh user reports based on their historical accuracy in flagging inappropriate content? This weighted score will then be used in conjunction with the model to make final decisions.*