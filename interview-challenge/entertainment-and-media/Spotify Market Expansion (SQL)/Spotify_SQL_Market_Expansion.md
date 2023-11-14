# **Business Problem Statement:**
Spotify is planning to expand its services to new regions. The Market Expansion and User Growth Team is tasked with identifying potential regions for expansion based on current user listening habits, demographic segmentation, and competitor presence. The team needs to analyze the current data to find patterns and trends that can guide the expansion strategy.

**Data Tables:**

**Table: UserActivity**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| user_id      | Unique identifier for each user | int | Primary Key |
| song_id      | Unique identifier for each song | int | |
| listen_date  | Date when the user listened to the song | date | |
| region       | Region where the user is from | varchar | |
| age_group    | Age group of the user | enum | Options: '18-24', '25-34', '35-44', '45-54', '55+' |

**Table: CompetitorPresence**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| region       | Region name | varchar | Primary Key |
| competitor_count | Number of competitors in the region | int | |

## Questions:

**Question 1:**
- *Topics and Operations:* Geospatial analysis, demographic segmentation (from "Sellers With No Sales" and "Confirmation Rate")
- *Scenario:* Before expanding to a new region, it's crucial to understand the user demographics and their listening habits. This will help in tailoring the marketing strategies for the target audience.
- *Task:* Write an SQL query to find the top 3 regions with the highest number of users in the age group '18-24' who have listened to more than 10 unique songs in Sep. 2023.


**Question 2:**
- *Topics and Operations:* Geospatial analysis, competitor analysis (from "Leetcodify Friends Recommendations" and "Sellers With No Sales")
- *Scenario:* Competitor presence in a region can influence Spotify's decision to expand. It's essential to understand regions where competitors are less, but user activity is high.
- *Task:* Write an SQL query to identify regions where the competitor count is less than 3, but the total number of unique songs listened to by users in Sep. 2023 is more than 100.


**Question 3:**
- *Topics and Operations:* Demographic segmentation, international markets (from "Confirmation Rate" and "Leetcodify Friends Recommendations")
- *Scenario:* Different age groups have varied music preferences. Identifying songs popular among specific age groups can help in curating playlists for marketing campaigns.
- *Task:* Write an SQL query to find the top 5 most listened to songs in the age group '25-34' in Sep. 2023. The result should also display the total number of times each song was listened to by this age group.