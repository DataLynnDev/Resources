# **Business Problem Statement:**
Indeed aims to improve user engagement by tailoring marketing campaigns, personalized job alerts, and offering specialized content based on user segments. Through clustering algorithms, user segments are created based on demographics, search behavior, and job preferences. Your challenge is to help Indeed understand these user segments better and provide actionable insights and predictions that can enhance user experience.

## **Data Tables:**

**Table: UserProfiles**

| Column Name     | Description                       | Feature Type   |
|-----------------|-----------------------------------|----------------|
| UserID          | Unique identifier for the user    | Categorical    |
| Age             | Age of the user                   | Numerical      |
| Gender          | Gender of the user                | Categorical    |
| SearchFrequency | How often they search jobs/week   | Numerical      |
| LastSearch      | Days since their last job search  | Numerical      |
| JobPreference   | Type of job they're interested in | Categorical    |

**Table: UserInteractions**

| Column Name    | Description                              | Feature Type  |
|----------------|------------------------------------------|---------------|
| UserID         | Unique identifier for the user           | Categorical   |
| CampaignID     | Unique identifier for the marketing campaign | Categorical |
| Clicked        | Whether they clicked on a marketing campaign or not | Boolean   |
| JobAlertOpened | Whether they opened a personalized job alert | Boolean     |
| ContentRead    | Type of content read by the user (if any) | Categorical |

## **Questions:**

1. You notice that some users in the `UserProfiles` table have an unusually high value in the `SearchFrequency` column, possibly due to an error in tracking. Detect and visualize any outliers in the `SearchFrequency` column. Based on this, suggest a threshold beyond which values might be considered errors.  


2. Indeed wants to understand if certain demographics are more likely to engage with their personalized job alerts. Given the `UserProfiles` and `UserInteractions` tables, can you test if the probability of a user with a `JobPreference` of "Tech" opening a `JobAlertOpened` is significantly different from the rest of the population?  


3. To tailor marketing campaigns effectively, Indeed wants to predict if a user will click on a particular marketing campaign based on their profile.  Using the `UserProfiles` and `UserInteractions` tables, develop a model where the target variable is `Clicked`. Specify the features you would choose and justify your choice. Also, discuss the performance metric that would be most relevant for this problem.  
*Target Variable:* Clicked (Boolean)  

4. Indeed believes that users who have recently searched for jobs (`LastSearch` close to 0) are more likely to interact with content. However, this might vary based on the `JobPreference` category. Calculate the probability that a user with `LastSearch` less than 7 days (i.e., within the last week) has also read a particular type of content, say "InterviewTips", grouped by their `JobPreference`. Compare these probabilities among the different `JobPreference` categories and provide insights.  

