# **Business Problem Statement:**

As part of Google's Semantic Search team, we are continually working to enhance the understanding of user queries, ensuring we provide the most relevant and accurate search results. One key aspect of this is understanding the semantics or meaning of search queries. In recent times, we have observed anomalies in the search results quality for a subset of queries, potentially impacting user satisfaction and engagement. The task is to identify the possible cause of these anomalies and suggest improvements to enhance the overall user experience and satisfaction.

## **Data tables:**

**1. Query_Data Table**

| Column Name | Description                       | Data Type |
|-------------|-----------------------------------|-----------|
| query_id    | Unique identifier for each query  | Integer   |
| user_id     | Unique identifier for each user   | Integer   |
| query       | The text of the search query      | String    |
| timestamp   | The time when the query was made  | Datetime  |
| result_rank | Rank of the results shown to user | Integer   |
| clicked     | If the result was clicked or not  | Boolean   |

**2. User_Feedback Table**

| Column Name | Description                             | Data Type |
|-------------|-----------------------------------------|-----------|
| user_id     | Unique identifier for each user         | Integer   |
| query_id    | Unique identifier for each query        | Integer   |
| rating      | User's rating for the query (1 to 5)    | Integer   |
| feedback    | User's textual feedback for the query   | String    |

## **Questions:**

1. **(Data Manipulation & Cleaning)** Using the `Query_Data` table, calculate the click-through rate (CTR) for each query. The CTR is defined as the number of clicks divided by the total number of queries. How does the CTR vary across different result ranks?

2. **(Probability and Statistics)** From the `User_Feedback` table, calculate the average rating for each query. Given that a user is dissatisfied if their rating is 2 or less, calculate the probability that a user is dissatisfied given that the result rank was higher than 5.

3. **(Machine Learning & Modeling)** Build a predictive model using the `Query_Data` and `User_Feedback` tables that predicts user dissatisfaction based on query characteristics and user interaction data. What are the key features contributing to user dissatisfaction?

4. **(Product Design & Analytics)** Assuming that changes were made to the semantic search algorithm and then tested, how would you determine if these changes resulted in a statistically significant improvement in user satisfaction? Proposed an experiment using the `Query_Data` and `User_Feedback` tables to evaluate this.