# **Business Problem Statement**:
Apple's iPhone team is keen on understanding the relationship between device performance, user feedback, and sales trends. The team believes that by analyzing these factors, they can provide better hardware improvements, optimize market segmentation, and devise effective sales strategies. The data analyst's role would be to extract insights from the data to guide these decisions.

## **Data Tables**:

**Table: DeviceDiagnostics**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| device_id    | Unique identifier for each device | int | Primary Key |
| manufacture_date | Date when the device was manufactured | date | |
| battery_health | Health of the device's battery in percentage | int | Range: 0-100 |
| storage_used | Storage used in GB | int | |
| ios_version | Version of iOS installed | varchar | |
| region | Region where the device is primarily used | varchar | |

**Table: UserFeedback**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| feedback_id  | Unique identifier for each feedback | int | Primary Key |
| device_id    | Identifier for the device | int | Foreign Key (references DeviceDiagnostics.device_id) |
| feedback_date | Date when the feedback was given | date | |
| feedback_type | Type of feedback | enum | Options: 'Positive', 'Neutral', 'Negative' |
| feedback_text | Detailed feedback from the user | varchar | |

## Questions

**Question 1**:
- *Topics and Operations*: Product Sales Analysis I (Joining tables, Select specific columns)
- *Scenario*: The iPhone team wants to understand the correlation between device performance and user feedback. Specifically, they are interested in devices that have a battery health below 50%.
- *Task*: Write a SQL query to retrieve the `device_id`, `battery_health`, `feedback_date`, and `feedback_type` for devices with a battery health below 50%.


**Question 2**:
- *Topics and Operations*: New Users Daily Count (Group by, Count, Date operations)
- *Scenario*: The iPhone team is interested in understanding the feedback trends over time. They believe that feedback received shortly after the manufacture date might be more about device performance, while feedback received later might be more about software or other issues.
- *Task*: Write a SQL query to count the number of feedbacks given within 30 days of the device's manufacture date. The result should show the `manufacture_date`, and the count of feedbacks.


**Question 3**:
- *Topics and Operations*: Build the Equation (String operations, Case When, Order By)
- *Scenario*: To improve user experience, the iPhone team wants to categorize the feedback text based on its length: 'Short' for feedback text with less than 50 characters, 'Medium' for 50-100 characters, and 'Long' for more than 100 characters.
- *Task*: Write a SQL query to display the `feedback_id`, `feedback_text`, and a new column named `feedback_length_category` that categorizes the feedback text based on its length as per the above criteria. The results should be ordered by `feedback_id`.
