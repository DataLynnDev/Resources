# **Business Problem Statement:**

The Marketing Channel Analysis team at Netflix is dedicated to understanding and optimizing the performance of various marketing channels including social media, email marketing, partnerships, and more. The goal is to drive more subscriptions and engagements, assess the return on investment (ROI) of each channel, and understand the user journey through different channels before they become subscribers. The new Data Analyst will play a crucial role in analyzing large sets of data to provide insights that will help in decision-making and strategic planning.

## **Data Tables:**

**Table: ChannelPerformance**

| Feature Name  | Feature Description                       | Feature Data Type | Comments       |
|---------------|-------------------------------------------|-------------------|----------------|
| channel_id    | Unique identifier for marketing channels  | int               | Primary Key    |
| channel_name  | Name of the marketing channel             | varchar           |                |
| date          | Date of the data record                   | date              |                |
| subscriptions | Number of subscriptions driven            | int               |                |
| engagements   | Number of engagements                     | int               |                |
| spend         | Amount spent on the channel               | int               |                |

**Table: UserJourney**

| Feature Name    | Feature Description                       | Feature Data Type | Comments       |
|-----------------|-------------------------------------------|-------------------|----------------|
| user_id         | Unique identifier for users               | int               | Primary Key    |
| channel_id      | Identifier for marketing channels         | int               | Foreign Key    |
| date            | Date of interaction                       | date              |                |
| interaction_type| Type of interaction (view, click, etc.)   | enum              | view, click    |

## **SQL Questions:**

1. **Operations:** Aggregation, Grouping, Joining

   **Scenario:**
   Understanding the effectiveness of different marketing channels is crucial. The number of subscriptions driven by each channel on a daily basis is a good indicator of performance.

   **Task:**
   Write a SQL query to find the total number of subscriptions driven by each marketing channel for each date. Order the result by date, then by channel_name.


2. **Operations:** Grouping, Calculations

   **Scenario:**
   Assessing the ROI of each marketing channel is essential to optimize the marketing budget. Calculating the cost per subscription can provide insights into the ROI.

   **Task:**
   Write a SQL query to calculate the cost per subscription for each marketing channel. Order the result by cost per subscription in descending order.

3. **Operations:** Joining, Calculations

   **Scenario:**
   Understanding the user journey through different channels before they become subscribers can provide insights into channel effectiveness at different stages.

   **Task:**
   Write a SQL query to find the total number of unique users and the total number of interactions for each marketing channel. Order the result by total number of interactions in descending order.

