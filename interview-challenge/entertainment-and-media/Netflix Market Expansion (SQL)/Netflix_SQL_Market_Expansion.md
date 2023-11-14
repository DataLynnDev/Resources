# **Business Problem Statement:**

Netflix is exploring opportunities to expand its market presence in the Asia-Pacific (APAC) region. The goal is to identify high potential areas based on various economic, demographic, and geographical factors. As a Data Analyst in the Market Expansion Analysis team, you will be required to analyze and provide insights on the available data to support data-driven decision-making for market expansion. Your analysis will aid in understanding the regional preferences, potential subscriber base, and economic feasibility to ensure a successful market penetration.

## **Data Tables:**

Table 1: `RegionalData`

| Feature Name | Brief Feature Description               | Feature Data Type | Comments                              |
|--------------|----------------------------------------|-------------------|---------------------------------------|
| region_id    | Unique identifier for each region      | int               | Primary Key                           |
| region_name  | Name of the region                     | varchar           |                                       |
| internet_penetration | Percentage of internet users    | float             | Range: 0 to 100                       |
| competitor_presence  | Presence of competitors (Yes/No)| enum              | Values: 'Yes', 'No'                   |
| avg_income   | Average income of the region's populace| int               |                                       |

Table 2: `ContentPreferences`

| Feature Name | Brief Feature Description               | Feature Data Type | Comments                              |
|--------------|----------------------------------------|-------------------|---------------------------------------|
| region_id    | Unique identifier for each region      | int               | Foreign Key, references RegionalData  |
| genre        | Preferred genre of content             | varchar           |                                       |
| avg_view_time| Average view time in hours             | float             |                                       |

## **SQL Questions:**

**Question 1:**

*Topics and Operations:* Aggregate Functions, Group By, Order By, Join Operations

*Scenario:*
Netflix wants to analyze the internet penetration and competitor presence in different regions to evaluate the initial conditions for market expansion.

*Task:*
Write a SQL query to find the total number of regions with and without competitor presence, along with the average internet penetration rate for both scenarios. Order the result based on the average internet penetration rate in descending order.

**Question 2:**

*Topics and Operations:* Sub-query, Having Clause

*Scenario:*
Based on the insights from the first question, Netflix is interested in understanding the content preferences in regions with high internet penetration and no competitor presence.

*Task:*
Write a SQL query to list the top 3 preferred genres in regions with internet penetration rate higher than 70% and no competitor presence. Provide the average view time for each genre.

**Question 3:**

*Topics and Operations:* Common Table Expressions (CTE), Case Statement, Window Function

*Scenario:*
Having understood the content preferences, Netflix now wants to correlate the average income of regions with the average view time of the top genre from the previous question to gauge the economic feasibility.

*Task:*
Write a SQL query to find the correlation between the average income of regions and the average view time of the top genre from the previous question. Divide the regions into three categories based on their average income: 'Low', 'Medium', and 'High'.