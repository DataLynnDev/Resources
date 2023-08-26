# **Business Problem Statement:**
Spotify Premium Duo is a product designed for two people living at the same address. It offers all the benefits of Premium for two accounts at a discounted price. Your challenge, as an aspiring data scientist for the Premium Duo team, is to understand how the Premium Duo offering impacts user behavior, product engagement, and revenue. Additionally, we want to understand the elements that contribute to the success of a shared playlist and how marketing strategies could optimize the product's reach.

## **Data Tables:**

**Table: DuoUserActivity**

| Column Name | Description                              | Feature Type  |
|-------------|------------------------------------------|---------------|
| UserID      | Unique identifier for the user           | Categorical   |
| PlaylistID  | Unique identifier for the playlist       | Categorical   |
| SongCount   | Number of songs listened in the playlist| Numerical     |
| ListenTime  | Total time spent listening in hours     | Numerical     |
| Location    | Address of the user                      | Categorical   |
| PremiumType | Type of premium (Individual/Duo)         | Categorical   |
| Revenue     | Revenue generated from the user          | Numerical     |

**Table: SongData**

| Column Name | Description                          | Feature Type  |
|-------------|------------------------------------------|---------------|
| SongID      | Unique identifier for the song          | Categorical   |
| Genre       | Genre of the song                       | Categorical   |
| Artist      | Artist of the song                      | Categorical   |
| Duration    | Duration of the song in minutes         | Numerical     |
| PlaylistID  | Unique identifier for the playlist      | Categorical   |

## **Questions:**

1. **(Data Manipulation & Cleaning)** Given the `DuoUserActivity` and `SongData` tables, can you create a new dataframe that consolidates the top 5 genres preferred by Duo users? Use the total listen time for each genre as the determining factor. Also, create a new column which indicates the average revenue generated from these top genres.


2. **(Probability and Statistics)** Based on the uniform distribution of song durations within the `SongData` table, if you were to pick 100 random songs, estimate the probability that their average duration is more than 4 minutes?


3. **(Machine Learning & Modeling)** Imagine the Premium Duo team is interested in launching a recommendation system for Duo users, leveraging the listening history. Use the `DuoUserActivity` and `SongData` tables to predict the next possible genre a user might want to explore. Please specify which features would be critical for this prediction, and which machine learning model would be suitable for this kind of prediction.

4. **(Product Design & Analytics)** The Duo product marketing team wants to understand the attributes that make a shared playlist successful. Considering the `DuoUserActivity` table, if a playlist has a higher song count and longer listen time, how would you assess the correlation between these metrics and revenue generation? Additionally, if there were to be a decline in listen time, how would you advise the product team to modify their playlist curation approach?



