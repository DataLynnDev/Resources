# **Business Problem Statement:**

Microsoft Azure Virtual Machines (VMs) have been widely adopted by various businesses for diverse purposes. However, ensuring optimal performance, cost-effectiveness, and high utilization is always a challenge. Given the vast amount of data that Azure VMs generate, it's crucial to use this data effectively to make informed decisions about VM management, optimization, and feature development. Our main objectives are to ensure that users get optimal performance from their VMs while ensuring cost savings, predict potential downtimes or lags, and offer insights for enhanced user experience.

## Data Table

**VM_Data**

| Column Name         | Description                                        | Feature Type        |
|---------------------|----------------------------------------------------|---------------------|
| VM_ID               | Unique ID for each VM                              | Categorical         |
| OS_Type             | Operating System of VM (Windows/Linux)             | Categorical         |
| CPU_Usage           | Percentage of CPU used by VM                       | Continuous          |
| Memory_Usage        | Percentage of memory used by VM                    | Continuous          |
| Storage_Read_Write  | Storage read and write speeds (in MB/s)            | Continuous          |
| User_Rating         | User rating for VM performance (scale of 1-10)     | Ordinal             |
| Downtime_Duration   | Duration of any VM downtime (in minutes)           | Continuous          |
| Monthly_Cost        | Monthly cost incurred for VM (in $)                | Continuous          |
| Session_Duration    | Average user session duration (in minutes)         | Continuous          |
| Error_Logs_Count    | Number of error logs generated in the past month   | Continuous          |

## **Questions:**

1. **Data Manipulation & Cleaning Question**
    * Scenario: In your initial exploration of the VM_Data, you notice anomalies in the `CPU_Usage` and `Memory_Usage` columns. The percentages occasionally exceed 100%.
    * Question: Identify VMs with `CPU_Usage` and `Memory_Usage` values exceeding 100% and propose a strategy for dealing with such anomalies.

2. **Probability and Statistics Question**
    * Scenario: User ratings provide feedback on VM performance, but we need to ensure that the feedback is not biased due to downtime.
    * Question: Given the user ratings and downtime durations, can you establish a probabilistic relationship between them? If a VM has a downtime of 10 minutes, what would be its expected user rating?

3. **Machine Learning & Modeling Question**
    * Scenario: Azure wants to provide a cost estimator tool for potential users. Based on historical data, the estimator will give potential monthly costs.
    * Question: Using the features in VM_Data, develop a model to predict the `Monthly_Cost`. Clearly define the target variable and its type. Additionally, which features have the most influence on the model's prediction?

4. **Product Design & Analytics Question**
    * Scenario: We're looking to enhance the Azure VM user experience. It is believed that long session durations may impact the VM's performance negatively.
    * Question: Analyze the correlation between `Session_Duration` and performance metrics such as `CPU_Usage`, `Memory_Usage`, and `User_Rating`. Based on your findings, propose modifications in VM design or settings to enhance user experience.

