# **Business Problem Statement:**
In an era of increasing energy demands, IBM seeks to harness the power of data to optimize energy consumption, reduce wastage, and lessen environmental impacts. For the energy sector, integrating weather data, consumption patterns, and equipment sensor readings can open avenues to improve energy production, distribution, and consumption. We invite you to take this challenge to showcase your data science skills in helping us achieve this objective.

## **Data Table:**

**`EnergyUsage`**

| Column Name       | Description                               | Feature Type      |
|-------------------|-------------------------------------------|-------------------|
| `EquipmentID`     | Unique ID for each piece of equipment     | Categorical       |
| `Timestamp`       | Date and time of the reading              | Datetime          |
| `Consumption`     | Energy consumption in kWh                 | Numerical         |
| `WeatherTemp`     | Temperature in Celsius                    | Numerical         |
| `EquipmentStatus` | Equipment operational status (On/Off)     | Categorical       |
| `SensorReading`   | Sensor reading indicating equipment health| Numerical         |
| `CustomerID`      | Unique ID for the customer using equipment| Categorical       |
| `Location`        | Geographical location of the equipment    | Categorical       |
| `WeatherCondition`| Weather conditions like sunny, cloudy, etc| Categorical       |
| `ProductionRate`  | Energy production rate in kWh             | Numerical         |

**Questions:**

1. **Scenario:** Given the diverse geographical spread, you notice that weather plays a significant role in energy consumption. Using the `EnergyUsage` dataset:
   - Identify the correlation between `WeatherTemp` and `Consumption`. How does weather impact energy consumption patterns?

2. **Scenario:** Due to recent anomalies in energy consumption, the team suspects certain equipment might be malfunctioning.
   - Rank the top 5 `EquipmentID` based on their average `Consumption`. Then, based on the `SensorReading`, determine if they are likely to be malfunctioning or just high consumers.

3. **Scenario:** Post-analysis, the team plans to forecast energy consumption using machine learning. But before that, it's essential to understand the data's nature.
   - Is the energy `Consumption` more influenced by a supervised or unsupervised learning approach, given the `WeatherCondition` and `EquipmentStatus`? Justify your answer.

4. **Scenario:** The business team is concerned about equipment performance in varied weather conditions.
   - Build a predictive model using the provided dataset to predict `Consumption` (target variable) based on the provided features. Comment on the importance of features like `WeatherCondition` and `SensorReading` on the model's prediction. (Hint: Consider feature importance methods.)
