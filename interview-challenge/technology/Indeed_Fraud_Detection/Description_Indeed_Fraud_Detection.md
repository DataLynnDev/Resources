# **Business Problem Statement**:
The primary aim at Indeed's Fraud Detection team is to ensure that the platform remains a reliable space for genuine job seekers and employers. With the vast number of job postings, fraudulent behavior can tarnish the credibility of the platform. The role of a data scientist in this team would be to use advanced data science techniques combined with domain knowledge to identify potentially fraudulent job postings and maintain the platform's credibility. The candidate's ability to understand, manipulate, and infer from large datasets will be paramount to success in this role.

## **Table Name: JobPostings**

| Column Name        | Description                                 | Feature Type     |
|--------------------|---------------------------------------------|------------------|
| JobID              | Unique Identifier for Each Job              | Numerical        |
| JobTitle           | Title of the Job Position                   | Categorical/Text |
| CompanyName        | Name of the Company Posting the Job         | Categorical/Text |
| DescriptionLength  | Number of Words in the Job Description      | Numerical        |
| PostedDate         | Date When the Job was Posted                | Date             |
| Salary             | Offered Salary for the Position             | Numerical        |
| ApplicationCount   | Number of Applications Received             | Numerical        |
| Category           | Job Category (e.g., IT, Finance)            | Categorical      |

**Table Name: UserActivities**

| Column Name   | Description                  | Feature Type     |
|---------------|------------------------------|------------------|
| UserID        | Unique Identifier for Each User | Numerical       |
| JobID         | Job they Interacted With     | Numerical        |
| ActivityDate  | Date of User Activity        | Date             |
| ActionType    | Type of Action (e.g., View, Apply) | Categorical  |


## **Questions**:

1. **SQL/Data Analysis**:
    *Scenario*: Some jobs seem to be attracting an unusually high number of applications within a short duration from being posted.
    - Using the `JobPostings` and `UserActivities` tables, identify job postings where the `ApplicationCount` within the first three days of posting exceeds the 95th percentile of application counts across all jobs in their respective `Category`. What patterns or insights can you infer from these listings?
    

2. **Probability and Statistics**:
    *Scenario*: Observing the `JobPostings` table, you notice that some job categories have a suspiciously high average salary offering.
    - Based on the `Category` and `Salary` columns in the `JobPostings` table, identify if any job category has an unusually high average salary. Explain your statistical approach and how you would validate if this is a genuine trend or potential fraud.
    

3. **Machine Learning & Modeling**:
    *Scenario*: In order to proactively detect potentially fraudulent postings, you decide to build a predictive model.
    - Using the features from the `JobPostings` table, build a model to predict the `ApplicationCount`. Clearly specify your target variable and its type. Additionally, discuss the reasoning behind the choice of your model, how you handled missing data, and any techniques you used to improve the model's accuracy.
    
4. **Progressive Question**:
    *Scenario*: With the insight from Question 1, you decide to delve deeper.
    - Based on the jobs identified in Question 1, use the `UserActivities` table to see if there are any patterns or anomalies in the user activities related to these jobs, especially around the `ActivityDate` and `ActionType`. This information can be vital in understanding user behavior and potentially spotting orchestrated fraudulent behavior.