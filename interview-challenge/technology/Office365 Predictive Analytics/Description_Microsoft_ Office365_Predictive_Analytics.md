# **Business Problem Statement**:
As Microsoft continues to develop its productivity tools within Office 365, the Predictive Analytics team has been tasked to enhance the functionality of Excel to better anticipate user needs. The goal is to utilize historical user interaction data with Excel to provide better suggestions for data entry, chart types, and even auto-complete functions. To ensure the effectiveness of these predictive models, data related to users' behavior and interactions, as well as the data they input into Excel sheets, needs to be analyzed thoroughly.

## **Data Table:**
**UserInteractions**

| Column Name | Description                                           | Feature Type  |
|-------------|-------------------------------------------------------|---------------|
| userID      | Unique identifier for the user                        | Categorical   |
| sessionID   | Unique identifier for the user's Excel session        | Categorical   |
| actionType  | Type of action (data entry, select chart, auto-fill)  | Categorical   |
| inputData   | Data entered by the user                              | Numerical     |
| timeSpent   | Time (in seconds) user spent on action                | Numerical     |
| suggestedChart | Chart type suggested by Excel                       | Categorical   |

**UserFeedback**

| Column Name | Description                                           | Feature Type  |
|-------------|-------------------------------------------------------|---------------|
| userID      | Unique identifier for the user                        | Categorical   |
| sessionID   | Unique identifier for the user's Excel session        | Categorical   |
| feedback    | User rating on suggestions (1-5 scale)                | Numerical     |
| comments    | Free text comments provided by the user               | Text          |

## **Questions**:

1. **Data Manipulation & Cleaning**:
   - From the `UserInteractions` table, identify sessions where users utilized the auto-fill function more than three times. How many such sessions exist?

2. **Probability and Statistics**:
   - Given a random session from the `UserInteractions` table, compute the probability that the `suggestedChart` was a bar chart and the user spent more than 30 seconds on selecting it.

3. **Machine Learning & Modeling**:
   - Using the `UserFeedback` table, build a regression model to predict 'feedback' based on the timeSpent and actionType from the `UserInteractions` table. Indicate which is the target variable.
   - **Target Variable**: feedback

4. **Product Design & Analytics**:
   - Imagine Excel is introducing a new predictive feature to suggest the best chart type for a given dataset. Based on the `UserInteractions` and `UserFeedback` tables, propose a recommendation system design to ensure that the most appropriate chart suggestions are made for user datasets.


