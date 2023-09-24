# **Business Problem Statement:**
With the ongoing efforts of Facebook Community Integrity & Content Moderation team, our primary aim is to maintain the quality and credibility of the content on the platform. As Facebook continues to grow with billions of daily active users, it becomes crucial for us to efficiently identify and moderate inappropriate content while ensuring legitimate content remains unaffected. The challenge is to analyze the existing data, draw patterns, and come up with insights that can assist in refining our content moderation algorithms.

## **Data Tables**:

**Table 1: UserReports**

| Column Name | Description                                        | Feature Type |
|-------------|----------------------------------------------------|--------------|
| report_id   | Unique ID for the report                           | Numeric      |
| user_id     | ID of the user who reported                        | Numeric      |
| content_id  | ID of the content being reported                   | Numeric      |
| reason      | Reason for the report (e.g., Hate Speech, Spam)   | String       |
| timestamp   | Timestamp of the report                            | Date-Time    |

**Table 2: ContentModeration**

| Column Name   | Description                                           | Feature Type |
|---------------|-------------------------------------------------------|--------------|
| content_id    | Unique ID for the content                             | Numeric      |
| is_inappropriate | Flag indicating if the content was inappropriate (0 or 1) | Binary      |
| reviewed_by  | ID of the moderator who reviewed the content         | Numeric      |
| review_timestamp | Timestamp of when the content was reviewed         | Date-Time    |

## Questions:

1. **Question 1 - Data Cleaning & Exploration**

**Scenario:**
During the data preparation phase, you observed that there might be some inconsistencies and missing data within the 'UserReports' table which could affect the quality of the analysis.

**Task:**
Clean the 'UserReports' table by handling any missing values, identifying and addressing outliers in the 'timestamp' column, and ensuring all timestamps follow a unified date format (YYYY-MM-DD HH:mm:ss).


2. **Question 2 - SQL Queries**

**Scenario:**
You are interested in analyzing the patterns of user reports and how they correlate with the actual content that was flagged as inappropriate.

**Task:**
Using the 'UserReports' and 'ContentModeration' tables, write an SQL query to retrieve the 'reason' for reports, count of those reasons, and the percentage of those reported contents that were actually found inappropriate. Ensure to handle instances where content may have been reported multiple times for different reasons. Order the results by the count of reports in descending order.

3. **Question 3 - Probability and Statistical Analysis**

**Scenario:**
Given the massive influx of reports and moderated content, you're interested in understanding the variability in the number of reports received daily.

**Task:**
Calculate the sample mean and variance of daily reports using data from the 'UserReports' table.

4. **Question 4 - Product & Business Sense**

**Scenario:**
After implementing new features in the Facebook content moderation system, you want to ensure they are positively impacting the platform's community integrity.

**Task:**
Design a metric or set of metrics that would help you measure the success of these newly implemented features in the moderation system. Discuss how you'd use the available data to inform decisions about potential monetization strategies or user recommendations based on their interaction with moderated content.
