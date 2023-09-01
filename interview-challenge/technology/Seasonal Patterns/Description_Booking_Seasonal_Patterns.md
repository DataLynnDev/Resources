# **Business Problem Statement:**
Booking is trying to leverage its vast troves of data to understand the seasonal booking patterns of its customers. By predicting the seasonal demand for hotel bookings across various regions, Booking can optimize its inventory, adjust marketing strategies, and provide better recommendations to its users. The challenge here is to uncover these patterns and design strategies based on time series analysis.

## **Data Table:**

**Info_data**

| Column Name | Description | Feature Type |
|-------------|-------------|--------------|
| booking_id | Unique ID for each booking | Categorical |
| hotel_id | Unique ID for each hotel | Categorical |
| user_id | Unique ID for each user | Categorical |
| booking_date | Date when the booking was made | Date |
| stay_date | Date when the user will stay at the hotel | Date |
| price | Price of the booking | Continuous |
| region | Region of the hotel | Categorical |
| rating | Rating of the hotel | Continuous |
| user_intent | Reason for booking (e.g. Leisure, Work) | Categorical |
| was_stayed | Indicates if the user stayed or not (0 = no, 1 = yes) | Binary |
| number_of_bookings | Estimated count of bookings for a given date in the Europe region | Continuous|

## **Questions:**

1. **Data Manipulation & Cleaning**:
    - *Scenario*: Often the same hotel gets booked for multiple dates by various users. To understand demand patterns, we need to aggregate the data not just by region but also by the purpose of the stay (`user_intent`).
    **Question**: Aggregate the booking data by `region` and `user_intent`. Calculate the total number of bookings and the average price for each group (region and user_intent combined). What are the top 5 groups (combinations of region and user_intent) by average booking price during the peak travel season (June - August)?

2. **Probability and Statistics**:
    - *Scenario*: Given the nature of hotel booking, there might be days with unusually high or low bookings which might be anomalies.
    **Question**: Using the bootstrap method, calculate the 95% confidence interval of the mean number of bookings for the month of December. Is the actual mean within this interval?

3. **Machine Learning & Modeling**:
    - *Scenario*: To aid in promotional activities, you decide to predict the number of bookings for a given 'stay_date' and 'region'.
    **Question**: Build a time series model to predict the number of bookings for the next 30 days in the "Europe" region. Specify which features you'd use and why. Also, explain how you would validate this model, ensuring that it's not overfitting.  

4. **Product Design & Analytics**:
    - *Scenario*: One of the key features for users is the 'Value for Money' tag on hotel listings. This feature becomes even more crucial during peak seasons.
    **Question**: Design an algorithmic approach to automatically tag a hotel listing as 'Value for Money' during the peak season, considering factors like price, region, and rating. Explain how this will be beneficial in driving more bookings. Also, if you were to run an A/B test on this feature, how would you set it up and evaluate its success?  

