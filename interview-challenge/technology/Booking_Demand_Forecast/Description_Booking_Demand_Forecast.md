# Business Problem Statement:

At Booking, the ability to forecast demand accurately for specific locations and accommodations types is crucial. Our platform needs a system that can predict spikes in demand, seasonal variations, and the effect of various external factors on demand. As a predictive analytics team, our goal is to ensure that our platform is always a step ahead, allowing our partners to optimize their pricing and inventory, and enabling us to manage resources efficiently.

## Data Tables:

**Table Name:** `Demand_Forecast`

| Column Name      | Description                                               | Feature Type       |
|------------------|-----------------------------------------------------------|--------------------|
| `location_id`    | Unique ID for each location                               | Categorical        |
| `date`           | Date for which the data is recorded                       | Date               |
| `demand_count`   | Number of bookings for that location and date             | Continuous         |
| `room_type`      | Type of room (e.g., single, double, suite)                | Categorical        |
| `avg_price`      | Average price for the room type on that date              | Continuous         |
| `special_event`  | If there is a special event near the location (0 or 1)    | Binary             |
| `prev_year_demand`| Demand from the same date the previous year               | Continuous         |
| `season`         | Season (e.g., spring, summer, autumn, winter)             | Categorical        |
| `reviews_avg`    | Average review rating of the location                    | Continuous         |
| `external_factor`| An index representing external factors affecting demand   | Continuous         |



## Questions:

1. **Scenario:** Upon analyzing the `Demand_Forecast` table, you notice some discrepancies in the `demand_count` for certain `location_id`s and `room_type`s.

   *Question:* Determine which location and room type combination has the highest inconsistency (variation) in `demand_count` over the past year. How would you handle such inconsistencies in your forecasting model?



2. **Scenario:** Booking has recently included the `external_factor` in the `Demand_Forecast` table. It's a combination of various factors like economic indices, competitor pricing, and travel restrictions that might impact the demand.

   *Question:* Given that this was not a standard setup before, how would you integrate the `external_factor` into your existing prediction model? What would the target variable be and how would you validate the new model?


3. **Scenario:** Upon seeing the influence of `special_event` on `demand_count`, the marketing team wants to run targeted campaigns on locations with upcoming special events.

   *Question:* Design an experiment to understand the impact of such targeted campaigns on `demand_count`. What are the important metrics to consider and how would you evaluate success?


4. **Scenario:** The revenue team is interested in understanding how `avg_price` fluctuations influence demand.

   *Question:* Considering `avg_price` as a potential predictor, how would you assess its relationship with `demand_count`? If the relationship isn't linear, what modeling strategies would you adopt?
