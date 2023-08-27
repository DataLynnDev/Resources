## **Business Problem Statement:**

Microsoft Azure's Machine Learning platform is continually evolving, aiming to provide better services for its users. The company is exploring the performance and user engagement metrics of their Azure Machine Learning tools. One of the main objectives is to understand the user demographics, the most frequently used features, and potential system bottlenecks or areas of improvement. By doing so, Microsoft hopes to enhance user experience and optimize resource allocation.

## **Data Tables:**

1. **UserActivity**

| Column Name | Description                                         | Feature Type  |
|-------------|-----------------------------------------------------|---------------|
| UserID      | Unique identifier for each user                     | Categorical   |
| Age         | Age of the user                                     | Numerical     |
| Country     | Country of the user                                 | Categorical   |
| LoginDate   | Date when user logged in                            | Date          |
| FeatureUsed | The machine learning feature used by the user       | Categorical   |
| Duration    | Time spent on the feature in minutes                | Numerical     |

2. **SystemPerformance**

| Column Name | Description                                                 | Feature Type  |
|-------------|-------------------------------------------------------------|---------------|
| Date        | Date of observation                                         | Date          |
| FeatureName | Name of the machine learning feature                        | Categorical   |
| LoadTime    | Average loading time for the feature in seconds             | Numerical     |
| ErrorRate   | Percentage of user sessions with errors using the feature   | Numerical     |


## **Questions:**

1. **(Data Manipulation & Cleaning)**

    Given the UserActivity table, some users have multiple entries for the same day due to logging in multiple times. Generate a new table that aggregates the total duration for each user per day. Then, using the SystemPerformance table, identify any potential relationships between the feature's LoadTime and the average duration spent on that feature.


2. **(Probability and Statistics)**

    Observing the SystemPerformance table, can you calculate the probability that a randomly chosen user session experienced an error while using a particular feature on any given day?

3. **(Machine Learning & Modeling)**

    Using the aggregated table from question 1, predict the Duration a user will spend on Azure ML based on Age, Country, and FeatureUsed. Clearly state which feature is your target variable and the target variable type.


4. **(Product Design & Analytics)**

    Considering the UserActivity and SystemPerformance tables, design an experiment to test the hypothesis that improving the LoadTime of a feature by 10% can increase the average Duration spent by a user by at least 5%. Describe your approach, metrics to track, and how you would evaluate the success of the experiment.

