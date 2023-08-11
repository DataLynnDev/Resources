**Business Problem Statement:**

As a data scientist in the Search Engine, PageRank Algorithm team at Google, your role is to help improve the efficiency and accuracy of our search engine results. We have noticed that despite our current PageRank algorithm, some less relevant pages are still appearing in the top results. Your task is to analyze the current situation, identify the causes of this issue, and propose solutions to improve the ranking of search results.

**Data Tables:**

1. **Table: WebPages**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| page_id | Unique identifier for each webpage | Integer |
| page_content | Text content of the webpage | String |
| page_links | List of page_ids that this page links to | List of Integers |
| page_rank | Current PageRank score of the webpage | Float |

2. **Table: SearchQueries**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| query_id | Unique identifier for each search query | Integer |
| query_text | Text of the search query | String |
| clicked_page_ids | List of page_ids that were clicked on for this query | List of Integers |

**Questions:**

1. **Data Manipulation & Cleaning question:** Given the `WebPages` table, identify any pages that have unusually high PageRank scores but have very few inbound links (i.e., not many other pages link to them). What could be causing these anomalies, and how would you propose to handle them?

   *Topic: Window function and group by, Data manipulation*

2. **Probability and Statistics question:** Using the `SearchQueries` table, calculate the probability that a page with a PageRank score in the top 10% gets clicked on when it appears in the search results. How does this compare to the click probability for pages with lower PageRank scores?

   *Topic: Basic statistics, statistical sampling, Probability distribution*
   

3. **Product Design & Analytics question:** Suppose you propose a modification to the PageRank algorithm to address the issues identified in Question 1. How would you design an A/B test to evaluate the effectiveness of your proposed changes? What metrics would you use, and how would you interpret the results?

   *Topic: Bias in AB testing, Inference from data, Metric selection*
