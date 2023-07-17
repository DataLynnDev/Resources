## Apple Data Scientist Mock Interview

### Business Problem Statement:

Apple is considering implementing a new feature in the App Store, that suggests apps based on customers' purchase history and browsing habits. As a data scientist at Apple, your challenge is to develop a predictive model that accurately recommends apps to customers. The two datasets provided consist of customer behavior data and app metadata.

### Questions Roadmap:

- Data Manipulation
	- Resampling and analyzing user activity data
	- Detecting and handling outliers in app ratings

- Feature Engineering
	- Calculating and integrating average user ratings
	- Extracting and analyzing time-related features from user interactions

- Model Questions
	- Data Preprocessing:
		- Preparing data for regression models
		- One-hot encoding for categorical data
		- Splitting the dataset into training and test sets
	- Modeling:
		- Constructing and evaluating a Linear Regression model
		- Constructing and evaluating a RandomForestRegressor model
		- Constructing, training, and evaluating a basic neural network model
		- Hyperparameter tuning of RandomForestRegressor model with GridSearchCV
	- Model Explainability:
		- Interpreting the predictions of the neural network model using SHAP values


**Table 1: User_Activity**

Column Name  | Description
-------------------|------------------
UserID (int) | A unique identifier for each user.
AppID (int) | A unique identifier for each app.
Interaction_Type (String) | Describes the type of interaction (e.g., 'Download', 'View', 'Review', 'Uninstall').
Interaction_Time (DateTime) | The timestamp of the interaction.


**Table 2: App_Info**

Column Name  | Description
-------------------|------------------
AppID (int) | A unique identifier for each app (matching the AppID in the User_Activity table).
Category (string) | The category the app belongs to (e.g., 'Productivity', 'Games', 'Health & Fitness').
Release_Date (DateTime) | The date the app was released on the App Store.
Average_Rating (float) | The average user rating of the app (from 1 to 5).
Size_MB (float) | The size of the app in megabytes.
Price (float) | The price of the app.
Downloads (int) | The total number of downloads for the app.

### Data Manipulation:

#### Q1_Answer:

This script is a process of data transformation and aggregation on a user activity log. The user_activity DataFrame, which records the interactions of users with different apps, is being analyzed.

The code first duplicates the original dataset to avoid any changes to the original data. It then adjusts the time-related data to a standardized DateTime format and reindexes the dataset by this interaction time.

The core of this script is grouping the user activities by user and app, then resampling it into a monthly frequency. It counts the interactions (assumed to be each row of data) for each user on each app every month, providing a monthly interaction count.

So, essentially, it converts a large and complex log of user activities into a clear, time-based summary of monthly user interactions with each app.


#### Q2_Answer:

This code is about handling outliers in a dataset of application information (app_info), specifically in the 'Average_Rating' column. Outliers are extreme values that deviate significantly from other observations in the data and can be due to variability in the data or errors.

The first part of the code calculates the interquartile range (IQR) for the 'Average_Rating'. The IQR is a measure of statistical dispersion and is calculated as the difference between the 75th percentile (Q3) and the 25th percentile (Q1) of the data.

Using this IQR, the code then defines what would be considered as outliers. Any 'Average_Rating' less than 1.5 times the IQR below Q1 (lower_bound) or more than 1.5 times the IQR above Q3 (upper_bound) is considered an outlier. These bounds are typical thresholds used in the IQR method for outlier detection.

Next, it identifies these outliers and prints out the number of outliers detected.

The last part of the code provides two options for handling outliers:

1. The first option removes these outliers from the dataset, resulting in a new DataFrame 'app_info_no_outliers' which doesn't contain these extreme values.

2. The second option doesn't remove the outliers, but instead limits their impact by capping and flooring them to the defined lower_bound and upper_bound respectively. This means that all 'Average_Rating' below the lower_bound are set to the value of lower_bound and those above the upper_bound are set to the value of upper_bound. This technique is also known as "winsorizing". The resulting DataFrame 'app_info_capped' still contains the same number of entries, but outliers have been adjusted.


### Feature Engineering:

#### Q3_Answer:

This code is manipulating two datasets, 'user_activity' and 'app_info', with the goal of calculating the average rating per user across all apps they interact with.

Initially, it merges the 'user_activity' and 'app_info' datasets based on the 'AppID' column, creating a combined dataset that links user activity with the corresponding app information.

Then, it groups the merged dataset by 'UserID' and calculates the average 'Average_Rating' for each user. This generates a dataset that lists each user and their corresponding average rating across all apps they've interacted with.

Finally, this average user rating data is merged back into the original (merged) dataset. This enriches the original dataset with a new feature, 'UserAvgRating', that provides an average rating for each user. This could be used for further analysis or modeling.


#### Q4_Answer:

This code is performing time-series manipulations on the merged_data DataFrame, which contains user activity data merged with app information.

First, it sorts the data by the 'Interaction_Time' column to ensure that the data is in chronological order.

Next, for each combination of 'UserID' and 'AppID', it creates a new column 'LastInteraction' that contains the time of the previous interaction. This is done using the shift() function which moves the 'Interaction_Time' values down by one row within each group.

The code then calculates the time elapsed since the last interaction for each row, in hours. This 'TimeSinceLastInteraction' could provide insights into user behavior patterns.

The 'DayOfWeek' column is then created by extracting the day of the week from 'Interaction_Time', with Monday encoded as 0 and Sunday as 6.

Finally, a new boolean column 'IsWeekend' is added, which indicates whether an interaction occurred on a weekend (Saturday or Sunday). This column is created by applying a function to the 'DayOfWeek' column that returns 1 if the day of the week is 5 (Saturday) or 6 (Sunday), and 0 otherwise.

Overall, this code is enriching the dataset with additional time-related features that can be useful for further analysis or predictive modeling.


### Model Questions:

#### Q5_Answer:

This code is implementing a basic machine learning pipeline to predict the 'Downloads' of applications using a linear regression model.

First, it applies one-hot encoding to the 'Category' column in the 'app_info' DataFrame, converting categorical data into a binary vector representation which can be used as input for the model.

The next step is a data cleaning process where irrelevant columns 'Category', 'Release_Date', and 'AppID' are dropped from the 'app_info' DataFrame.

Then, the 'app_info' DataFrame is split into input features (X) and target output (y), where 'Downloads' is the target to be predicted.

The dataset is then split into a training set and a test set using train_test_split(), with 80% of the data being used for training and 20% for testing.

A Linear Regression model is then created and fitted using the training data. The fitted model is used to predict the 'Downloads' for the test data.

Finally, the Root Mean Squared Error (RMSE), a measure of the differences between values predicted by the model and the actual values, is calculated and printed out. This serves as an evaluation of the model performance. The lower the RMSE, the better the model's performance.


#### Q6_Answer:

This code introduces a different machine learning model - the RandomForestRegressor - to predict the 'Downloads' in the 'app_info' dataset.

The RandomForestRegressor is a type of ensemble learning model which operates by constructing a multitude of decision trees at training time and outputting the average prediction of the individual trees. It's often more accurate than a single decision tree due to its ability to reduce overfitting.

A RandomForestRegressor model is instantiated with 100 decision trees (n_estimators=100) and then fitted on the training data. The model is then used to make predictions on the test data.

Finally, the RMSE is calculated for the RandomForestRegressor model's predictions. This is a commonly used metric that provides a measure of the model's prediction error. By comparing the RMSE from the RandomForestRegressor to the one obtained from the previous LinearRegression model, we can have an indication of which model performs better on this particular task.


#### Q7_Answer:


This code is building a basic feedforward neural network model using the Keras library in TensorFlow, training it on data, and then using SHAP (SHapley Additive exPlanations) to explain the predictions of the model.

The defined model consists of two layers: an input layer with 32 nodes and a ReLU activation function, and an output layer with 1 node, which is appropriate for regression tasks like predicting 'Downloads'.

The model is then compiled with the Adam optimizer and Mean Squared Error (MSE) as the loss function, both of which are commonly used choices for regression problems.

The model is trained on the input features (X_train) and target output (y_train) for 50 epochs with a batch size of 32.

Following this, a wrapper function is defined for the model's prediction method, and this function is used to create a SHAP explainer. This explainer is then used on the test data to compute the SHAP values. SHAP values interpret the impact of features on the model's output, attributing each feature with a value representing its contribution towards the prediction.

Finally, a force plot for the first prediction in the test data is generated. A force plot visualizes the SHAP values, showing how each feature pushes the model's output from the base value (the average prediction over the training dataset) to the actual model output.

In summary, this script is implementing a neural network for a regression task and then using SHAP values to interpret the model's predictions.


#### Q8_Answer:

This code uses Grid Search Cross Validation to find the best hyperparameters for a RandomForestRegressor model.

Grid Search is a method for hyperparameter tuning that builds and evaluates a model for each combination of algorithm parameters specified in a grid. In this case, the grid consists of different values for 'n_estimators', 'max_depth', and 'min_samples_leaf', which are key parameters for a random forest.

The GridSearchCV object performs a 5-fold cross-validation, meaning the training set is split into 5 subsets, and the model is trained and tested 5 times, each time using a different subset as the validation set. The performance metric used to evaluate the models is the negative mean squared error, which is simply the mean squared error negated. The model with the lowest negative mean squared error (i.e., the highest mean squared error) is considered the best.

After fitting the GridSearchCV object to the training data, the code then prints out the hyperparameters of the best model found and the corresponding root mean squared error.

Overall, this script aims to find the optimal hyperparameters for a RandomForestRegressor model to improve its performance on a regression task.






