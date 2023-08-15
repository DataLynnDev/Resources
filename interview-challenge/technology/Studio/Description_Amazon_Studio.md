# Business Problem Statement

Amazon Studios aims to improve user engagement with Prime Video by tailoring original content based on user preferences and viewing habits. The business problem to solve is how to recommend the right content to the right audience at the right time, optimize the production of new series or films, and enhance the overall user experience through informed data-driven decisions.

## Data Tables
**Table 1: `user_activity`**

| Column Name   | Description                        | Feature Type |
|---------------|------------------------------------|--------------|
| user_id       | Unique identifier for users        | Categorical  |
| movie_id      | Unique identifier for movies       | Categorical  |
| watch_time    | Total time watched in minutes      | Numerical    |
| watched_date  | Date when the movie was watched    | Date         |

**Table 2: `movie_details`**

| Column Name  | Description                        | Feature Type |
|--------------|-------------------------------------|--------------|
| movie_id     | Unique identifier for movies        | Categorical  |
| genre        | Genre of the movie or series        | Categorical  |
| release_date | Release date of the movie or series | Date         |

## Questions

1. **Scenario**: Amazon Studios wants to understand user retention and engagement with various genres over the past six months. How would you compute the month-to-month user retention rate for each genre?

2. **Scenario**: Some user profiles are showing significant spikes in watch time, while others have null values. How would you approach identifying and treating these anomalies in watch time, such as replacing missing values?


3. **Scenario (Progressive)**:
   * **Part 1**: Amazon Studios is planning a new series and wants to know which genre appeals the most to its users. Based on the user activity and movie details tables, build a classification model to predict the likelihood that a user would watch a particular genre. How would you process the dataset for training, decide what model to use, and explain the model you chose?
   * **Part 2**: After building the model, explain how you would test it, tune hyperparameters, and interpret the results in the context of the business problem.