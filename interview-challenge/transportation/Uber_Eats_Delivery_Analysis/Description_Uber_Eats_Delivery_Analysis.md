# **Business Problem Statement:**

Uber Eats is dedicated to providing a seamless experience for its customers, right from choosing the restaurant to delivering the food hot and fresh. As a part of its expansion, Uber Eats is interested in entering new cities and optimizing the existing ones. We want to understand restaurant preferences, optimize delivery routes, predict delivery time based on various factors, and enhance the overall user experience.

For this, Uber Eats has collected data on restaurants, deliveries, and user preferences. Your challenge is to derive insights and build models that can help in the areas mentioned above.

## **Data Tables**:

**1. Restaurants**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| restaurant_id | Unique ID for each restaurant | Integer |
| cuisine_type | Type of cuisine offered by the restaurant | String |
| avg_prep_time | Average preparation time for meals | Integer (minutes) |
| city | City where the restaurant is located | String |
| rating | Average rating given by users | Float |

**2. Deliveries**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| delivery_id | Unique ID for each delivery | Integer |
| restaurant_id | ID of the restaurant | Integer |
| user_id | ID of the user who placed the order | Integer |
| estimated_delivery_time | Estimated time for delivery | Integer (minutes) |
| actual_delivery_time | Actual time taken for delivery | Integer (minutes) |
| distance | Distance between user and restaurant | Float (miles) |

**3. UserPreferences**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| user_id | Unique ID for each user | Integer |
| preferred_cuisine | Preferred cuisine type | String |
| last_order_time | Last time user ordered | Datetime |
| avg_spending | Average spending per order | Float |

## **Questions**

1. **Restaurant Analysis**: Given the restaurant ratings and their average preparation time, can you identify if there's any correlation between the two? Specifically, do restaurants with quicker preparation times generally have better ratings? Also, identify which cuisine types are the most popular among users.
   
2. **Delivery Time Prediction**: Uber Eats wants to provide users with an estimated delivery time when they place an order. This helps in setting the right expectations and enhances the user experience. To achieve this, a prediction model needs to be built using the known data. First, only consider distance and the average preparation time. Then, add features you think will be useful and select model of your choice.
    
3. **User Experience Enhancement**: Suppose you were given feedback that users are often overwhelmed by too many restaurant choices. How would you use data to recommend a personalized shortlist of restaurants to a user on their next login, based on their preferences and order history?

4. **Surge Pricing Strategy**: Recently, some users complained about higher delivery charges during peak times. How would you use the data to optimize and explain the surge pricing mechanism for Uber Eats deliveries during high-demand periods? Can you design an experiment to test the effectiveness of this new surge pricing strategy? Define "effectiveness" and give your choice of metrics. (Hint: Do decrease in order means surge pricing is not good? Is customer data the only data we want to look at?)
