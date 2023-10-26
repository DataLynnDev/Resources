# **Business Problem Statement:**

Google is keen to understand the efficiency of search personalization for users. As a data analyst in the Google Search Personalization team, your role is to identify patterns and insights from users' search behavior to determine the effectiveness of the personalization rules and to ensure that the tailored search results cater to individual user preferences, while maintaining strict adherence to user privacy.

## **Data Tables**:

**Table: UserSearches**

| Feature Name | Description                              | Data Type | Comments |
|--------------|------------------------------------------|-----------|----------|
| user_id      | Unique identifier for each user          | int       | PK       |
| search_query | The actual search query                  | varchar   |          |
| search_date  | Date when the search was made            | date      |          |
| click_link   | The link clicked after the search        | varchar   |          |
| click_date   | Date when the link was clicked           | date      |          |
| session_id   | Unique identifier for a user's session   | int       |          |

**Table: UserProfiles**

| Feature Name | Description                                 | Data Type | Comments |
|--------------|---------------------------------------------|-----------|----------|
| user_id      | Unique identifier for each user             | int       | PK, FK   |
| preference   | The user's general search preference        | varchar   |          |
| last_active  | Date when the user was last active          | date      |          |
| privacy_mode | Whether user has turned on privacy mode     | enum      | Options: On, Off |

## **SQL Questions**:

1. **Topics and Operations:** Aggregate Functions, JOIN, WHERE
   - **Scenario:** Google is interested in identifying the most popular search queries for users who have their privacy mode turned off. This will help in refining the personalization rules.
   - **Task:** Find the top 3 most searched queries and their respective counts from users who have their privacy mode turned off.

2. **Topics and Operations:** Common Table Expressions (CTE), Aggregate Functions, JOIN, WHERE, ORDER BY
   - **Scenario:** Google wants to measure the effectiveness of search personalization by looking at the number of clicks after a search. The time taken to click after a search can be an indicator of how relevant the search results were to the user.
   - **Task:** Using a Common Table Expression (CTE), calculate the average time (in days) taken by users to click on a link after making a search, and order the result by search preference.

3. **Topics and Operations:** Subqueries, Aggregate Functions, JOIN, GROUP BY, HAVING
   - **Scenario:** Google is interested in understanding the behavior of users who are consistently active. By understanding the behavior of users who search frequently, Google can refine its personalization rules.
   - **Task:** Identify users who have made searches on at least 5 different days in Sep. 2023 and calculate their average number of searches per day. Also, return the user's search preference from the UserProfiles table.