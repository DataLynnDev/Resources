## Uber Data Scientist Mock Interview
  The goal of the data challenge is to assess the candidate's skills in SQL syntax, experiment design, feature selection and modeling. The candidates will be asked a series of questions related to these aspects with PySpark coding skills, utilizing the provided dataset.

## Business Problem

Uber needs insights from its trip data to improve ETA predictions and customer satisfaction. Additionally, the impact of a new "Streak Bonus" feature for drivers needs to be assessed. Finally, the company seeks to understand the factors influencing driver activity levels and wants to predict a new driver's trip count.

## Questions Roadmap

- SQL syntax
	- Calculate the mean and standard deviation
	- Calculate percentage of rides with higher rating
- Experiment Design
	- Propose a measurable definition
	- Design Experiment to test engagment increase
- Data Analysis in Python
	- Analyze feature pattern
	- Use regression model to predict feature `total_trips`

## Dataset Information
### Dataset for part 1 problems
**Assume a PostgreSQL database, server timezone is UTC.**

Table Name: **`trips`**

|Column Name:|Datatype:|
| :-: | :-: |
|`id`|integer|
|`client_id`|integer (Foreign keyed to `events.rider_id`)|
|`driver_id`|integer|
|`city_id`|integer (Foreign keyed to `cities.city_id`)|
|`client_rating`|integer|
|`driver_rating`|integer|
|`request_at`|Timestamp with timezone|
|`predicted_eta`|integer|
|`actual_eta`|integer|
|`status`|Enum(‘`completed`’, ‘`cancelled_by_driver`’, ‘`cancelled_by_client`’)|


Table Name: **`cities`**

|Column Name:|Datatype:|
| :-: | :-: |
|`city_id`|integer|
|`city_name`|string|

### Dataset for part 3 problems

Table Name: **`drivers`**

| Field | Description |
|-------|-------------|
| id | Driver ID |
| city_id | ID of the city where the user signed up |
| signup_os | Signup device of the user (possible values: "android", "ios", "website", "other") |
| signup_channel | Channel from which the driver signed up (possible values: "offline", "paid", "organic", "referral") |
| signup_timestamp | Timestamp of account creation, represented in local time in the form 'YYYY/MM/DD' |
| bgc_date | Date of background check consent, represented in the form 'YYYY/MM/DD' |
| vehicle_added_date | Date when driver's vehicle information was uploaded, represented in the form 'YYYY/MM/DD' |
| first_trip_date | Date of the first trip as a driver, represented in the form 'YYYY/MM/DD' |
| vehicle_make | Make of vehicle uploaded (e.g., Honda, Ford, Kia) |
| vehicle_model | Model of vehicle uploaded (e.g., Accord, Prius, 350z) |
| vehicle_year | Year that the car was made, represented in the form 'YYYY' |
| total_trips | Total trips taken by the driver in the past year |


Please note that this data is fake and does not represent actual driver signup behavior
## Solution Overview

### Part 1 - SQL Syntax
#### Q1 Answer: 
1. It imports the necessary libraries, `sqlite3` and `pandas`.
2. It establishes a connection to an in-memory SQLite database.
3. It converts Pandas dataframes (`trips` and `cities`) into SQL tables within the database.
4. It defines an SQL query that calculates mean and standard deviation differences between columns in the `trips` table.
5. It executes the query and stores the results in a Pandas dataframe (`result1`).


#### Q2 Answer:
The provided code performs analysis on a dataset stored in an SQLite database. It executes an SQL query to calculate the percentage of trips with a client rating above 4 for each day of the week, within a specific date range, and for specific cities ('Qarth' and 'Meereen'). The results are stored in a Pandas dataframe. The code then closes the database connection and displays the resulting dataframe (`result2`). The query uses the `strftime()` function to extract the day of the week from the `request_at` column in the `trips` table.

### Part 2 - Experiment and Metrics Design

#### Q3 Answer:
Shown in notebook.

#### Q4 Answer:
Shown in notebook.

### Part 3 - Data Analysis in Python

#### Q5 Answer:
To understand the differences in activity levels among drivers, we need to explore various features in the dataset that could potentially influence these activity levels. For example, we can consider the following features:
1. signup_os
2. city_id
3. vehicle_year

**GroupBy Analysis**

We can group the data by categorical features and calculate the average 'total_trips' for each group. This can give us insights into which categories have higher activity levels.

#### Q6 Answer:
The provided Python code conducts data pre-processing, feature encoding, data splitting, and model training for a prediction task. It converts four datetime columns to numeric format by calculating elapsed days since 2010. Original datetime columns are then dropped. Categorical variables are one-hot encoded, and the resulting encoded features are concatenated with the remaining dataset. The data is then split into a training set and a testing set. It scales the features using StandardScaler for better model performance. A Gradient Boosting Regressor is trained, predictions are made on the test set, and Mean Squared Error is computed for both training and testing sets to evaluate the model.



