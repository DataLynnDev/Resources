# Business Problem Statement

At Google Maps, our mission is to provide the most accurate, accessible and user-friendly mapping service in the world. As an integral part of this service, we aim to offer precise traffic predictions to enhance user's route planning and experience. In light of this, your task is to create a predictive model that forecasts traffic conditions in specific areas at specific times, to enable users to find the most efficient routes for their journeys. This model should consider a multitude of static and dynamic variables, including but not limited to, road attributes, historic traffic data, special events, and weather conditions.

To facilitate this, we provide two datasets: one is our Historical Traffic Dataset (HTD) and the other is a Road Attribute and Event Dataset (RAED).

## Data Challenge Table

**Table 1: Historical Traffic Dataset (HTD)**

|Column Header|	Description |
|---------------|---------------------------------------------------|
|Column Name |	Description |
|traffic_id	| Unique identifier for each traffic data point.|
|location_id	| Identifier for each specific location (interconnected with RAED).|
|timestamp	| The time at which the traffic data was recorded (YYYY-MM-DD HH:MM:SS).|
|speed	| Average speed of vehicles (km/h) at the given time.|
|volume	| Number of vehicles passing through the location at the given time.|
|congestion	| Congestion level(continuous variable). |

**Table 2: Road Attribute and Event Dataset (RAED)**

|Column Header|	Description |
|---------------|---------------------------------------------------|
|location_id	| Identifier for each specific location (interconnected with HTD).|
|road_type	| Type of road - 'Highway', 'Main Road', 'Side Street', etc.|
|num_lanes	| Number of lanes on the road.|
|event_id	| Unique identifier for a specific event (like a concert, football match, etc.). Null if no event.|
|event_type	| Type of event if exists - 'Sporting', 'Concert', 'Festival', etc. Null if no event.|
|event_timestamp	| Start time of the event (YYYY-MM-DD HH:MM:SS). Null if no event.|
|weather	| Weather condition at the time - 'Sunny', 'Rainy', 'Snowy', etc.|

## Question:

**1: Data Manipulation**

 Given the Historical Traffic Dataset (HTD) and Road Attribute and Event Dataset (RAED), how would you merge these datasets to maximize the data's usefulness for traffic prediction? Consider issues like differing time granularities, missing values, and outlier handling.

 **2: Metric Selection**

 Given the unique problem statement, how would you create a custom evaluation metric that directly relates to our goal of minimizing travel time for users?

**3: Feature Engineering**

1. Weather and traffic congestion are often correlated. How would you quantify this relationship and incorporate it into your features?

2. Consider the temporal patterns in the data. How would you engineer features to capture patterns at different granularities (hourly, daily, monthly, annually)?

**4: Model Selection**

Establish a regression model to predict traffic conditions.

**5: Model Optimization and Evaluation**

1. Discuss how you would improve your model. What techniques would you use and why?

2. How would you approach the evaluation of model fairness and bias, considering that traffic conditions might affect different users unequally?

**6: Business Insights**

1. Based on your model, what kind of interventions could Google Maps suggest to city planners to improve traffic conditions?

2. How would you design a system to continuously evaluate the model's performance after deployment, and how would it inform you of any significant performance degradation?