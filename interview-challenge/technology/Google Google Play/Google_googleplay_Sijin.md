## 1. Business Problem Statement

Google Play Games has become a global platform hosting a wide variety of games, serving millions of users. Understanding the factors influencing user ratings of games is vital as high ratings often correlate with increased popularity and revenue. The goal of this data challenge is to predict the average user rating of upcoming games on Google Play Games. By leveraging data science methodologies, historical game data, user behavior, and external factors, we aim to create a model that anticipates potential high-rated games early in their lifecycle. This allows Google Play Games to more effectively strategize its promotion and resource allocation, potentially elevating user satisfaction and engagement.


## 2. Data Challenge Tables


#### 1. GameMetaData

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

Sample Data:

|GameID|GameName|GameGenre|Developer|Price|InAppPurchase|GameSize|AverageUserRating|AgeRating|ReleaseDate|MajorEventInFirstWeek|MajorEventInFirstMonth|
|---|---|---|---|---|---|---|---|---|---|---|---|
|1|Game A|Action|Developer X|0|Yes|150|4.5|12+|2022-01-15|Yes|Yes|
|2|Game B|Adventure|Developer Y|2.99|No|200|4.2|9+|2022-02-20|No|Yes|
|3|Game C|Puzzle|Developer Z|0|Yes|50|4.8|4+|2022-03-30|No|No|

#### 2. GamePopularityData

|Column|Description|
|---|---|
|GameID| Unique identifier for each game|
|Downloads| Number of downloads|
|Revenue| Revenue earned from the game|
|PeakPopularityDate| Date when the game reached peak popularity|
|TimeToPeakPopularity| Time (in days) it took the game to reach peak popularity after its release|

Sample Data:

|GameID|Downloads|Revenue|PeakPopularityDate|TimeToPeakPopularity|
|---|---|---|---|---|
|1|2000000|100000|2022-02-01|17|
|2|1500000|200000|2022-03-01|9|
|3|2500000|150000|2022-04-15|16|

#### 3. UserDemographicsData

|Column|Description|
|---|---|
|UserID| Unique identifier for each user|
|Age| Age of the user|
|Gender| Gender of the user|
|Location| Location of the user|
|FavoriteGenre| Favorite game genre of the user|

Sample Data:

|UserID|Age|Gender|Location|FavoriteGenre|
|---|---|---|---|---|
|1|25|Male|USA|Action|
|2|34|Female|UK|Adventure|
|3|18|Male|India|Puzzle|


#### 4. UserGameInteraction

|Column|Description|
|---|---|
|UserID| Unique identifier for each user|
|GameID| Unique identifier for each game|
|InteractionTime| The total time a user has played the game, measured in minutes|
|InteractionDate| The date of the interaction|
|InteractionCount| Number of interactions a user has with a game on a given day|
|MoneySpent| Amount of money a user has spent on a game on a given day|


Sample Data:

| UserID | GameID | InteractionTime | InteractionDate | InteractionCount | MoneySpent |
|--------|--------|-----------------|-----------------|------------------|------------|
| 1      | 1      | 50              | 2023-01-20      | 3                | 0.00       |
| 2      | 1      | 120             | 2023-01-22      | 5                | 1.99       |
| 1      | 2      | 75              | 2023-01-25      | 4                | 0.00       |
| 3      | 1      | 85              | 2023-01-30      | 2                | 0.99       |
| 4      | 2      | 60              | 2023-02-05      | 1                | 0.00       |



## 3. Questions for the Data Challenge

###  1. "Generating a User Engagement Score (Python)"

Use the existing data in the 'UserGameInteraction' table to generate a 'UserEngagementScore' for each game. This score should incorporate the InteractionTime, the frequency of interaction, and be normalized to fall within the range of 0 to 100. Discuss how you came up with this score, the mathematical formula used, and how this score can be used to gauge the user engagement level of the games. Provide the Python code to implement this.

**Answer:**

To come up with the User Engagement Score, I considered three primary factors that indicate how engaged a user is with a game:

1. `InteractionTime`: This represents the total amount of time a user has spent interacting with a game. A higher interaction time generally suggests that a user is more engaged with the game.

2. `InteractionCount`: This is the frequency of interactions a user has with the game. Even if a user doesn't spend a lot of time on a game in each session, frequent interactions may still indicate a high level of engagement.

3. `MoneySpent`: This represents the total amount of money a user has spent on a game. Spending money on a game is a strong indicator of engagement, as it suggests that the user values the game enough to invest in it.

The User Engagement Score is calculated by taking the average of these three factors. However, before averaging them, I first normalize each factor to a range of 0 to 1. This ensures that each factor contributes equally to the final score, regardless of their original scales. For example, without normalization, `InteractionTime` (which could be in the range of hundreds or thousands of minutes) could overshadow `InteractionCount` (which might typically be less than 10).

Normalization is done using the following formula:

`(x - min(x)) / (max(x) - min(x))`

where x represents one of the three factors, and min(x) and max(x) are the minimum and maximum values of that factor across all games.

Finally, to make the User Engagement Score more intuitive and easier to interpret, I scale it to a range of 0 to 100. This is done by multiplying the average of the normalized factors by 100.


Mathematically, the formula to calculate 'UserEngagementScore' could be:

![Engagement_Score_Formula](https://latex.codecogs.com/svg.latex?%5Cinline%20UserEngagementScore%20%3D%20%5Cfrac%7B%5Cleft%28%5Cfrac%7BInteractionTime_i%20-%20InteractionTime_%7Bmin%7D%7D%7BInteractionTime_%7Bmax%7D%20-%20InteractionTime_%7Bmin%7D%7D%5Cright%29%20&plus;%20%5Cleft%28%5Cfrac%7BInteractionCount_i%20-%20InteractionCount_%7Bmin%7D%7D%7BInteractionCount_%7Bmax%7D%20-%20InteractionCount_%7Bmin%7D%7D%5Cright%29%20&plus;%20%5Cleft%28%5Cfrac%7BMoneySpent_i%20-%20MoneySpent_%7Bmin%7D%7D%7BMoneySpent_%7Bmax%7D%20-%20MoneySpent_%7Bmin%7D%7D%5Cright%29%7D%7B3%7D%20*%20100)

Where:

- 'i' refers to each individual game
- 'InteractionTime', 'InteractionCount', and 'MoneySpent' are the total interaction time, interaction count, and money spent for game 'i', respectively
- 'InteractionTime_min', 'InteractionTime_max', 'InteractionCount_min', 'InteractionCount_max', 'MoneySpent_min', and 'MoneySpent_max' are the minimum and maximum values of 'InteractionTime', 'InteractionCount', and 'MoneySpent' across all games, respectively


In the final merged dataset, each game now has an additional 'UserEngagementScore' that represents the level of user engagement based on interaction time, interaction frequency, and money spent.

### 2. "User Rating Trends Across Different Genres (SQL)"


Using the 'GameMetaData' tables, analyze the user rating trends across different game genres. How might these trends be applied to predict which game genres may receive higher user ratings in the future?



**Answer:**

We could look at the distribution of ratings in each genre, rather than just the average. A genre may have the same average rating as another, but a different distribution (e.g., more 5-star ratings and 1-star ratings, fewer middle-of-the-road ratings). In such cases, the mode (most common rating) or the median (middle rating when sorted) might be more informative than the mean.

---


This query will give us the average, minimum, and maximum rating for each genre. It will also count the total number of games and the number of highly-rated games (with a rating of 4 or higher) in each genre.

By analyzing this output, we can obtain more detailed insights:

1. **AvgRating:** We can understand which genres, on average, perform better than others.

2. **MinRating and MaxRating:** We can identify the range of ratings in each genre, which will help us understand the quality consistency within genres.

3. **TotalGames:** We can see how many games belong to each genre. This might have an effect on the average rating as genres with more games may have a more "averaged out" rating.

4. **HighRatedGames:** This will help us understand which genres tend to have more high-rated games. Genres with a high proportion of high-rated games could be considered of higher quality or more consistently pleasing to users.


### 3. "Impact of In-App Purchases on User Ratings (Python)"

In the 'GameMetaData' table, investigate the relationship between the option for in-app purchases and the average user rating. How does this feature impact the game's user ratings? How might this information be used in predicting the user ratings of future games?

**Answer:**

1. We first merge the `game_metadata` and `game_popularity` datasets using the `GameID` field. This creates a single DataFrame that contains both the game metadata and the game popularity data.

2. Next, we split the merged DataFrame into two separate DataFrames: `with_inapp`, which contains games that have in-app purchases, and `without_inapp`, which contains games that don't have in-app purchases.

3. Finally, we use the `ttest_ind` function from the `scipy.stats` module to perform a two-sample t-test on the 'AverageUserRating' of the two groups. The `ttest_ind` function returns two values: the t-statistic and the p-value. The t-statistic tells us how much the means of the two groups differ in terms of standard error, while the p-value tells us the probability of seeing a result as extreme as the one we observed if the null hypothesis were true. In this case, a low p-value (usually below 0.05) would suggest that the 'AverageUserRating' significantly differs between games with and without in-app purchases.

---

**How the test results help us understand user psychology:**

The results from the t-test would help determine if there's a significant difference in average user ratings between games with and without in-app purchases. If the t-test results in a low p-value (typically below 0.05), it would suggest that there is a statistically significant difference in average user ratings based on the presence of in-app purchases.

If, for instance, games with in-app purchases have a higher average user rating, this could suggest that users may appreciate the flexibility and extended content that in-app purchases can provide, thereby rating these games higher. On the other hand, if games without in-app purchases have a higher average user rating, this could indicate that users prefer not to be 'nickel-and-dimed' after initially purchasing or downloading a game.

**How this information might be used in predicting the user ratings of future games:**

Understanding the relationship between in-app purchases and user ratings can be valuable when building a predictive model for game ratings. If a significant relationship is found, the presence of in-app purchases could be a strong feature in the model.

For instance, if games with in-app purchases are generally rated higher, a predictive model could factor this in and might predict a higher user rating for a new game that features in-app purchases, all else being equal. Conversely, if games without in-app purchases tend to rate higher, the model might predict a lower rating for a game that includes them.

### 4. "Demographic Analysis of High Rated Games (SQL)"

Using the 'UserDemographicsData', 'GameMetaData', and 'UserGameInteraction' tables, determine which demographic groups are most attracted to the highest rated games. How does this analysis help in predicting the user ratings of future games?


**Answer:**

This is a complex question that will require some deeper analysis. To answer this question, let's follow these steps:

1. Identify the highest rated games: We can do this by averaging the user ratings for each game and then selecting the top-rated games.
2. For these top-rated games, observe the demographic information of the users who interacted with these games. We can get this information by joining 'UserGameInteraction' with 'UserDemographicsData' on 'UserID'.
3. Then, analyze the demographic information to see which demographic groups are most represented among these users. For example, we could calculate the count or percentage of users from each demographic group who played the top-rated games.
4. Finally, we can discuss how this information could help in predicting the user ratings of future games. For example, if we know that a certain demographic group is more likely to play top-rated games, and a new game is targeting this demographic group, it might also be more likely to receive high ratings.



---

As for how it helps in predicting user ratings for future games, we can consider a few scenarios. If a new game is targeted towards a demographic group that frequently plays high-rated games, we might anticipate higher ratings for that game. We could also use this demographic information as features in a machine learning model to predict user ratings. For example, if a game is targeting a demographic group associated with high user ratings, that could be a positive feature in our model. This allows us to build a richer model that not only includes information about the game itself (like genre or developer), but also the target demographic, increasing our chances of accurately predicting user ratings.


### 5. "Data Preprocessing and Categorical Variables Handling (PySpark)"

Given the provided tables, write a PySpark script to perform data preprocessing. This should include handling missing values and transforming categorical variables into a format suitable for machine learning models. Discuss how these preprocessing steps could potentially impact the performance of models predicting game ratings.


**Answer:**

1. **Spark Session**: We start by creating a SparkSession which is the entry point to any Spark functionality.

2. **Data Conversion**: The merged pandas dataframe is then converted to a Spark dataframe using the `createDataFrame` function.

3. **Null Handling**: The numeric columns are filled with `0` for any null values. The categorical columns are filled with a placeholder string 'Missing'. The rationale is that nulls or missing data can often cause issues during processing or modeling, so it's better to handle them upfront.

4. **Binary Conversion**: For binary columns, we map 'Yes' to 1 and 'No' to 0.

5. **Encoding Categorical Variables**: Spark ML can't directly handle categorical variables. Therefore, these need to be converted into a form that can be understood by the machine learning algorithms. For this, we use a two-step process: `StringIndexer` and `OneHotEncoder`.

   - **StringIndexer**: This indexes (assigns unique integer values to) each category of the column. For example, if a column has 'Red', 'Blue', 'Green', these might be mapped to 0, 1, 2 respectively.

   - **OneHotEncoder**: This then converts these index numbers into a binary vector with at most a single '1'. For example, 'Red' might be [1, 0, 0], 'Blue' might be [0, 1, 0], and 'Green' might be [0, 0, 1]. This is done because most machine learning algorithms work better with numerical inputs.

6. **Pipeline**: A pipeline is used to apply these transformations in sequence. The transformed dataframe contains the indexed and encoded columns.

7. **Dropping Original Columns**: After the transformations, the original categorical columns are dropped from the dataframe, as they are no longer needed.

8. **Feature Vector**: Lastly, a feature vector is created using `VectorAssembler`. This feature vector is a single vector column that aggregates all the feature columns. This is typically how Spark ML expects the input data.


### 6. "Creating a User Rating Prediction Model (PySpark)"

Once the data is preprocessed and features are engineered, use this data to train a machine learning model to predict the average user rating of a game. Discuss your choice of model, the reason behind this choice, and any optimization techniques used for its training.

**Answer:**

**Choice of model: RandomForestRegressor**

Random Forest is an ensemble learning method that operates by constructing a multitude of decision trees during training and outputting the mean prediction of the individual trees for regression tasks.

The reason behind this choice:

1. **Handling of Complex Data:** Random Forests are capable of handling complex datasets with a mixture of numerical and categorical features, as well as missing data.

2. **Robust to Overfitting:** Random Forests are less prone to overfitting than many other models because they average the results over a large number of individual decision trees, each of which is trained on a random subset of the data.

3. **Non-linear Relationships:** Random Forests can capture non-linear relationships between features and the target variable, which might be the case in our data.

4. **Feature Importance:** Random Forests provide a measure of feature importance, which can be very helpful in understanding which features are driving the predictions.

**Optimization techniques used for training:**

In the provided code, we don't explicitly use any optimization techniques. However, there are a few things we could do to optimize a Random Forest model:

1. **Hyperparameter Tuning:** We could use methods like Grid Search or Random Search to find the optimal hyperparameters for the model, such as the number of trees, the maximum depth of the trees, and so on.

2. **Feature Selection:** Although Random Forests can handle a large number of features, irrelevant features could still potentially reduce the performance of the model. We could use feature importance measures to select the most relevant features.

3. **Handling Imbalanced Data:** If our target variable is heavily imbalanced, we might want to use techniques such as oversampling, undersampling, or generating synthetic samples to make the data more balanced.

