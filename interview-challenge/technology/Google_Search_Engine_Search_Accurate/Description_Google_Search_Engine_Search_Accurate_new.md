## Business Problem Statement

Our team is continuously working on enhancing Google's Hummingbird algorithm to improve our search results. The primary goal of our team is to make Google Search more accurate, faster, and personalized. We have two main objectives in our upcoming initiative:

1. Analyze search query trends and patterns to understand user intent better.
2. Refine our search algorithm to understand the semantics of a search query better and match it with the most relevant webpages.

For these purposes, we've collected data related to search queries, user behavior, and webpage details.

## Data Tables

### Table 1: Search Queries (search_queries)

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| query_id | Unique identifier for the search query | Integer |
| user_id | Unique identifier for the user | Integer |
| search_text | Text entered by the user | String |
| timestamp | The date and time the search was made | Datetime |

### Table 2: Webpages (webpages)

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| webpage_id | Unique identifier for the webpage | Integer |
| url | The webpage URL | String |
| content | The textual content of the webpage | String |
| domain | The domain of the webpage | String |

### Table 3: User Clicks (user_clicks)

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| click_id | Unique identifier for the click | Integer |
| user_id | Unique identifier for the user | Integer |
| query_id | Unique identifier for the search query | Integer |
| webpage_id | The webpage clicked by the user for the query | Integer |
| timestamp | The date and time the click happened | Datetime |

## Questions

1. **(Data Manipulation & Cleaning)** The 'search_text' in the 'search_queries' table contains the raw search query data entered by the users. It may contain typos, irrelevant symbols, and stop words that might not contribute significantly to the semantics of the queries. How would you clean and pre-process this data to make it more suitable for further analysis?

2. **(Machine Learning & Modeling)** From the cleaned 'search_text', build a model to understand the semantics of the search queries (Hint: techniques like TF-IDF, word embeddings might be useful). How would you ensure that the model is accurately capturing the semantics? Use this model to identify the top 5 topics (or semantic themes) that users are searching for.


3. **(Probability and Statistics)** Based on the data provided and the model developed in question 2, can you estimate the probability that a randomly picked search query from a specific user (say, user_id = 100) would be about a particular topic (say, topic = "machine learning")? Explain your approach and any assumptions you've made.