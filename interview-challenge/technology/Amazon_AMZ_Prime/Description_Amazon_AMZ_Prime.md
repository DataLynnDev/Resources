# **Business Problem Statement**:

Given the competitive landscape of streaming services and increased logistical challenges due to global disruptions, there is a need for Amazon Prime to optimize its content offerings and streamline its delivery system for higher customer satisfaction. Specifically, Amazon Prime needs to identify which genres/categories of content are more popular among users to curate better content in Prime Video and Music. Simultaneously, it must also understand the factors influencing delivery delays, allowing Amazon to reduce shipping times.

## **Data Tables**:
1. **Table Name**: `Prime_Content_Usage`

| **Column Name** | **Description** | **Type** |
|------------------|-------------|---------------|
| userID | Unique identifier for the user | Integer |
| contentID | Unique identifier for the content | Integer |
| contentType | Type of content (Video, Music) | String |
| genre | Genre of the content | String |
| viewDuration | Duration content was viewed/listened | Float |
| watchDate | Date when the content was accessed | Date |

2. **Table Name**: `Prime_Deliveries`

| **Column Name** | **Description** | **Type** |
|------------------|-------------|---------------|
| orderID | Unique identifier for the order | Integer |
| userID | Unique identifier for the user | Integer |
| orderDate | Date of order placement | Date |
| deliveryDate | Expected delivery date | Date |
| actualDeliveryDate | Actual delivery date | Date |
| delayReason | Reason for delivery delay, if any | String |

## **Questions**:

1. **Question 1: Data Cleaning & Exploration**

**Scenario**: We've received the `Prime_Content_Usage` table from a new source. Before any in-depth analysis, it's vital to ensure that the data's quality meets Amazon's standards.

a) Identify any missing values in the `Prime_Content_Usage` table.

b) Explore and handle outliers in the `viewDuration` column.

c) Ensure that the `watchDate` column follows a unified date format.

2. **Question 2: SQL Queries**

**Scenario**: The Amazon Prime executive team is keen on understanding user preferences to curate content better. Using the `Prime_Content_Usage` table:

a) Identify the top 3 most popular genres among users in the last 6 months.

b) For each genre, determine the average `viewDuration`.

c) Using a subquery, find out how many unique users accessed content more than 10 times in the last month.

3. **Question 3: Probability and Statistical Analysis**

**Scenario**: Amazon Prime is exploring the likelihood of delivery delays based on historical data to anticipate and mitigate any future challenges.

a) Using the `Prime_Deliveries` table, determine the probability distribution of `delayReason`.

b) Calculate the average delay time when the `delayReason` is "Weather disruptions".

c) Implement the above calculation using a coding language of your choice to obtain the result.

4. **Question 4: Product & Business Sense**

**Scenario**: With the insights you've gathered from both the `Prime_Content_Usage` and `Prime_Deliveries` tables:

a) Propose a data-driven strategy to improve content curation for Prime Video and Music.

b) Recommend steps to alleviate common reasons for delivery delays, ensuring expedited shipping for Prime users.