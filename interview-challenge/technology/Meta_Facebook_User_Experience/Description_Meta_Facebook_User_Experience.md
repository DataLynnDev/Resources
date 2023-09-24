# **Business Problem Statement:**
With the growth of Facebook's user base, there has been an increasing number of users reporting challenges with the platform's new features. We've observed that a significant drop in user interaction happens post-feature release. As the Data Analyst for the User Experience & Product Development team, your responsibility is to identify problem areas and suggest potential improvements. By analyzing user interactions, feedback, and behavior patterns, you will help the team reshape these new features to optimize user satisfaction and engagement.

## **Data Tables:**

### **Table 1: User_Feedback**

| Column Name     | Description                              | Feature Type  |
|-----------------|------------------------------------------|---------------|
| user_id         | Unique identifier for each user          | Numeric      |
| feature_name    | Name of the feature the feedback is about| Text         |
| feedback_date   | Date when the feedback was given         | Date         |
| feedback_score  | User rating for the feature (1-5)        | Numeric      |
| feedback_text   | Textual feedback from the user           | Text         |

### **Table 2: User_Interactions**

| Column Name     | Description                                 | Feature Type  |
|-----------------|---------------------------------------------|---------------|
| user_id         | Unique identifier for each user             | Numeric      |
| feature_name    | Name of the feature the user interacted with| Text         |
| interaction_date| Date of interaction                         | Date         |
| interaction_time| Duration of interaction in seconds          | Numeric      |
| drop_point      | Point in the feature where user left/dropped| Text         |

## Questions

1. **Data Cleaning & Exploration**
**Scenario:** There have been complaints from the product team that some feedback scores are missing, and certain interaction times seem unusually high, potentially due to logging errors.
**Task:** Identify and handle missing values in the `feedback_score` column from the `User_Feedback` table. Additionally, detect and treat outliers in the `interaction_time` column of the `User_Interactions` table.

2. **SQL Queries**
**Scenario:** The management wants to understand which features have the least favorable feedback and also see which features have the highest interaction times, possibly indicating user struggles.
**Task:** Using SQL, join `User_Feedback` and `User_Interactions` tables on `user_id` and `feature_name`. Find the feature with the lowest average feedback score and the feature with the third-highest average interaction time.


3. **Probability and Statistical Analysis**
**Scenario:** The product team hypothesizes that user interactions with a certain feature have been dropping over time due to the negative feedback received.
**Task:** Based on the `User_Feedback` table, calculate the probability that on a given day, a user gives a feedback score below 3 AND interacts with the feature for more than 300 seconds. Implement this calculation programmatically to validate the product team's hypothesis.


4. **Product & Business Sense**
**Scenario:** Post your analysis, the product team decides to introduce a revised version of the least favorable feature. They plan to run an A/B test to compare the old and new versions.
**Task:** Design an A/B test strategy to measure the success of the new feature. Considering your findings from the above questions, what metrics would you track and what insights would you look to derive to determine the success of the new feature?
