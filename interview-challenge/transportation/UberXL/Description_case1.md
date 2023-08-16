# Business Problem Statement:

UberXL is a service designed for larger groups or families, offering rides in vehicles that can seat up to six people. However, UberXL is struggling with ride optimization, as there are often instances where smaller groups book these larger vehicles, leading to inefficient utilization of vehicle capacity. Uber is keen to understand the factors driving this behavior and wants to optimize the use of UberXL for larger groups while still maintaining a high level of customer satisfaction.

## Data Tables:

*Table 1: Ride_Details*

| Column Name | Description | Data Type |
| ----------- | ----------- | --------- |
| ride_id | Unique identifier for each ride | String |
| user_id | Unique identifier for each user | String |
| ride_time | Time of the ride | Datetime |
| group_size | Number of passengers in the ride | Integer |
| city | City where the ride took place | String |
| pickup_location | Location where the ride was requested from | String |
| dropoff_location | Destination of the ride | String |
| ride_duration | Duration of the ride in minutes | Integer |
| vehicle_type | Type of vehicle used for the ride (UberX, UberXL, etc.) | String |

*Table 2: User_Details*

| Column Name | Description | Data Type |
| ----------- | ----------- | --------- |
| user_id | Unique identifier for each user | String |
| user_city | City where the user is located | String |
| user_age | Age of the user | Integer |
| user_gender | Gender of the user | String |
| user_rating | User's average rating given by drivers | Float |

## Questions:

1. Given the data from 'Ride_Details' and 'User_Details', can you identify patterns or factors (such as time of ride, user age, user gender, user rating) influencing the utilization of UberXL for smaller groups? If a supervised classification algorithm was used to identify these factors, what business insights could you make based on the results?

2. Suppose Uber wants to conduct an A/B test to evaluate the effectiveness of a new feature aimed at promoting UberXL to larger groups. How would you design this experiment? What metrics would you use to evaluate the results?

3. Given the ride data, can you build a regression model to predict the likelihood of an UberXL being booked by a smaller group? What features would you include in your model and why?

4. Suppose Uber wants to personalize its app interface to promote UberXL to users who are more likely to travel in larger groups. How would you use the data to inform this product decision? What metrics would you track to measure the impact of this change?