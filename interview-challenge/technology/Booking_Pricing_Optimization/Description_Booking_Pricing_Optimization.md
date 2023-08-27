# Business Problem Statement:
Booking.com wants to refine its dynamic pricing strategies for hotels, ensuring that pricing remains competitive based on various factors such as demand, competitor prices, historical booking data, and seasonal trends. The aim is to maximize revenue while ensuring customer satisfaction. The challenge is to utilize optimization algorithms to make dynamic pricing decisions based on the given data.

## Data Tables:

**Table Name:** `hotel_data`

| Column Name       | Description                                               | Feature Type     |
|-------------------|-----------------------------------------------------------|------------------|
| hotel_id          | Unique identifier for the hotel                           | Categorical      |
| demand_score      | Score indicating the demand for the hotel (0 to 100)      | Continuous       |
| competitor_price  | Average price of nearby competitors                       | Continuous       |
| previous_bookings | Number of bookings in the last month                      | Discrete         |
| seasonal_trend    | Multiplier based on time of year (e.g., 1.5 for peak season) | Continuous      |
| current_price     | Current price of the hotel room                           | Continuous       |
| customer_rating   | Average rating given by customers (1 to 5 stars)          | Continuous       |
| room_type         | Type of room (e.g., single, double, deluxe)               | Categorical      |

**Table Name:** `booking_history`

| Column Name       | Description                                               | Feature Type     |
|-------------------|-----------------------------------------------------------|------------------|
| booking_id        | Unique identifier for the booking                         | Categorical      |
| hotel_id          | ID of the hotel booked                                    | Categorical      |
| booked_price      | Price at which the room was booked                        | Continuous       |
| date_of_booking   | Date on which the booking was made                        | DateTime         |
| stay_duration     | Duration of the stay in days                              | Discrete         |

### Questions:

1. **Scenario:** Booking.com has identified that certain hotels are consistently priced higher than their competitors but still manage to maintain a high demand. How would you identify such hotels, and how can the pricing model be refined to maximize revenue without affecting demand too negatively?


2. **Scenario:** It has been noticed that during certain periods of the year, the demand for some hotels surges, affecting their pricing. Using the `seasonal_trend` and `demand_score` columns, can you design an ML model to predict `current_price` for a given hotel? Ensure to validate the model and handle any non-linearity in the relationship.

    - Note: Target variable is `current_price` and its type is continuous.

3. **Scenario:** A new strategy is being proposed: to adjust the hotel prices based on the average booked price from the `booking_history` table in the last week, particularly for those hotels with high `demand_score`. Describe the steps and techniques you would employ to test this strategy using A/B testing.


4. **Scenario:** Booking.com is interested in launching a new feature called "Value Picks". Using the available data, especially the `customer_rating`, `current_price`, and `competitor_price` columns, how would you identify hotels that offer the best value for money? Once identified, how would you evaluate the success of this feature from a business perspective?
