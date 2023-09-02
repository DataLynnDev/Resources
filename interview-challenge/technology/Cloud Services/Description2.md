# **Business Problem Statement:**  
IBM's cloud services, which serve as the backbone for numerous enterprises, have observed a decline in customer satisfaction over the past quarter. This has coincided with increased downtimes and slower processing speeds. The management suspects inefficiencies in resource allocation, particularly in data processing units, and needs insights to improve the situation. The challenge is to analyze user behaviors, server downtimes, and processing speeds to help in optimizing cloud resources for better service delivery.

## **Data Table**

**CloudServiceData:**

| Column Name         | Description                                                   | Feature Type     |
|---------------------|---------------------------------------------------------------|------------------|
| UserID              | Unique identifier for each user                               | Categorical      |
| SessionDate         | Date when the user accessed the cloud service                 | Date             |
| DataProcessed_GB    | Amount of data processed in gigabytes during the session       | Numerical        |
| ProcessingSpeed_MBps| Average processing speed in megabytes per second               | Numerical        |
| Downtime_Min        | Minutes the service was unavailable during the session         | Numerical        |
| ServicePlan         | Type of subscription plan of the user (Basic, Pro, Enterprise) | Categorical      |
| UserFeedbackScore   | User satisfaction score on a scale of 1-10                     | Ordinal          |
| AdClicked           | Whether an advertisement was clicked by the user (0 or 1)      | Binary Categorical|
| DatasetSize_GB      | Size of dataset uploaded by the user in gigabytes              | Numerical        |

## **Questions**:

1. **Scenario:** It's known that different service plans might have varying levels of user satisfaction due to the differentiated resources allocated to them. By looking into the data, **provide insights** into how the average processing speed and downtime impact the user feedback score across different service plans.

2. **Scenario:** The marketing team has been trying to push ads to potential high-end clients. While we have information on which users click on advertisements, the team believes that users who process larger datasets might be more inclined to click on them. **Build a model** predicting if a user will click on an advertisement based on their `DatasetSize_GB`, `ServicePlan`, and `ProcessingSpeed_MBps`. Clearly indicate `AdClicked` as the target variable.


3. **Scenario:** The technical team noticed that on days with higher downtimes, the processing speeds tend to drop. Using the data, **determine** if there's a statistically significant relationship between the `Downtime_Min` and `ProcessingSpeed_MBps`.

4. **Scenario:** To improve our cloud service, we want to give additional resources to users who might require higher processing speeds. **Using the data**, find a subset of users who consistently show a higher average of `DataProcessed_GB` but have a lower `ProcessingSpeed_MBps`. This will help in identifying potential candidates for a service plan upgrade.

