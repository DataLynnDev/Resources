
# Business Problem Statement:
Facebook News is focused on delivering high-quality news articles to users and aims to increase user engagement, retention, and overall satisfaction. The challenge is to analyze user interactions, content performance, and engagement patterns to optimize content recommendations, identify areas for improvement, and assess the impact of newly introduced features. The questions in this data challenge will require the candidate to leverage data manipulation, probability and statistics, machine learning, and product design & analytics skills to address the identified issues.

## Data Table:
| Column Name          | Description                                 | Feature Type      |
|----------------------|---------------------------------------------|-------------------|
| user_id              | Unique identifier for each user             | Categorical       |
| article_id           | Unique identifier for each news article     | Categorical       |
| interaction_type     | Type of interaction (e.g., view, like)      | Categorical       |
| interaction_date     | Date of the interaction                     | Date              |
| time_spent           | Time spent on the article in seconds        | Numeric           |
| category             | Category of the news article (e.g., Sports) | Categorical       |
| user_country         | Country code of the user                    | Categorical       |
| engagement_score     | Calculated engagement score for the user    | Numeric           |
| article_publish_date | Publication date of the article             | Date              |
| author_id            | Unique identifier for the article author    | Categorical       |

## Questions:

1. You're interested in analyzing user interactions across different countries. Given the `user_country`, `interaction_type`, and `engagement_score` columns, write an SQL query to find the total count of interactions and average engagement score, grouped by `user_country`. Provide insights into how this information can be leveraged to increase global reach.

2. Facebook News is planning to introduce a subscription model. Given the engagement patterns in the `engagement_score` and `time_spent` columns, calculate the expected revenue if 5% of the users with an engagement score above a certain threshold subscribe. Then, compute the probable loss if the feature fails to attract new subscribers. How would you optimize the threshold to balance the risk and revenue?

3. Based on user interactions with articles (using columns `user_id`, `article_id`, `time_spent`, `category`, and `user_country`), build a recommendation model to suggest articles to users. Explain how the model will be evaluated and how it aligns with the overall business goal of increasing engagement.


