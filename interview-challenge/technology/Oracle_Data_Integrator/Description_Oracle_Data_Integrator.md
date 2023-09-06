# **Business Problem Statement**:

Oracle's integration suite has been widely used by many enterprise-level clients, and they've been collecting data regarding performance metrics, user interaction, and system logs. There is a rising need to predict the system's response time based on various input metrics to enhance user experience and to understand which factors contribute most to any delays or lags.


## **Data Table**:

**Info_data**

| Column Name   | Description                                            | Feature Type    |
|---------------|--------------------------------------------------------|-----------------|
| `user_id`     | Unique identifier for each user                        | Categorical     |
| `session_id`  | Unique identifier for each session                     | Categorical     |
| `timestamp`   | Time of the record                                      | DateTime        |
| `system_load` | Load on the system in percentage (0-100%)              | Numerical       |
| `queries`     | Number of queries made during the session              | Numerical       |
| `db_size`     | Size of the database at the time of the session (GB)   | Numerical       |
| `errors`      | Number of errors encountered during the session        | Numerical       |
| `response_time`| Time taken to respond to a query (in ms)               | Numerical (Target) |
| `integration_tool`| Whether ODI or GoldenGate was used                  | Categorical     |
| `user_type`   | Type of user (admin, developer, general user)          | Categorical     |


## **Questions**:

1. **Data Manipulation & Cleaning**:
   
   During a session analysis, you notice there are some records with extreme `response_time` values, likely due to system glitches. Identify sessions where the `response_time` seems like an outlier, and propose a strategy to handle them.
   

2. **Probability and Statistics**:
   
   Given the data collected over the past year, determine if there's a statistically significant difference in `response_time` when using Oracle Data Integrator (ODI) compared to Oracle GoldenGate.

3. **Machine Learning & Modeling**:
   
   Scenario: The response time is crucial for maintaining a high-quality user experience. Using the available data, create a model to predict `response_time` based on the input features. Clearly specify the feature importance once the model is trained.
   
   **Target Variable**: `response_time`
  

4. **Business Context**:
   
   Among the user types (`admin`, `developer`, `general user`), identify which group encounters the most errors during their sessions. Further, determine if this has a significant impact on `response_time`.

