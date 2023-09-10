# **Business Problem Statement:**

Adobe's Customer Journey Analytics team seeks to optimize the customer experience across various touchpoints in their journey. Our goal is to better understand drop-off points, predict potential drop-offs, and provide actionable insights to enhance the customer's overall experience. For this purpose, we've collected data from various sources, providing insights into the user's actions, preferences, and feedback.


## **Data Tables**:

**Table 1: UserActions**

| Column Name  | Description                                          | Feature Type   |
|--------------|------------------------------------------------------|----------------|
| `UserID`       | Unique identifier for each user                      | Categorical    |
| `Touchpoint`   | The interaction point (e.g., website, mobile app)    | Categorical    |
| `TimeSpent`    | Time spent by the user at the touchpoint (in mins)   | Numerical      |
| `ActionTaken`  | Action taken by the user (e.g., purchase, left, etc.)| Categorical    |

**Table 2: UserFeedback**

| Column Name  | Description                                          | Feature Type   |
|--------------|------------------------------------------------------|----------------|
| `UserID`       | Unique identifier for each user                      | Categorical    |
| `Feedback`     | User's feedback on their experience                  | Text           |
| `Rating`       | Rating given by the user out of 5                    | Numerical      |



## **Questions**:

1. **Customer Touchpoint Analysis**: Analyzing the data from the `UserActions` table, identify touchpoints where most drop-offs occur. Can you illustrate the journey of an average user using a flow diagram, emphasizing these drop-off points?

2. **Feedback Sentiment Analysis**: Using the `UserFeedback` table, conduct a sentiment analysis on the feedback received from users. Based on this, which touchpoints (from `UserActions` table) are most likely associated with negative sentiments?

3. **Predicting User Drop-offs**: Using both `UserActions` and `UserFeedback` tables, build a model to predict whether a user will drop off at the next touchpoint. Use the `ActionTaken` column as the target variable, where "left" denotes a drop-off. How would you ensure that your model is not biased by imbalanced data?

4. **Enhancing Customer Experience**: Given the insights from questions 1 & 2, and predictions from question 3, recommend strategies to improve the customer experience at the identified drop-off touchpoints. Which touchpoints should be the primary focus for improvements?