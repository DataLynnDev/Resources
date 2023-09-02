# **Business Problem Statement:**
Oracle's Database Management System is pivotal in supporting various businesses, and its performance and utility are of utmost importance. Recently, with the rise of online businesses and new-age technology, there has been an increase in database requests from eCommerce platforms. Oracle wishes to optimize the database to handle these requests more efficiently. For this, Oracle requires insights on how eCommerce platforms interact with its database, the types of requests, the intensity, and frequency of these requests, and any patterns or trends. The goal is to enhance user experience, minimize downtime, and maximize efficiency.

## **Data Tables**

**Data Table 1: `Requests`**

| Column Name | Description                                      | Feature Type |
|-------------|--------------------------------------------------|--------------|
| Request_ID  | Unique Identifier for each request               | Numeric      |
| Time_Stamp  | The time the request was made                    | DateTime     |
| Website     | The eCommerce platform making the request        | Categorical  |
| Query_Type  | Type of database query (e.g., SELECT, UPDATE)    | Categorical  |
| Duration    | Time taken for the query to execute (in seconds) | Numeric      |
| Response    | Whether the query was successful or failed       | Categorical  |

**Data Table 2: `eCommerce_Info`**

| Column Name | Description                       | Feature Type |
|-------------|-----------------------------------|--------------|
| Website     | The eCommerce platform's name     | Categorical  |
| User_Base   | Number of active users on platform| Numeric      |
| Avg_Queries_Day | Average queries per day        | Numeric      |
| Peak_Hours  | Time period with most queries     | Categorical  |

## **Questions:**

1. **Scenario:** The eCommerce platforms vary in their user bases, potentially leading to varying levels of requests to Oracle's Database. By understanding the request patterns, Oracle can better manage resources.
   * Extract features from the `Requests` and `eCommerce_Info` tables to determine the relationship between the user base of an eCommerce platform and the average duration of its requests. Do larger platforms generate longer request times?

2. **Scenario:** During peak hours, databases are more likely to be strained. We need to understand if certain websites intensify this strain.
   * Analyze the data to identify if there's a correlation between the peak hours of the highest user-base platforms and increased request durations. Is Oracle's database slower during these peak times?

3. **Scenario:** Oracle is curious about the distribution of query types among different platforms.
   * Using statistical methods, analyze the `Query_Type` distribution among the top 5 eCommerce platforms by user base. Are certain query types predominant among larger platforms? (please use SQL to answer this question)


4. **Scenario:** Improving the response rate is crucial for enhancing user experience. We suspect that certain types of queries might be more prone to failures.
   * Build a model using data from the `Requests` table to predict the `Response` based on other features. Which features are most influential in predicting a successful or failed query?
   * Mark: `Response` as the target variable.