## Business Problem Statement ##

UberPool operates on the premise of ride-sharing, where multiple passengers traveling in similar directions share the same ride. This not only reduces cost per passenger but also optimizes vehicle occupancy and reduces traffic congestion. To maximize the effectiveness of this model, we need to efficiently match riders heading in the same direction while ensuring minimal detours and delays for all passengers.


## Dataset Description ##

1. 'RiderRequestData'

| ride_request_id | timestamp | pickup_location | dropoff_location | rider_id |
|-----------------|-----------|-----------------|------------------|----------|
| 1               | 2023-07-01 07:15:00  | (40.748817, -73.985428) | (40.758896, -73.985130) | 3435     |
| 2               | 2023-07-01 07:20:00  | (40.7829, -73.9654) | (40.755102, -73.972333) | 8765     |
| 3               | 2023-07-01 07:25:00  | (40.7613, -73.9771) | (40.752650, -73.977245) | 7654     |
| 4               | 2023-07-01 07:30:00  | (40.7330, -73.9881) | (40.748817, -73.985428) | 8965     |
| 5               | 2023-07-01 07:35:00  | (40.7243, -74.0115) | (40.7619, -73.9663) | 6432     |

- ride_request_id: Unique identification for the ride request.
- timestamp: The time when the ride request was made.
- pickup_location: The GPS coordinates for the pickup location.
- dropoff_location: The GPS coordinates for the dropoff location.
- rider_id: Unique identification for the rider who made the request.

2. 'DriverAvailabilityData'

| driver_id | timestamp | location | status |
|-----------|-----------|----------|--------|
| 1         | 2023-07-01 07:15:00  | (40.7449, -73.9913) | Available |
| 2         | 2023-07-01 07:20:00  | (40.7531, -73.9789) | Busy     |
| 3         | 2023-07-01 07:25:00  | (40.7393, -73.9849) | Available |
| 4         | 2023-07-01 07:30:00  | (40.7522, -73.9771) | Available |
| 5         | 2023-07-01 07:35:00  | (40.7397, -73.9883) | Busy     |

- driver_id: Unique identification for the driver.
- timestamp: The time when the driver's status was recorded.
- location: The GPS coordinates for the driver's location.
- status: The status of the driver (e.g., Available, Busy, Offline).

3. 'RideData'

| ride_id | driver_id | rider_ids | pickup_locations | dropoff_locations | start_time | end_time | fare | distance | status |
|---------|-----------|-----------|------------------|-------------------|------------|----------|------|----------|--------|
| 1       | 2         | 3435 | (40.748817, -73.985428) | (40.758896, -73.985130) | 2023-07-01 07:30:00  | 2023-07-01 07:45:00  | 25.00 | 2.5 | Completed |
| 1       | 2         | 7654 | （40.7613, -73.9771) | (40.752650, -73.977245) | 2023-07-01 07:35:00  | 2023-07-01 07:40:00  | 10.00 | 1.2 | Completed |
| 3       | 4         | 6432 | (40.7330, -73.9881) | (40.748817, -73.985428) | 2023-07-01 07:45:00  | 2023-07-01 08:00:00  | 30.00 | 3.0 | Completed |
| 4       | 5         | 8765 | (40.7613, -73.9771) |  (40.755102, -73.972333) | 2023-07-01 07:50:00  | 2023-07-01 08:05:00  | 25.00 | 2.5 | Completed |
| 5       | 1         | 3435 | (40.748817, -73.985428) | (40.758896, -73.985130) | 2023-07-01 07:55:00  | 2023-07-01 08:00:00  | 10.00 | 1.2 | Completed |

- ride_id: Unique identification for the ride.
- driver_id: The ID of the driver who accepted the ride.
- rider_ids: The IDs of riders who shared the ride.
- pickup_locations: The GPS coordinates for the pickup locations of all riders.
- dropoff_locations: The GPS coordinates for the dropoff locations of all riders.
- start_time: The start time of the ride.
- end_time: The end time of the ride.
- fare: The total fare charged for the ride.
- distance: The total distance of the ride in miles.
- status: The status of the ride (e.g., Completed, Cancelled, In-progress).


## Data Challenge ##


### 1. Demand and Supply Analysis

Utilizing the available historical data in the 'RiderRequestData', 'DriverAvailabilityData', and 'RideData' tables, analyze and visualize the temporal and spatial patterns of demand and supply for UberPool services in a given city. Explain any observed patterns and trends. What factors seem to influence the demand and supply of rides?


**Solution 1:**
We can start this analysis by exploring the temporal patterns of the demand and supply. To do so, we will group the data by hour of the day, day of the week, and month of the year. For spatial patterns, we can create heat maps using the latitudes and longitudes from 'pickup_location' and 'dropoff_location' for demand, and 'location' for supply. We also need to consider 'status' in 'DriverAvailabilityData' to determine actual supply.

## 2. Metrics For a Good CarPool

What metrics could help evaluate the efficiency of the matching algorithm. Discuss why you chose these particular metrics, how to calculate them, and what insights they provide about the algorithm's performance.

**Solution 2:**

We can define several metrics to evaluate the efficiency of the matching algorithm.

1. Occupancy Rate: For a ride-sharing service like UberPool, the occupancy rate will typically be measured as the number of passengers in the vehicle per ride, on average, during the duration of a single trip.

    **Math**: `Occupancy Rate = Number of passengers per ride / Number of rides`

   If the occupancy rate is above a certain threshold, it means that rides are generally shared by more than one passenger, leading to better utilization of vehicles and potentially greater profits.

2. Detour Time: In the context of ride-sharing services, detour time is an important aspect to consider. It is the additional time spent by a passenger on the road due to the route taken to pick up or drop off other passengers. It can be calculated as the difference between the time it would take to travel directly from the pickup to the drop-off location and the actual travel time.

    **Math**: `Detour Time = Actual Ride Time - Direct Ride Time`

   Ensuring that the detour time does not exceed a certain limit is important to maintain customer satisfaction, as excessive detours may result in passengers opting not to use the ride-sharing service.


3. Wait Time: This is the time from when a passenger requests a ride to when the ride actually starts.

   **Formula**: `Wait Time = Pickup Time - Request Time`

   Shorter waiting times improve customer satisfaction, and thus it is desirable to minimize this metric. It shows how quickly the algorithm can match a driver to a passenger.


4. Load Balance: This metric represents the uniformity in the distribution of rides among drivers. It can be calculated as the standard deviation of the number of rides per driver.

   **Formula**: `Load Balance = Standard Deviation(Rides per driver)`

   A lower load balance value indicates a more equitable distribution of work among drivers. This means that the algorithm is fair in assigning rides to drivers, preventing some drivers from being overworked while others have few rides.

These metrics, taken together, give a comprehensive picture of the matching algorithm's efficiency. Optimizing these metrics should lead to better utilization of resources, increased driver earnings, lower passenger wait times, and a smoother ride-sharing operation.

However, it's worth noting that while these metrics aim to improve the overall system, individual preferences and circumstances can vary widely, and some trade-offs might be necessary. For instance, achieving a high occupancy rate might increase detour time, and maintaining low detour times might decrease occupancy rates. Balancing these opposing factors is a key challenge in designing effective matching algorithms.



## 3. Matching Algorithm Design

From the previous question, you already knew what are important things to consider when designing a carpool strategy. Continuing on your great work, please design an algorithm to match riders with drivers for the UberPool service. Clearly define your objective and constraints. Explain your proposed approach and the rationale behind your design.


**Solution  3:**
Here's how we can incorporate those constraints into the formulation:


**Objective Function:**  
Our primary objective here is to minimize the average travel time for all passengers.


**Constraints:**

1. Each passenger can only be assigned to one ride (with possibly multiple other passengers).
2. Each ride can only have at most the vehicle's capacity of passengers.
3. The **detour time** of any passenger should not exceed a certain limit. The detour time can be calculated by the difference in time between the direct route to the passenger's destination and the time it takes when other passengers are considered.
4. The total **number of rides a driver can take** should be balanced. We can set a lower and upper limit on the number of rides each driver can take to avoid overloading or underutilizing any driver.
5. The **waiting time** for any passenger should not exceed a certain limit. The waiting time can be calculated as the difference between the time a passenger requests a ride and the time their ride starts.
6. The **average occupancy rate per ride** should be above a certain threshold. This constraint ensures that most rides are shared rides with more than one passenger, which is the core premise of the UberPool service.


One challenge here is to find the optimal trade-off between maximizing the occupancy rate and minimizing the ride time, which can be conflicting objectives. In other words, increasing the occupancy rate by assigning more passengers to a ride may increase the total ride time due to detours.

The first 2 constraints are hard constraints, whereas the last 4 are soft constraints that needs tuning based on estimation of customer sensitivity to the various factors. The addition of constraints on the waiting time of passengers and the average occupancy rate per ride further complicates the problem but also makes the solution more practical and aligned with the objectives of a ride-sharing service. The waiting time constraint ensures that the service is responsive and meets the expectations of passengers for a quick pickup, while the average occupancy rate constraint ensures that the service is efficient in terms of resource usage and environmental impact.


This problem is essentially a variant of the Vehicle Routing Problem (VRP), which is a well-known problem in operations research and combinatorial optimization. Specifically, it's a form of the Capacitated Vehicle Routing Problem (CVRP) with time windows (CVRPTW), where the capacity of the vehicle is the maximum number of passengers it can take and the time windows represent the pickup and dropoff times of passengers. We can use various optimization techniques or algorithms to solve this problem, including integer programming, metaheuristics (like Genetic Algorithm, Simulated Annealing, or Tabu Search), or machine learning approaches.

To make this problem tractable and solvable in real time, it may be necessary to use heuristics or approximation algorithms, given that VRPs are NP-hard problems and can't be solved optimally within a reasonable time frame for a large number of passengers and vehicles.


## 4. Estimating Ride Fee for UberPool

Uber, and similar rideshare services, would certainly have a formula or model for calculating the ride fee for a carpool service. The fee typically takes into account distance, duration, base fare, and demand at the time of ride request. This is usually implemented as part of a dynamic pricing model.

However, there are several reasons why Uber may be use machine learning model to predict ride fees:

1. Dynamic Pricing Refinement: By comparing predicted prices with actual prices, Uber can uncover insights to refine and improve their pricing algorithms. Machine learning models can find hidden patterns and relationships that may not be apparent or considered in the initial formula-based model.

2. Operational Efficiency: Predicting ride fees can also help in capacity planning and demand forecasting. For instance, if high fares are predicted for a particular area at a particular time, it can signal high demand. Uber can use this information to efficiently allocate drivers to meet this demand.

How can we accurately estimate the ride fee for UberPool, considering factors such as the number of riders, total distance, individual passenger drop-off points, potential detours, and delays? Your solution will enhance our business model's sustainability, customer satisfaction, and contribute to the overall mission of making transportation easier and more affordable.

**Solution 4:**
**Interpretation of the plot:**

The most important feature is distance_pickup_dropoff. This implies that the distance between the pickup and dropoff locations has the highest impact on estimating the fare for UberPool rides. This makes intuitive sense, as longer distances typically lead to higher fares.

The second most important feature is number of riders in the ride. The number of riders in the ride also plays a significant role in fare estimation. More riders generally result in a lower fare, and the result also proves one of UberPool's core idea: providing affordable and convienient service for people asking for a carpool.

Then it comes to waiting_time. Longer waiting time generally result in a higher fare.

The other features have relatively lower importance values. For longtitute and latitude, the information is already encoded in the distance, so they are sort of redundant.

By analyzing the feature importances, we gain insights into which factors are most influential in predicting the fare for UberPool rides. This understanding can help in making informed decisions to enhance the fare estimation model and optimize the UberPool service for better customer satisfaction and cost efficiency.

### 5. Economies of Scale Analysis

Does your carpool model satisfy the concept of economies of scale? Economies of scale, in simple terms, refers to the cost advantage that is achieved with increased output of a product. Give your definition of “economies of scale” in the UberPool business and how you would investigate into the problem.

**Solution 5:**  

In the context of the UberPool business, "economies of scale" can be defined as the cost advantage or efficiency gained by the company as the number of riders sharing a ride increases. This means that as more passengers participate in a single UberPool ride, the average cost per passenger decreases, leading to a potentially lower overall cost for each rider compared to individual Uber rides. Achieving economies of scale in the carpool model is crucial for UberPool's sustainability and the overall mission of making transportation easier and more affordable.


To achieve this, we'll consider the following cost components for each UberPool ride:

1. Driver's labor cost: The driver's labor cost includes the time and effort spent by the driver to complete the ride. As the number of riders increases, the driver's labor cost can be distributed among more passengers, potentially reducing the cost per rider.

2. Car's ride cost: The car's ride cost is primarily determined by the distance the car travels to complete the ride. With more riders sharing the same ride, the car travels more efficiently, and the distance per rider decreases, leading to potential cost savings.

The total cost per ride is the sum of the driver's labor cost and the car's ride cost. By analyzing how the total cost per ride changes with an increase in the number of riders, we can determine whether economies of scale are achieved.


If the total cost per ride decreases as the number of riders increases, it indicates a cost advantage with increased output, supporting the concept of economies of scale. This would mean that UberPool is effectively reducing costs for riders by offering shared rides. To make the comparison, we could assume all the rides only takes 1 rider. Compute the cost under such hypothesis and get our desired metric, which is average cost per ride. Then, calculate the metric on real carpool data and compares.

It is essential for UberPool to continuously analyze and optimize its cost structure and pricing strategies to ensure that economies of scale are realized. By doing so, UberPool can enhance its value proposition to customers, improve cost-efficiency, and contribute to making transportation more accessible and affordable for a broader audience.

