# **Business Problem Statement:**
Google's PageRank algorithm is a cornerstone of its search engine capabilities. As part of the PageRank team, the data analyst is responsible for ensuring that the algorithm is performing optimally and that user interactions with search results are positive. The team has recently made some updates to the algorithm and needs to understand its impact on user behavior, especially in terms of click-through rates and bounce rates. The goal is to identify any anomalies or significant changes in user interactions post-update and provide insights to refine the algorithm further.

## **Data Tables:**

**Table: SearchResults**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| search_id    | Unique identifier for each search query | int | Primary Key |
| query        | The search query entered by the user | varchar | |
| result_url   | The URL of the search result | varchar | |
| rank         | The rank of the search result (1 being the top, range from 1-5) | int | |
| click        | Whether the result was clicked (1 for yes, 0 for no) | enum | Options: 0, 1 |
| bounce       | Whether the user quickly returned after clicking (1 for yes, 0 for no) | enum | Options: 0, 1 |

**Table: UserBehavior**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| search_id    | Unique identifier for each search query | int | Foreign Key (references SearchResults.search_id) |
| user_id      | Unique identifier for each user | int | |
| session_time | Duration of the user's session in seconds | int | |
| region       | The geographical region of the user | varchar | |

## Questions

1. **Question 1:**

*Scenario:* After the recent update to the PageRank algorithm, the team wants to understand the average session time of users who clicked on the top 3 search results. This will help gauge if users are finding the top results relevant.

*Task:* Write an SQL query to calculate the average session time of users who clicked on search results ranked 1 to 3. Group the results by the rank of the search result.


2. **Question 2:**

*Scenario:* The team is interested in understanding sequences of searches where users consecutively clicked on the top result but then bounced back. Identifying such sequences can help in refining the algorithm to reduce such bounce rates.

*Task:* Write an SQL query to identify search_ids where users clicked on the top-ranked result (rank = 1) and then bounced back in their next search. Return the search_ids in ascending order.


3. **Question 3:**

*Scenario*: The PageRank team has observed that users from different geographical regions interact differently with search result rankings. While some regions might predominantly click on top-ranked results, others might interact more with lower-ranked results. To optimize the algorithm for each region, it's essential to understand the popularity of each rank across different regions.

*Task*: Write an SQL query to pivot the combined data of SearchResults and UserBehavior tables. For each geographical region, the output should provide aggregated data on the number of clicks for each search result rank (e.g., Rank1_Clicks, Rank2_Clicks, ...). The output headers should start with 'Region', followed by respective columns for each rank.
