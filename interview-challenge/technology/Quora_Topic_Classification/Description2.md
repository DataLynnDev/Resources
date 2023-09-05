# **Business Problem Statement**:

As the number of questions on Quora grows exponentially, there's a growing need to efficiently categorize new questions into topics. This will not only aid in content discoverability but also increase user engagement. The key is to develop machine learning models that can predict the right topics for incoming questions. However, before deploying a model, it's essential to validate its efficiency and understand the product implications.


## **Data Table**:

**info_data**

| Column Name   | Description                           | Feature Type   |
|---------------|---------------------------------------|----------------|
| question_id   | Unique identifier for the question    | Categorical    |
| question_text | Text of the question asked            | Text           |
| user_activity | User's recent activity frequency      | Numeric        |
| topic_id      | ID of the topic assigned (historical) | Categorical    |
| question_age  | Time since question was posted        | Numeric        |
| upvotes       | Number of upvotes for the question    | Numeric        |
| downvotes     | Number of downvotes for the question  | Numeric        |
| user_id       | User who posted the question          | Categorical    |
| user_interest | List of topics user is interested in  | Text           |
| feedback      | Feedback on topic assignment          | Categorical    |


## **Questions**:

1. **Scenario**: You've observed that the distribution of upvotes and downvotes varies significantly across various topics. Given the `question_text`, `upvotes`, `downvotes`, and `topic_id`, can you develop a model to predict if a question belongs to a high upvote-to-downvote ratio topic or not? Remember, this could help in determining which topics generally receive positive reception.
   
   **Target Variable**: High upvote-to-downvote ratio (Binary: Yes/No)
   
2. **Scenario**: User feedback on the relevance of topic assignment has been collected. This feedback is essential to understanding any discrepancies in the machine learning model's topic predictions versus the user's perception. Using the `question_text`, `topic_id`, and `feedback`, can you identify any patterns or topics that consistently receive negative feedback? What statistical test would you use to confirm any observed discrepancy between topics?


3. **Scenario**: Quora has just implemented a new version of the topic classification model. Before a full rollout, they wish to test its efficiency on a smaller group of active users. Given the `user_activity`, `user_id`, and `feedback`, can you devise an A/B test plan to compare the performance of the new model versus the old one? Also, based on this sample, what metrics would be most relevant to gauge the success of the new model?


4. **Scenario**: There are concerns that recent questions might be categorized into topics too hastily, potentially leading to incorrect categorizations. Using the `question_age` and `feedback`, can you analyze if the feedback deteriorates for newer questions as compared to older ones? Based on this, can you suggest any improvements to the "Related Questions" suggestion process?