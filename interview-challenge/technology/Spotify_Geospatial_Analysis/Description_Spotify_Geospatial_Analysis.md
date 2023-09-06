# **Business Problem Statement**:
Different regions have unique musical tastes. By geographically analyzing listening habits, Spotify can curate region-specific playlists, promoting local artists, or even suggesting songs trending in a user's location. This data is invaluable to artists, helping them plan tours based on where their music is most popular. Also, to make informed decisions, Spotify needs a deeper understanding of how song popularity in one month influences listening habits in the next month for specific genres in various regions.



## **Data Table**:

**Data_Info**

| Column Name       | Description                                                  | Feature Type   |
|-------------------|--------------------------------------------------------------|----------------|
| `region`            | Geographical region (e.g., North America, Europe, Asia, etc.) | Categorical    |
| `genre`             | Music genre of the track                                     | Categorical    |
| `track_id`          | Unique identifier for the track                              | Categorical    |
| `track_popularity`  | Popularity score of the track (0-100)                        | Numerical      |
| `listen_count`      | Number of times the track was listened to in a given month    | Numerical      |
| `listen_month`      | Month and year when the track was listened to (e.g., Jan 2023)| DateTime      |



## **Questions:**

1. **SQL:** Given the data for January 2023, write a SQL query to find out how many unique genres had at least one song with a popularity score above 85 in the North America region.


2. **Statistics & Probability:** Let's assume for February 2023, you notice that a specific genre has suddenly become very popular in Europe. Using the data from January 2023, how would you estimate the likelihood of this event based on the listening habits of the previous month?


3. **Machine Learning & Modeling:** Based on the data for January 2023, build a predictive model to determine whether a genre's average track popularity score in a given region will lead to an increase in listen count for that genre in February 2023. Clearly mark the target variable and its type.

    - **Target Variable:** `IncreasedListens` (binary: 1 if February 2023 listens are higher than January 2023 listens for a specific genre in a region, 0 otherwise)

4. **Product Design & Analytics:** After analyzing the data for January and February 2023, you notice a trend in North America where tracks of a particular genre are gaining popularity. Design a visualization that shows the relationship between track popularity and listen count for this genre in North America for these two months.

