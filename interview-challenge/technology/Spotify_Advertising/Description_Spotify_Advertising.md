# **Business Problem Statement:**

Spotify's Advertising department is keen on optimizing its advertising strategies for the free-tier users. Their primary goal is to increase ad revenue by presenting users with highly relevant ads, based on their listening habits, search history, and demographics. Furthermore, they're interested in determining the best times to present these ads for maximizing their impact while ensuring that the user's listening experience isn't severely disrupted.

## **Data Tables:**

**Table 1: UserActivity**

| Column Name        | Description                                 | Feature Type           |
|--------------------|---------------------------------------------|------------------------|
| `userID`             | Unique identifier for the user              | Categorical (Nominal)  |
| `songID`             | Unique identifier for the song played       | Categorical (Nominal)  |
| `searchHistory`      | Recent searches made by the user            | Text                   |
| `listeningDuration`  | Total time user spent listening in minutes  | Numeric (Continuous)   |
| `adPlayedTime`       | Timestamp when an ad was played to the user | DateTime               |
| `demographicDetail`  | Demographic details (Age, Gender, Location) | Categorical (Nominal)  |

**Table 2: AdPerformance**

| Column Name       | Description                                | Feature Type           |
|-------------------|--------------------------------------------|------------------------|
| `adID`              | Unique identifier for the advertisement    | Categorical (Nominal)  |
| `userID`            | User who saw the advertisement             | Categorical (Nominal)  |
| `interaction`       | Whether the user interacted with the ad    | Boolean                |
| `adCategory`        | Category of the ad (e.g., Tech, Fashion)   | Categorical (Nominal)  |
| `adSuccessRate`     | Success rate of the ad on other platforms  | Numeric (Continuous)   |

## **Questions:**

1. **Scenario**: Recently, we noticed a pattern of users with specific search histories interacting more with particular ad categories.
  - Given the `UserActivity` table, derive a new column representing the predominant search theme for each user using SQL. Further, merge this with the `AdPerformance` table to analyze if there's a strong correlation between a user's search theme and the ad category they interact with.

2. **Scenario**: To avoid disrupting user experience, it's crucial to identify the optimal time intervals during which users might be more receptive to ads.

  - Using the `UserActivity` table, can you determine any patterns or specific timeframes where users are more likely to tolerate or interact with an ad, based on their `listeningDuration`?

3. **Scenario**: We've been experimenting with the success rate of our ads, as derived from their performance on other platforms. We believe this might be a predictor of whether a user would interact with the ad on Spotify.

  - Given the `AdPerformance` table, can you construct a model predicting `interaction` based on `adSuccessRate` and `adCategory`? Clearly specify the target variable and its type.
    - **Target Variable**: `interaction`
    - **Target Variable Type**: Boolean

4. **Scenario**: We're planning a new ad campaign and would like to understand the impact of this campaign in the coming months. However, post-campaign, we might not know which users were exposed to it.
  
  - How would you set up an experiment or use available data to measure the campaign's impact on user interaction with ads?
