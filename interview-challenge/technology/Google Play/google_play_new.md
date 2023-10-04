# 1. Business Problem Statement

Google Play Games has become a global platform hosting a wide variety of games, serving millions of users. Understanding the factors influencing user ratings of games is vital as high ratings often correlate with increased popularity and revenue. The goal of this data challenge is to predict the average user rating of upcoming games on Google Play Games. By leveraging data science methodologies, historical game data, user behavior, and external factors, we aim to create a model that anticipates potential high-rated games early in their lifecycle. This allows Google Play Games to more effectively strategize its promotion and resource allocation, potentially elevating user satisfaction and engagement.

## 2. Data Challenge Tables

** 1. GameMetaData**

|Column|Description|
|---|---|
|GameID| Unique identifier for each game|
|GameName| Name of the game|
|GameGenre| Genre of the game|
|Developer| Developer of the game|
|Price| Price of the game|
|InAppPurchase| Whether the game has in-app purchase option|
|GameSize| Size of the game in MB|
|AverageUserRating| Average user rating of the game|
|AgeRating| Age rating of the game|
|ReleaseDate| Release date of the game|
|MajorEventInFirstWeek| Indicator if a major event took place within the first week of game release|
|MajorEventInFirstMonth| Indicator if a major event took place within the first month of game release|

**2. GamePopularityData**

|Column|Description|
|---|---|
|GameID| Unique identifier for each game|
|Downloads| Number of downloads|
|Revenue| Revenue earned from the game|
|PeakPopularityDate| Date when the game reached peak popularity|
|TimeToPeakPopularity| Time (in days) it took the game to reach peak popularity after its release|

**3. UserDemographicsData**

|Column|Description|
|---|---|
|UserID| Unique identifier for each user|
|Age| Age of the user|
|Gender| Gender of the user|
|Location| Location of the user|
|FavoriteGenre| Favorite game genre of the user|


**4. UserGameInteraction**

|Column|Description|
|---|---|
|UserID| Unique identifier for each user|
|GameID| Unique identifier for each game|
|InteractionTime| The total time a user has played the game, measured in minutes|
|InteractionDate| The date of the interaction|
|InteractionCount| Number of interactions a user has with a game on a given day|
|MoneySpent| Amount of money a user has spent on a game on a given day|


## 3. Questions for the Data Challenge


**1. "Generating a User Engagement Score (Python)"**

Use the existing data in the 'UserGameInteraction' table to generate a 'UserEngagementScore' for each game. This score should incorporate the InteractionTime, the frequency of interaction, and be normalized to fall within the range of 0 to 100. Discuss how you came up with this score, the mathematical formula used, and how this score can be used to gauge the user engagement level of the games. Provide the Python code to implement this.

**2. "User Rating Trends Across Different Genres (SQL)"**

Using the 'GameMetaData' tables, analyze the user rating trends across different game genres. What are the commonalities and differences you observe among genres with higher average user ratings? How might these trends be applied to predict which game genres may receive higher user ratings in the future?

**3. "Impact of In-App Purchases on User Ratings (Python)"**

In the 'GameMetaData' table, investigate the relationship between the option for in-app purchases and the average user rating. How does this feature impact the game's user ratings? How might this information be used in predicting the user ratings of future games?


**4. "Demographic Analysis of High Rated Games (SQL)"**

Using the 'UserDemographicsData', 'GameMetaData', and 'UserGameInteraction' tables, determine which demographic groups are most attracted to the highest rated games. How does this analysis help in predicting the user ratings of future games?

**5. "Data Preprocessing and Categorical Variables Handling (PySpark)"**

Given the provided tables, write a PySpark script to perform data preprocessing. This should include handling missing values and transforming categorical variables into a format suitable for machine learning models. Discuss how these preprocessing steps could potentially impact the performance of models predicting game ratings.


**6. "Creating a User Rating Prediction Model (PySpark)"**

Once the data is preprocessed and features are engineered, use this data to train a machine learning model to predict the average user rating of a game. Discuss your choice of model, the reason behind this choice, and any optimization techniques used for its training.



