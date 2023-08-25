# Business Problem Statement:
Spotify's podcast team is looking to optimize the discovery and engagement of podcast listeners. The goal is to analyze user behavior, identify key success factors in podcast playlists, and provide personalized recommendations to enhance user engagement. The main challenge is to use the historical data to identify user preferences, analyze listening patterns, and propose strategies to improve podcast discoverability and increase listener retention.

## Data Table:

### Podcasts Data Table:

| Column Name  | Description                                | Feature Type |
|--------------|--------------------------------------------|--------------|
| podcast_id   | Unique identifier for the podcast          | Categorical  |
| genre        | Genre of the podcast (e.g., Comedy, News)  | Categorical  |
| duration     | Duration of the podcast in minutes         | Numerical    |
| launch_date  | Launch date of the podcast                 | Datetime     |

### User Behavior Data Table:

| Column Name      | Description                                            | Feature Type |
|------------------|--------------------------------------------------------|--------------|
| user_id          | Unique identifier for the user                         | Categorical  |
| podcast_id       | Unique identifier for the podcast                      | Categorical  |
| genre            | Genre of the podcast                                   | Categorical  |
| duration         | Duration of the podcast in minutes                     | Numerical    |
| listen_time      | Time spent listening to the podcast                    | Numerical    |
| rating           | User rating for the podcast (1 to 5)                   | Numerical    |
| subscribed       | Whether the user has subscribed to the podcast (1/0)   | Binary       |
| launch_date      | Launch date of the podcast                             | Datetime     |
| user_join_date   | Date the user joined Spotify                           | Datetime     |



## Questions:

1. We want to understand the listening patterns across different genres and how user subscriptions to podcasts influence those patterns. Write a SQL query that groups the podcasts by genre, aggregates the average listening time, and filters only those genres where the subscription rate is above 0.5 .

2. You are tasked with analyzing user ratings and the impact of the launch date of podcasts. Determine how the rating of a podcast correlates with its launch date and duration, and identify the genre that is most affected by these factors.

3. Spotify is planning to launch a new recommendation engine for podcasts. By considering a dataset with user ratings, listening time, and subscription status, build a regression model to predict a user's rating for a podcast. Identify the key features contributing to the predictions and provide insights on how to personalize podcast recommendations.


