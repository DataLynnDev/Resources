# Interview Challenge -- Google map

## 1. Business Problem Statement

At Google Maps, our mission is to provide the most accurate, accessible and user-friendly mapping service in the world. As an integral part of this service, we aim to offer precise traffic predictions to enhance user's route planning and experience. In light of this, your task is to create a predictive model that forecasts traffic conditions in specific areas at specific times, to enable users to find the most efficient routes for their journeys. This model should consider a multitude of static and dynamic variables, including but not limited to, road attributes, historic traffic data, special events, and weather conditions.

To facilitate this, we provide two datasets: one is our Historical Traffic Dataset (HTD) and the other is a Road Attribute and Event Dataset (RAED).

## 2. Data Challenge Table

### Table 1: Historical Traffic Dataset (HTD)
|Column Header|	Description |
|---------------|---------------------------------------------------|
|Column Name |	Description |
|traffic_id	| Unique identifier for each traffic data point.|
|location_id	| Identifier for each specific location (interconnected with RAED).|
|timestamp	| The time at which the traffic data was recorded (YYYY-MM-DD HH:MM:SS).|
|speed	| Average speed of vehicles (km/h) at the given time.|
|volume	| Number of vehicles passing through the location at the given time.|
|congestion	| Congestion level(continuous variable). |

### Table 2: Road Attribute and Event Dataset (RAED)
|Column Header|	Description |
|---------------|---------------------------------------------------|
|location_id	| Identifier for each specific location (interconnected with HTD).|
|road_type	| Type of road - 'Highway', 'Main Road', 'Side Street', etc.|
|num_lanes	| Number of lanes on the road.|
|event_id	| Unique identifier for a specific event (like a concert, football match, etc.). Null if no event.|
|event_type	| Type of event if exists - 'Sporting', 'Concert', 'Festival', etc. Null if no event.|
|event_timestamp	| Start time of the event (YYYY-MM-DD HH:MM:SS). Null if no event.|
|weather	| Weather condition at the time - 'Sunny', 'Rainy', 'Snowy', etc.|

### Load data

## 3. Questions for the Data Challenge

### 3.1 Data Manipulation

- Given the Historical Traffic Dataset (HTD) and Road Attribute and Event Dataset (RAED), how would you merge these datasets to maximize the data's usefulness for traffic prediction? Consider issues like differing time granularities, missing values, and outlier handling.

- Since traffic data is temporal and location-based, how would you structure the data to capture this complex interplay? Describe a strategy to manage time series data with the spatial dimension.

**Ans** 3.1.1: 

- **Differing time granularities**: The HTD has a timestamp for each data point, whereas the RAED only has a timestamp for events. When merging, we may need to consider using the event_timestamp from the RAED table that is closest to, but not after, the timestamp from the HTD table. We could consider a technique called "Time-based Join" or "As-of Join", which matches the latest available record from the second table for each record in the first table based on time.

- **Missing Values**: There might be null values for the event-related columns in the RAED table when no events are happening. We can replace these nulls with a default value, for example, "No Event" for event_type and an out-of-range value for event_id (like -1), signaling the absence of an event.

- **Outlier Handling**: Outliers in traffic data could be due to unusual events or data collection errors. We can use statistical methods to detect these outliers, for instance, data points that fall outside of 3 standard deviations from the mean or based on Interquartile Ranges. After identifying outliers, we need to decide whether to discard them or replace them with certain values depending on the context.

Here's how you can do this in Python:

**Ans** 3.1.2: 

Managing Time Series Data with Spatial Dimension:

Since the data has both temporal and spatial dimensions, we might need to structure our data to account for these complexities:

- *Time-based Features*: To capture temporal patterns, we can create features based on timestamp such as hour of the day, day of the week, month, is it a holiday, etc. This can help the model to capture daily, weekly, and seasonal patterns in traffic.

- *Lag Features*: Traffic at a certain location and time often depends on traffic in the recent past. So we could add lag features, i.e., traffic volume, speed, or congestion level at the same location for the past few hours.

- *Spatial Features*: If we have geographical data about the locations, we can create spatial features. For instance, we can use the number of lanes, road type from the RAED dataset. If we have exact coordinates, we can also calculate distance-based features (like distance from major landmarks, city center, etc.).

- *Neighboring Location Features*: Traffic at a location could be influenced by traffic conditions in nearby locations. If we have data that allows us to understand the adjacency or closeness of different locations (like a graph), we can use traffic conditions at neighboring locations as features.

- *Event-Based Features*: Special events can have significant impacts on traffic. We already have event data in our RAED dataset, so we should use event_type as a categorical feature.

The structuring and feature engineering would depend on the exact requirement of the analysis and the available data, and we might need to revisit and revise it as we explore the data and build the model.

### 3.2 Metric Selection

- Given the unique problem statement, how would you create a custom evaluation metric that directly relates to our goal of minimizing travel time for users?

- How would you consider the business impact while selecting your metrics? For instance, how might the cost of under-prediction compare to the cost of over-prediction in terms of user satisfaction?

**Ans** 3.2.1: 

To create a custom evaluation metric that directly relates to our goal of minimizing travel time for users, we need to look at what factors affect travel time the most. Typically, these would be congestion and speed of traffic. Therefore, our metric needs to reflect how well our predictions capture variations in these factors.

- **Root Mean Squared Logarithmic Error (RMSLE)**: RMSLE is a good candidate for such a metric. It's useful when you want to penalize underestimates more than overestimates, as underestimating congestion or speed could lead to longer travel times than expected, a worse outcome for users. Additionally, the logarithmic component ensures that the metric is sensitive to the relative error rather than the absolute error, which is appropriate when dealing with time, as an error of 5 minutes matters more when the travel time is 10 minutes than when it is 60 minutes.

- **Mean Absolute Percentage Error (MAPE)**: MAPE measures the size of the error in percentage terms, which makes it a good choice when you want to understand how big the error is relative to the actual value. This can be useful in our case where we care about the relative accuracy of our congestion and speed predictions.

**Ans** 3.2.2: 

When considering the business impact while selecting metrics, we should consider the costs of under-prediction versus over-prediction. In our case:

- **Under-prediction** of congestion could mean that users are advised to take routes that end up being more congested than predicted. This could lead to increased travel time, user dissatisfaction, and loss of trust in the service.

- **Over-prediction** of congestion might make users take longer alternate routes, while their regular route was free. This also could lead to increased travel time and user dissatisfaction, but might be considered less severe than under-prediction because users may feel that the service is trying to ensure a consistently smooth journey, even if it errs on the side of caution.

Given these considerations, a potential custom metric could be a weighted version of RMSLE or MAPE, where under-predictions are penalized more heavily than over-predictions. This reflects the higher cost of under-prediction in terms of user satisfaction.

### 3.3 Feature Engineering

- Weather and traffic congestion are often correlated. How would you quantify this relationship and incorporate it into your features?

- Consider the temporal patterns in the data. How would you engineer features to capture patterns at different granularities (hourly, daily, monthly, annually)?

**Ans** 3.3.1: 

The relationship between weather and traffic congestion can be quantified using a method called "feature encoding". One of the simplest ways to do this is using one-hot encoding where we create a binary 'dummy' variable for each category of weather.

Let's consider the weather conditions: 'Sunny', 'Rainy', 'Snowy'. We could add these dummy variables to the HTD dataframe after merging it with the 'weather' column from the RAED dataset.

Afterward, a simple correlation analysis (for instance using Pearson's correlation) between these encoded variables and congestion could tell us about the linear relationship between weather conditions and congestion. If required, these variables can be further used to build predictive models.

**Ans** 3.3.2: 

Temporal patterns can be quite important in traffic prediction. We can create features that capture these patterns at different granularities:

- *Hourly*: Traffic patterns can change significantly throughout the day. Morning and evening rush hours, for instance, can be periods of high congestion. To capture this, we can extract the hour from the timestamp and use it as a categorical feature.

- *Daily*: Traffic patterns can also differ by day of the week. Weekdays and weekends can have very different traffic patterns, as can specific days of the week (like Friday evenings). We can extract the day of the week from the timestamp and use it as a categorical feature.

- *Monthly*: There can be monthly trends in traffic due to things like holidays or vacation periods. To capture this, we can extract the month from the timestamp and use it as a categorical feature.

- *Annually*: If we have multiple years of data, there can be annual trends (like less traffic in summer months when people are on vacation). To capture this, we can extract the year from the timestamp and consider it as a feature.

### 3.4 Model Selection

Establish a regression model to predict traffic conditions.

**Ans** 3.4:

Meanwhile, we can visualize the model's results with a confusion matrix and a ROC curve.

The confusion matrix visualizes the performance of the model in terms of true positives, true negatives, false positives, and false negatives.

The ROC curve visualizes the trade-off between the true positive rate (sensitivity) and the false positive rate (1-specificity). The area under the ROC curve (AUC) is a summary measure of the model's performance. The closer the AUC is to 1, the better the model's performance.

### 3.5 Model Optimization and Evaluation

- Discuss how you would improve your model. What techniques would you use and why?

- How would you approach the evaluation of model fairness and bias, considering that traffic conditions might affect different users unequally?

**Ans** 3.5.1

We could use Random Forest Regressor

**Ans** 3.5.2

Model fairness and bias in this context would likely refer to whether the model makes systematically worse predictions for certain user groups or under certain conditions. It's crucial to check this because if our model was trained on biased data or captures some societal biases, it may perpetuate or even amplify these biases.

To evaluate model fairness and bias, we would first need to define what these concepts mean in the context of our application. In this case, fairness might mean that the model's predictions are equally accurate regardless of the time of day, the day of the week, the road type, or any other factor that could affect different users unequally.

Once we have defined fairness, we can evaluate it by subgrouping our test set according to these factors and comparing the model's performance across the different subgroups. For example, we could calculate the model's mean absolute error separately for traffic data recorded at peak hours and off-peak hours and compare these values. If the model's error is significantly higher at peak hours, that might indicate a bias against users who travel at these times.

### 3.6 Business Insights

- Based on your model, what kind of interventions could Google Maps suggest to city planners to improve traffic conditions?

- How would you design a system to continuously evaluate the model's performance after deployment, and how would it inform you of any significant performance degradation?

**Ans**: 3.6.1

**Interventions for City Planners**

- *Road Infrastructure*: If the model indicates that certain road types or areas with fewer lanes consistently experience high congestion, this information could be used to propose the construction of additional lanes or even the restructuring of certain roads.

- *Event Management*: If events like concerts or festivals are found to contribute significantly to traffic congestion, city planners might be encouraged to explore more effective event traffic management strategies or staggered timing for large events.

- *Time Management*: If congestion is significantly higher at specific times (like rush hours), city planners could consider introducing policies like flexible work hours or promoting public transport to distribute traffic load more evenly throughout the day.

- *Weather*: If adverse weather conditions are found to contribute to traffic congestion, city planners could consider improving road infrastructure for such conditions (e.g., better drainage systems for rainy days) or creating public awareness about safe driving during these conditions.

**Ans**: 3.6.2

**Continuous Model Evaluation**

- *Data Monitoring*: Regularly monitor and log the inputs and predictions of the model. This data can help in diagnosing issues if the model's performance drops.

- *Performance Metrics*: Identify key performance metrics (accuracy, precision, recall, F1, etc.) and compute these metrics on a regular basis, such as daily or weekly. Comparing these metrics over time can help in identifying any degradation in performance.

- *Real-time Dashboards*: Implement real-time dashboards that visualize these key metrics over time and flag any significant changes.

- *A/B Testing*: When updating or tweaking the model, use A/B testing to compare the performance of the new model against the old one on live traffic.

- *Automated Alerts*: Set up automated alerts to notify you if the model's performance drops below a certain threshold or if the metrics change significantly in a short amount of time.