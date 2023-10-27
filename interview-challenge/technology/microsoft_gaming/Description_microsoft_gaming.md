# **Business Problem Statement:**
As the gaming industry continues to grow, understanding player behavior becomes crucial for Microsoft's Gaming team. The team aims to enhance player experience, increase in-game purchases, and ensure higher engagement levels. To achieve this, the team needs insights into player preferences, their in-game purchase patterns, and the factors influencing their engagement. The data analyst's role will be to derive these insights using SQL operations on the available gaming data.

## **Data Tables:**

**Table: PlayerData**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| player_id    | Unique ID for each player | int | Primary Key |
| region       | Region where the player is from | enum | Options: NA, EU, ASIA, SA |
| age_group    | Age group of the player | enum | Options: <18, 18-24, 25-34, 35+ |
| last_login   | Last date the player logged in | date |  |
| total_spent  | Total amount spent by the player in-game | float |  |

**Table: GameActivity**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| activity_id  | Unique ID for each activity | int | Primary Key |
| player_id    | ID of the player | int | Foreign Key (references PlayerData.player_id) |
| game_id      | ID of the game played | int |  |
| hours_played | Number of hours played in a session | float |  |
| in_game_purchase | Amount spent in-game during the session | float |  |
| date_played  | Date of the gaming session | date |  |

## Questions:

**Question 1:**

*Topics and Operations:* Aggregation, Filtering

*Scenario:* The marketing team wants to target players from the ASIA region who have not logged in for the last 30 days for a re-engagement campaign.

*Task:* Find the total number of players from the ASIA region who have not logged in for Sep. 2023.

**Question 2:**

*Topics and Operations:* Grouping, Joining Tables

*Scenario:* The game development team is interested in understanding which age group spends the most in-game to tailor their future game designs.

*Task:* Calculate the average in-game purchase amount for each age group. Order the results by the average purchase amount in descending order.

**Question 3:**

*Topics and Operations:* Subquery, Aggregation, Filtering

*Scenario:* The team is planning to introduce a new game and wants to identify potential players who are highly engaged and have a history of spending in other games.

*Task:* Identify players who have played more than 50 hours in total and have an average in-game purchase of more than $15 across all their sessions. Return their player_id, total hours played, and average in-game purchase.
