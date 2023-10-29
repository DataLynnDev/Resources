# **Business Problem Statement:**
Spotify's Advertising and Monetization Team is keen on optimizing its advertising campaigns. With the increasing number of users, it's crucial to understand user behavior, segment them appropriately, and target ads for maximum effectiveness. The team is looking to evaluate the performance of ads, measure click-through rates, and assess the effectiveness of different advertising campaigns. They also aim to segment the user base for more targeted advertising.

## **Data Tables:**

**Table: UserActivity**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| user_id      | Unique identifier for each user | int | Primary Key |
| session_id   | Unique identifier for each session | int |  |
| ad_id        | Identifier for the ad displayed | int | Foreign Key (References AdDetails) |
| click        | Whether the ad was clicked (1 if clicked, 0 otherwise) | enum | Options: 0, 1 |
| session_date | Date of the session | date |  |

**Table: AdDetails**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|----------|----------|
| ad_id        | Unique identifier for each ad | int | Primary Key |
| campaign_id  | Identifier for the advertising campaign | int |  |
| ad_duration  | Duration of the ad in seconds | int |  |
| ad_type      | Type of the ad (e.g., video, banner) | enum | Options: video, banner |

## Questions:

**Question 1:**
- *Topics and Operations:* Delete Duplicate Entries
- *Scenario:* Over time, some ads might have been mistakenly entered multiple times into the AdDetails table. Before analyzing the effectiveness of each ad, we need to ensure that our data is clean and free from duplicates.
- *Task:* Write an SQL query to delete duplicate ads from the AdDetails table, keeping only the ad with the smallest ad_id.

**Question 2:**
- *Topics and Operations:* Aggregate Functions and Filtering
- *Scenario:* The team wants to evaluate the effectiveness of ads based on their click-through rates. However, they are particularly interested in ads that have been shown multiple times but have a low click-through rate.
- *Task:* Write an SQL query to find the total number of times each ad was displayed and the number of times it was clicked. Filter out ads that have been displayed less than 10 times. Return the ad_id, total displays, and total clicks, ordered by the number of clicks in ascending order.

**Question 3:**
- *Topics and Operations:* Joining Tables and Date Functions
- *Scenario:* The team is planning a new advertising campaign for the next year. For this, they want to analyze the performance of ads from different campaigns over the past year.
- *Task:* Write an SQL query to find the total number of clicks each ad received in the past year, along with its type and duration. Return the ad_id, ad_type, ad_duration, and total clicks, ordered by total clicks in descending order.
