# **Business Problem Statement**:
Spotify aims to better curate mood-based playlists, create smoother song transitions, and even suggest potential remixes or covers by leveraging the Echo Nest technology. This can enhance user engagement, leading to longer listening sessions and increased user satisfaction. As part of the Audio Analysis team, our focus is to deep dive into the musical features of each track to understand these attributes and provide insights for the above-mentioned applications.


## **Data Tables**:

**Table 1: TrackDetails**

| Column Name  | Description                              | Feature Type   |
|--------------|------------------------------------------|----------------|
| `track_id`     | Unique Identifier for each track         | Categorical    |
| `tempo`        | Beats per minute of the track            | Numerical      |
| `key`          | Key of the track                         | Categorical    |
| `mode`         | Major or Minor                           | Categorical    |
| `loudness`     | Overall loudness of the track            | Numerical      |
| `timbre`       | Overall quality/color of sound           | Numerical      |
| `energy`       | Energy of the track                      | Numerical      |
| `mood`         | Mood identifier of the track             | Categorical    |

**Table 2: TrackPopularity**

| Column Name  | Description                              | Feature Type   |
|--------------|------------------------------------------|----------------|
| `track_id`     | Unique Identifier for each track         | Categorical    |
| `date`         | Date of the track play                   | DateTime       |
| `play_count`   | Number of plays on the date              | Numerical      |



## **Questions**:

1. **Scenario**: As the first step in our analysis, we would like to understand the key characteristics of tracks that are popular during specific moods.
    - **Question**: Given the TrackDetails and TrackPopularity tables, for each mood, identify the top 3 tracks based on `play_count` in the last 30 days. Alongside, display their corresponding key, mode, and tempo.

2. **Scenario**: The transition between songs is crucial for maintaining the listening experience. To aid in this, understanding how tempo transitions work in popular songs can be insightful.
    - **Question**: Using `TrackDetails` and `TrackPopularity` tables, identify pairs of songs that have sequential popularity (i.e., one song is played often followed by another) and display the tempo difference between these pairs.

3. **Scenario**: Spotify is curious about how the `energy` and `loudness` of a track affect its popularity for a given mood.
    - **Question**: Implement a regression model where the target variable is `play_count` from the `TrackPopularity` table and the predictors are `energy` and `loudness` from the `TrackDetails` table. State the model's equation and interpret its coefficients.

4. **Scenario**: Spotify wants to test if introducing a new feature - 'Adaptive Mood Transition', which would use timbre to suggest song transitions, would be beneficial.
    - **Question**: Describe a strategy to implement A/B testing for this feature using the provided tables, including how you'd segment the users, what metrics you'd monitor, and how you'd measure success.