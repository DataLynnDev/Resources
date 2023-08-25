# **Business Problem Statement**:
Microsoft Teams seeks to improve the efficiency and user satisfaction of its third-party integrations. Understanding user interactions and feedback can provide insights to refine these integrations.

## **Data Tables**:

| Tables     | Column Name         | Description                                                         | Feature Type          |
|------------|---------------------|---------------------------------------------------------------------|-----------------------|
| Integrations| Integration_ID     | Unique ID for each integration                                      | Categorical           |
| Integrations| Integration_Name   | Name of the third-party service                                     | Categorical           |
| Integrations| Monthly_Users      | Number of users accessing the integration monthly                   | Numeric               |
| UserInteractions| User_ID        | Unique ID for each user                                             | Categorical           |
| UserInteractions| Interaction_TimeStamp | Time of interaction with a third-party service            | DateTime              |
| UserInteractions| Integration_ID | ID of the integration the user interacted with                       | Categorical (FK)      |
| UserInteractions| Feedback_Score | User's feedback score on the integration (1-5)                       | Numeric               |

## **Questions**:

1. **Data Manipulation & Cleaning**:
    - Using the Integrations table, detect and replace any potential empty cells in the Monthly_Users column with the median value of that column. Identify potential anomalies in the Monthly_Users column based on statistical measures.


2. **Machine Learning & Modeling**:
    - Leveraging both the Integrations and UserInteractions tables, propose a strategy to predict if an integration will receive an average feedback score above 4 in the upcoming month. Discuss potential challenges of unbalanced data and how techniques like bagging or boosting might assist.


3. **Product Design & Analytics**:
    - Observing the UserInteractions table, design a hypothetical experiment to enhance user experience. Outline how you'd implement an A/B test to measure the success of this experiment.