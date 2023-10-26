# **Business Problem Statement**:
Determine the most effective segmentation for displaying targeted ads to Gmail users based on their email activity, preferences, and demographics to maximize relevancy and engagement while maintaining a positive user experience.

## **Data Tables**:

**Table 1: GmailUsers**

| Feature Name | Description                                                   | Data Type     | Comments                                 |
|--------------|---------------------------------------------------------------|---------------|-----------------------------------------|
| user_id      | Unique ID for each Gmail user                                 | int           | Primary Key                              |
| age          | Age of the user                                               | int           |                                         |
| gender       | Gender of the user                                            | enum          | Options: Male, Female, Other, Prefer not to say |
| country      | Country where user resides                                    | varchar(50)   |                                         |
| last_login   | Timestamp of the user's last login                            | datetime      |                                         |
| ad_pref      | User's preferred ad category                                  | varchar(50)   |                                         |

**Table 2: AdInteractions**

| Feature Name   | Description                                      | Data Type   | Comments                               |
|----------------|--------------------------------------------------|-------------|---------------------------------------|
| interaction_id | Unique ID for each ad interaction                 | int         | Primary Key                            |
| user_id        | Unique ID for each Gmail user                     | int         | Foreign Key references GmailUsers      |
| ad_category    | Category of the ad displayed                      | varchar(50) |                                       |
| clicked        | Indicates if the ad was clicked by the user       | enum        | Options: Yes, No                       |
| sentiment      | User feedback on ad relevancy (1 to 5, 5 being most relevant) | int        | Range: 1-5                             |

## **Questions**

**Question 1**:

**Topics and Operations**:
- Aggregation
- JOIN operation

**Scenario**:
To refine our ad targeting algorithm, we need to first understand user preferences by studying which ad categories are most clicked by different age groups.

**Task**:
Write an SQL query to find the top 3 ad categories for each ad categories based on the total number of clicks. Return the age, ad category, and total clicks for each category.

**Question 2**:

**Topics and Operations**:
- Aggregation
- Sub-query
- WHERE condition

**Scenario**:
User feedback is an integral part of refining our ad targeting mechanism. By understanding the sentiment scores across different ad categories, we can prioritize more relevant ad categories.

**Task**:
Write an SQL query to find ad categories with an average sentiment score less than 3. For these categories, return the ad category and the average sentiment score in descending order.

**Question 3**:

**Topics and Operations**:
- JOIN operation
- Conditional CASE statement
- Aggregation

**Scenario**:
To ensure user experience isn't hampered by the ads, it's important to study user sentiment based on their demographic details. This can aid in adjusting our ad display logic for specific segments.

**Task**:
Write an SQL query to find out the average sentiment score for each gender in every country. If the average sentiment is less than 3, label it as 'Low', if it's between 3 and 4, label it as 'Medium', and if it's greater than or equal to 4, label it as 'High'. Return the country, gender, average sentiment, and the sentiment label.
