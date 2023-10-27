# **Business Problem Statement:**
The Digital Transformation team at Microsoft has been working on various projects to integrate digital technology into different areas of the business. As a data analyst, your role is to analyze the success rates of these projects, gather user feedback, and monitor adoption rates. This will help in refining training materials, optimizing change management strategies, and making informed decisions on tool selection. To assess your SQL skills in relation to this role, you will be provided with a set of data tables and questions related to our digital transformation projects.

## **Data Tables:**

**Table: Projects**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| project_id   | Unique identifier for each project | int | Primary Key |
| project_name | Name of the digital transformation project | varchar |  |
| start_date   | Start date of the project | date |  |
| end_date     | Expected end date of the project | date |  |
| status       | Current status of the project | enum | Options: 'Ongoing', 'Completed', 'On Hold', 'Cancelled' |

**Table: UserFeedback**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| feedback_id  | Unique identifier for each feedback | int | Primary Key |
| project_id   | Identifier for the project the feedback is related to | int | Foreign Key referencing Projects.project_id |
| user_id      | Identifier for the user giving the feedback | int |  |
| feedback     | Detailed feedback from the user | varchar |  |
| rating       | Rating given by the user for the project (1 to 5) | int |  |

## Questions

**Question 1:**

*Topics and Operations:* GROUP BY, COUNT

*Scenario:* As part of the Digital Transformation team, you want to identify projects that might need more attention based on user feedback.

*Task:* List all projects that have received more than 3 feedback entries with a rating of 2 or less.

**Question 2:**

*Topics and Operations:* AVG, HAVING

*Scenario:* The team wants to prioritize projects based on average user ratings to allocate resources effectively.

*Task:* Find all projects with an average rating less than 3.5 and list them in descending order of their average rating. Include the project name and the average rating in the result. (limit the output to 5 rows)

**Question 3:**

*Topics and Operations:* DATE FUNCTIONS, COUNT

*Scenario:* The management is interested in understanding the feedback trend for ongoing projects in the first half year in 2023.

*Task:* List all ongoing projects that started within the last 6 months and count the number of feedback entries they have received during this period. Include the project name and feedback count in the result.