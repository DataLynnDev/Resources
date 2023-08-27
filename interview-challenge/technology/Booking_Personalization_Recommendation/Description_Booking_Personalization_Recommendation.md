# **Business Problem Statement:**
Booking is looking to improve the personalization of hotel recommendations for its users. They believe that by offering better personalized recommendations, they can enhance the user experience and thereby increase the likelihood of bookings. The challenge is to use the available data to develop a recommendation model that ensures that users see listings most relevant to their preferences and behaviors.

## **Data Table:**

**Info_data**

| Column Name      | Description                                          | Feature Type    |
|------------------|------------------------------------------------------|-----------------|
| user_id          | Unique identifier for each user                      | Categorical     |
| hotel_id         | Unique identifier for each hotel                     | Categorical     |
| booking_date     | Date when the booking was made                       | Date            |
| stay_duration    | Number of days the user stayed at the hotel          | Continuous      |
| hotel_type       | Type of the hotel (e.g., beach resort, city hotel)   | Categorical     |
| user_search      | User's search keyword or preference                  | Text            |
| previous_stays   | Number of previous stays by the user at the hotel    | Continuous      |
| user_rating      | Rating given by the user after their stay            | Continuous (1-5)|
| hotel_description| Short text description provided by the hotel         | Text            |
| hotel_price      | Price of the hotel per night                         | Continuous      |

**Questions:**

1. **Data Manipulation & Cleaning:** Booking has observed that certain hotel descriptions have excessive promotional text and less actual information about the hotel. Using the `hotel_description` column, can you identify such listings and suggest a way to rectify this?

2. **Probability and Statistics:** Given the `user_rating` and `previous_stays` for each `hotel_id`, estimate the confidence interval for the average rating of hotels using the bootstrap method. How can this interval help in understanding the consistency in service quality?

3. **Product Design & Analytics:** Users who haven't given a rating (`user_rating` is missing) after their stay are a concern. How can we incentivize them to provide feedback? Further, based on the feedback, propose a mechanism to highlight "Value for Money" hotels on the homepage.

4. **Progressive Question - Machine Learning & Modeling:** Using the model designed in Question 3, predict the likelihood of booking for each `user_search`. Now, given that some of these searches might result in a booking, how would you adjust the `hotel_price` to maximize the probability of bookings while ensuring profitability?