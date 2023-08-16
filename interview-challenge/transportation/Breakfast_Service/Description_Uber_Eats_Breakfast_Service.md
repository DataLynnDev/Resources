# Business Problem Statement
With the rise of remote work and changing morning routines, breakfast has gained a new importance in users' daily lives. Uber Eats aims to tap into this evolving dynamic by making its breakfast service more efficient, tailored, and engaging. The goal is to analyze user behavior, optimize breakfast delivery, and recommend personalized breakfast choices, ultimately leading to a surge in breakfast orders.


## Data Tables

#### 1. **BreakfastPatterns**

| Column Name | Description                                 | Data Type  |
|-------------|---------------------------------------------|------------|
| user_id     | Unique identifier for each user             | INT        |
| order_weekday | Day of the week (1=Monday, 7=Sunday)      | INT        |
| order_time  | Exact time of breakfast order placement    | TIME       |
| preferred_breakfast | Common breakfast category chosen    | STRING     |

#### 2. **BreakfastMenu**

| Column Name  | Description                               | Data Type  |
|--------------|-------------------------------------------|------------|
| restaurant_id| Unique identifier for each restaurant     | INT        |
| dish_name    | Name of the breakfast dish                | STRING     |
| prep_time    | Time taken to prepare the dish (minutes)  | INT        |
| dish_type    | Category (e.g., Vegan, Continental, etc.) | STRING     |

#### 3. **DeliveryMetrics**

| Column Name   | Description                             | Data Type  |
|---------------|-----------------------------------------|------------|
| order_id      | Unique identifier for each order        | INT        |
| route_duration| Estimated route time (minutes)          | INT        |
| traffic_conditions | Traffic conditions (Light, Moderate, Heavy) | STRING |

## Questions

1. **Data Manipulation & Cleaning**: Consider the `BreakfastPatterns` table. People's breakfast habits vary by the day of the week. Aggregating by weekday, identify the top 3 `preferred_breakfast` categories for each day. For instance, are weekends more indulgent with pastries compared to weekdays?

2. **Probability and Statistics**: Using data from `DeliveryMetrics`, can you find any statistically significant trend in route_duration on Mondays when people might be rushing to work, leading to traffic, compared to lazy Sundays?

3. **Machine Learning & Modeling**: Given the historical ordering data from BreakfastPatterns table which records users' preferences for different breakfast types and their ordering habits, design a clustering model that groups users with similar breakfast tastes. Here are some hints for your analysis:
     - How would you preprocess and encode the data to make it suitable for clustering?
     - Which distance metric would you choose considering the nature of the data and why?
     - How would you validate the quality of the identified clusters in the absence of ground truth labels?

4. **Product Design & Analytics**: Having clustered the Uber Eats users based on their breakfast tastes using the `BreakfastPatterns` table, you've identified distinct user segments that show homogeneous preferences within each cluster. Given the clusters you've identified, how would you suggest the marketing team to leverage this segmentation to promote Uber's breakfast service? Give your recommended feature, and design an experiment to measure the effectiveness of your feature. Here are some hints for your analysis:
    - What star metrics and guardrail metrics you would use for the experiment?
    - How to validate if the order volume increase is due to these personalized promotions and not due to external factors? Discuss potential pitfalls or biases that could affect the results of your experiment and how you would account for them.
    - If the metric showed significant improvement in one segment but not in others, what further investigations or actions would you suggest?
