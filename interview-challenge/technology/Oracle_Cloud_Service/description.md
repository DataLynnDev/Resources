# **Business Problem Statement:**
The Oracle Cloud Infrastructure (OCI) team wants to optimize cloud service utilization among its customers. To do this, the team seeks to understand the patterns in which clients use the cloud resources, identify potential areas for upselling, and proactively address performance bottlenecks before they impact the client's operations.

## **Data Table:**

**Info_data**

| Feature Name       | Description                                       | Feature Type   |
|--------------------|---------------------------------------------------|----------------|
| `user_id`          | Unique identifier for each user                   | Categorical    |
| `resource_type`    | Type of cloud resource (e.g., compute, storage)   | Categorical    |
| `usage_hours`      | Hours a resource was used in a month              | Continuous     |
| `resource_size`    | Size/capacity of the resource (e.g., 16GB, 500GB) | Continuous     |
| `performance_score`| Score indicating the performance of the resource  | Continuous     |
| `region`           | Geographic region of the resource's data center   | Categorical    |
| `cost`             | Monthly cost for the user for that resource       | Continuous     |
| `feedback_score`   | User's feedback score for the resource            | Continuous     |
| `upgraded`         | If the resource was upgraded in the past month    | Boolean        |
| `ticket_count`     | Number of support tickets raised for the resource | Discrete       |

## **Questions:**

1. **Data Manipulation & Cleaning:**
    - *Scenario:* You've been handed a raw dataset extracted from OCI's telemetry data for the past month. However, while examining the `usage_hours` column, you find that some entries exceed the number of hours in a month. Also, a considerable number of entries in the `feedback_score` column are extreme values (potentially outliers).
      - How would you preprocess the `usage_hours` column to ensure data integrity?
      - Given that you observe a significant percentage of outliers in the `feedback_score` column, explain your approach to handling these outliers, especially considering the relevance of feedback to business operations.

2. **Probability and Statistics:**
    - *Scenario:* In order to better allocate resources, you are asked to understand the distribution of `performance_score` across different `resource_types` in various `regions`.
      - What statistical tests or methods would you use to determine if there is a significant difference in `performance_score` between different `resource_types` in the same region?

3. **Machine Learning & Modeling:**
    - *Scenario:* To improve upselling strategies, you've been tasked with creating a model that predicts whether a user is likely to upgrade their resources in the coming month based on their past interactions.
      - Identify and justify the most appropriate target variable from the data provided for this prediction task.
      - Describe how you'd set up a machine learning framework for this task, ensuring model robustness and avoiding overfitting.

4. **Advanced Techniques:**
    - *Scenario:* In the context of cloud infrastructure, understanding sequences of user actions can be crucial. You're interested in understanding patterns in ticket raising by users - especially if they follow any upgrades.
      - Propose a method or technique to analyze sequential patterns in user ticket raising behavior following any upgrades. This should take into account both `upgraded` and `ticket_count` columns.