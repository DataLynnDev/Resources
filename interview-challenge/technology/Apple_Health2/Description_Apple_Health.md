# **Business Problem Statement**:
As Apple continues to innovate within the health domain through its Health app and ResearchKit platform, there's a growing need to understand users' health behaviors, predict potential health risks, and enhance participation in clinical studies. As part of the Health and ResearchKit team, the primary objective is to leverage data to foster healthier communities and assist medical professionals in collecting accurate clinical data.



## Data Table:
**HealthData**

| Column Name  | Description                             | Feature Type     |
|--------------|-----------------------------------------|------------------|
| `UserID`     | Unique Identifier for each user         | Categorical      |
| `Timestamp`  | Time of the health data entry           | DateTime         |
| `Activity`   | Type of activity (e.g., walking, yoga)  | Categorical      |
| `Duration`   | Duration of the activity in minutes     | Numerical        |
| `HeartRate`  | Average heart rate during activity      | Numerical        |
| `Steps`      | Number of steps during activity         | Numerical        |
| `Calories`   | Calories burned during the activity     | Numerical        |
| `SleepHours` | Number of hours slept per day           | Numerical        |
| `StudyID`    | Identifier for any associated study     | Categorical      |
| `StudyParticipation` | If the user participated in a study (yes/no)  | Categorical  |



## **Questions**:

1. **Scenario**: Given the increasing popularity of the Health app, a considerable volume of health data is available. From this data, we want to understand users' fitness habits.
   
   **Question**: From the `HealthData` table, load the last three months of data and segment users based on the average number of `Steps` they take and the total `Duration` of their activities. What can you infer about the different segments of users in terms of their health habits?
   
2. **Scenario**: Apple wants to improve its Health app by tailoring features to different types of users. Understanding sleep patterns is essential to make app recommendations and improve user health.

   **Question**: Compute the average `SleepHours` for users participating in clinical studies (`StudyParticipation` = yes) versus those who do not. Using statistical tests, determine if there's a significant difference in sleep patterns between these two groups.


3. **Scenario**: A new version of the Health app was recently released. Apple wants to determine if the app update increased users' participation in clinical studies.

   **Question**: Conduct an A/B test where Group A comprises users on the old version and Group B includes users on the new version. Using the `StudyParticipation` column, determine if there's a significant increase in study participation in Group B.


4. **Scenario**: Apple is partnering with health professionals to design a new study related to heart health. For this, understanding the correlation between activities and heart rate is essential.

   **Question**: Analyze the relationship between `Activity` and average `HeartRate` for each activity. Which activity leads to the highest average heart rate? How does this vary amongst different user segments in question 1? For the next phase, use this information to recommend potential users that can be targeted for the heart health study.
