# **Business Problem Statement:**
IBM's IoT solutions are working with a major manufacturer, "MachinoTech", to develop a system that optimizes their manufacturing processes using IoT devices. These devices generate vast amounts of data which can provide insights into machine efficiency, failure predictions, and supply chain improvements. Your role as a data scientist is to derive actionable insights from this data, which can help reduce costs, increase production uptime, and streamline processes.

## Data Table:
**`IoT_data`**

| Column Name          | Description                                                    | Feature Type         |
|----------------------|----------------------------------------------------------------|----------------------|
| device_id            | Unique identifier for each IoT device                          | Categorical          |
| timestamp            | Time when the data was recorded                                | Datetime             |
| machine_temperature  | Temperature of the machine                                      | Continuous           |
| machine_vibration    | Vibration measurement of the machine                            | Continuous           |
| product_quality      | Quality score of the product being manufactured (0 to 10)       | Continuous           |
| defective            | Whether the product was defective (1 for Yes, 0 for No)         | Binary               |
| supply_chain_status  | Status of the supply chain (Normal, Delayed, Critical)          | Categorical          |
| device_battery_level | Battery level of the IoT device (percentage)                    | Continuous           |
| device_location      | Location code where the device is installed                     | Categorical          |
| machine_operation    | Whether the machine was in operation (1 for Yes, 0 for No)      | Binary               |


## **Questions:**

1. **(Data Manipulation & Cleaning)**  
   Given the `IoT_data` table, which is laden with missing values and potential anomalies:
   - Identify and handle missing values for the machine_temperature and machine_vibration columns.
   - Spot and handle any potential outliers in the product_quality score.
    

2. **(Probability and Statistics)**  
   From the `IoT_data`, using data from devices located at 'location_code_X':
   - Calculate the probability that a product is defective.
   - Based on machine_temperature, can you infer if there's a significant difference in temperature when a product turns out to be defective?
    

3. **(Machine Learning & Modeling)**  
   Using the `IoT_data`, we want to create a predictive model:
   - Set 'defective' as the target variable.
   - Use relevant features from the dataset to predict if a product will be defective.
   - Once the model is built, explain the importance of each feature in predicting the defectiveness of a product.
    

4. **(Product Design & Analytics)**  
   MachinoTech has observed that certain IoT devices report a high number of defective products. Dive deep into the `IoT_data` to:
   - Identify any patterns related to specific devices or locations leading to higher defects.
   - Propose a solution or strategy to mitigate these defects based on the insights drawn from the data.