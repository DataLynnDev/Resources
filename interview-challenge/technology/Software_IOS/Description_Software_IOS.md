# **Business Problem Statement**:
Apple's iOS team is keen on understanding the user behavior on its mobile devices. With the increasing competition in the mobile market, it's crucial to understand how users interact with their devices, which apps are most frequently used, how device performance impacts user behavior, and how users rate their overall experience. This will help the team in enhancing the mobile experience and making informed decisions for future iOS updates.

## **Data Tables**:

**Table: AppUsage**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| device_id    | Unique identifier for each device | int | Primary Key |
| app_name     | Name of the app | varchar(255) | - |
| usage_time   | Time spent on the app in minutes | int | - |
| usage_date   | Date of the app usage | date | - |

**Table: DevicePerformance**

| Feature Name | Description | Data Type | Comments |
|--------------|-------------|-----------|----------|
| device_id    | Unique identifier for each device | int | Foreign Key referencing AppUsage |
| performance_score | Score indicating device performance (1-10) | int | - |
| feedback_rating | User's feedback rating for device performance (1-5) | int | Enum (1,2,3,4,5) |
| feedback_date | Date of the feedback | date | - |

## Questions:

**Question 1**:
- *Topics and Operations*: Aggregation, Filtering
- *Scenario*: The iOS team wants to understand which apps are most popular among users. This will help in optimizing the iOS experience around these apps.
- *Task*: Write an SQL query to find the top 5 apps based on total usage time in the last 30 days (Oct. 2023).

**Question 2**:
- *Topics and Operations*: Join, Aggregation, Filtering
- *Scenario*: Device performance can greatly influence the user experience. The team wants to understand if there's a correlation between device performance and app usage.
- *Task*: Write an SQL query to find the average usage time of apps on devices with a performance score less than 5 and compare it with devices having a performance score of 5 or more.

**Question 3**:
- *Topics and Operations*: Join, Aggregation, Window Functions
- *Scenario*: User feedback is crucial for understanding the real-world performance of devices. The team wants to track if there's any pattern in feedback ratings based on device performance over time.
- *Task*: Write an SQL query to find the monthly average feedback rating for devices, segmented by their performance score (1-10). The result should show the month, performance score, and the average feedback rating for that score in that month.
