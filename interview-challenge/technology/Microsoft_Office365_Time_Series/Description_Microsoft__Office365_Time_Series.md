# **Business Problem Statement:**
Our team at Office 365 aims to use time series analysis to enhance the Outlook experience for users. Given the vast amount of emails users receive daily, it's crucial for Outlook to intelligently predict when a user is most likely to receive important emails based on their past email traffic. This would allow us to optimize notifications, reduce distractions, and improve user satisfaction. To achieve this, we are leveraging historical email traffic data to extract patterns, trends, and seasonal variations.

## **Data Table**
**EmailTraffic**

| Column Name   | Description                                      | Feature Type        |
|---------------|--------------------------------------------------|---------------------|
| UserID        | Unique identifier for the user                   | Categorical         |
| Timestamp     | Date and time when the email was received        | Datetime            |
| EmailType     | Type of the email (Promotional, Work, Personal)  | Categorical         |
| Importance    | Importance score from 0 (not important) to 10    | Continuous          |
| ResponseTime  | Time taken by user to open the email (in minutes)| Continuous          |
| SenderDomain  | Domain of the sender (e.g., gmail.com)           | Categorical         |
| EmailSize     | Size of the email in KB                          | Continuous          |
| AttachmentNum | Number of attachments in the email               | Discrete            |
| Weekday       | Day of the week the email was received           | Categorical         |
| HourOfDay     | Hour of the day when the email was received      | Discrete            |

## **Questions:**

1. **Data Manipulation & Cleaning**: Many users have reported that some emails have missing Importance scores. To fill these gaps, use statistical analysis to determine the best metric to replace these missing values. Considering the nature of our data, would it be best to replace missing values with the median or another statistical metric? Explain your reasoning.


2. **Probability and Statistics**: Given the dataset, we would like to understand how email traffic varies across different days of the week. What is the conditional probability that an email is of 'Work' type given that it's received on a 'Monday'? Also, derive insights on the distribution of the Importance scores for emails received on weekdays. Are they normally distributed?


3. **Machine Learning & Modeling**: Our primary goal is to predict the importance of an incoming email. Using the features from the `EmailTraffic` table, build a model to predict the `Importance` score of an email. Discuss potential issues like overfitting, especially considering the balance between different `EmailType` categories.
   - Target Variable: Importance


4. **Product Design & Analytics**: Imagine we're redesigning the notification system for Outlook. How would you use time series analysis on the `Timestamp` and `Importance` columns to design a model that intelligently predicts when a user is most likely to receive an important email in the next hour? This prediction would be instrumental in sending timely notifications to users, enhancing their experience.
