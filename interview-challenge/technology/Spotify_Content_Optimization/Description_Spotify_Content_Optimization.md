# **Business Problem Statement:**  
Spotify's Content Optimization team aims to identify which artists, podcasts, or content to promote based on user listening trends. The challenge is to analyze user behavior on tracks, comprehend their preferences, and provide insights into content acquisition and production. Understanding patterns in user searches, track skips, and playtime can offer deep insights into what content is in demand.

## **Data Table:**

**UserBehavior**

| Columns      | Description                                        | Feature Type        |
|--------------|----------------------------------------------------|---------------------|
| `userID`                 | Unique identifier for users                                | Categorical      |
| `trackID`                | Unique identifier for tracks                               | Categorical      |
| `searchQuery`            | Text of user's search                                      | Text             |
| `skipCount`              | Number of times a track was skipped by a user              | Numerical        |
| `playTime`               | Total time a user listened to a track (in minutes)         | Numerical        |
| `genre`                  | Genre of the track                                         | Categorical      |
| `artistID`               | Unique identifier for artist                               | Categorical      |
| `timestamp`              | Date and time when the track was played                    | Datetime         |
| `playlistType`           | Type of playlist (e.g., curated, user-generated)           | Categorical      |
| `searchBeforePlay`       | Whether the track was searched before it was played (True/False) | Boolean        |

## **Questions:**

**1. Data Manipulation & Cleaning Question**:  
  - **Scenario**: In a weekly review, you noticed that some tracks have a playTime of zero but no skip actions recorded. This seems to be an anomaly.  
  - **Question**: Identify these anomalies in the `UserBehavior` table. Additionally, create a new column named 'anomalyFlag' that marks these tracks as anomalies (`True` or `False`).  

**2. Probability and Statistics Question**:  
  - **Scenario**: Spotify is considering promoting a set of new artists in the rock genre. But before doing so, they want to assess the general popularity of rock songs based on the skip rate.  
  - **Question**: Calculate the skip rate (ratio of skipCount to total play instances) for the rock genre. Is this rate significantly different from the overall skip rate for all genres?   

**3. Machine Learning & Modeling Question**:  
  - **Scenario**: Spotify is planning to introduce a new feature that predicts whether a user will skip a song within the first 30 seconds. This will help in curating more personalized playlists.  
  - **Question**: Based on the `UserBehavior` table, build a model that predicts if a song will be skipped by a user within the first 30 seconds of playtime. Use 'skipCount' as the target variable and consider 'genre', 'searchBeforePlay', and 'playlistType' as features. Indicate the type of modeling technique you would use.  
    - *Target Variable*: `skipCount` (Binary: 1 if skipped, 0 if not)  

**4. Product Design & Analytics Question**:  
  - **Scenario**: Spotify is launching a new curated playlist for jazz enthusiasts. However, initial metrics show that the playlist has a high skip rate.  
  - **Question**: Investigate the tracks within the jazz genre in the `UserBehavior` table. Provide insights on why the skip rate might be high and suggest improvements for the curated playlist based on the most played tracks or artists.   