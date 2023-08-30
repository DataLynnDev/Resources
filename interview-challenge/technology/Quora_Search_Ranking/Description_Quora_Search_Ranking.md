# **Business Problem Statement:**

Quora's search ranking algorithm needs continuous refinement to provide users with the most relevant and high-quality content. The quality of the search results is determined by various factors, such as the popularity of a question, its recency, the quality of answers, and user engagement. Your challenge is to refine and optimize the ranking algorithm based on the given data to enhance the user experience.

## **Data Table:**

**info_data**

| Column Name | Description                                  | Feature Type    |
|-------------|----------------------------------------------|-----------------|
| query_id    | Unique ID for the search query               | Categorical     |
| question_id | Unique ID for the returned question          | Categorical     |
| user_id     | ID of the user performing the search         | Categorical     |
| popularity  | Popularity score of the question (0 to 100)  | Numerical       |
| recency     | Days since the question was last updated     | Numerical       |
| answer_qual | Average quality rating of answers (0 to 10)  | Numerical       |
| user_engage | Average user engagement score (0 to 10)      | Numerical       |
| click_thru  | Whether the user clicked on the result (0/1) | Binary          |
| time_spent  | Time user spent on clicked question (in sec) | Numerical       |
| result_rank | Rank of the question in the search results   | Numerical       |

## **Questions:**

1. Quora has recently updated its UI, leading to a change in user behavior. Using the provided data, analyze if the recency of a question has a significant impact on the click-through rate (click_thru). Further, determine if this varies based on the quality of answers (answer_qual).


2. Quora believes that the engagement of a user with the platform can significantly influence the success of the search ranking algorithm. Can you develop a model predicting the click-through rate (click_thru) based on features such as popularity, recency, answer quality, user engagement, and time spent? Clearly state which feature is the target variable and its type.
    *Target Variable:* click_thru, *Type:* Binary

3. A recent update on Quora introduced a new feature where users can rate the quality of answers. Your task is to analyze if there's a correlation between user engagement (user_engage) and answer quality (answer_qual). If a significant correlation is found, would you recommend incorporating this feature as a key element in the search ranking algorithm? Why or why not?

4. Quora's engineers have a hypothesis that the top 3 search results (based on result_rank) garner the most user clicks irrespective of their actual relevance. Using the data, can you test this hypothesis? Further, if this is proven correct, how would you suggest modifying the ranking algorithm to ensure that relevance isn't overshadowed by mere ranking?
