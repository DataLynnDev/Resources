# Business Problem Statement:
With the increase in iCloud users and data traffic, it's crucial to optimize storage solutions, pricing models, and ensure smooth data synchronization across devices. We need to analyze storage usage patterns, data traffic, and user engagement to make data-driven decisions for optimizing storage and pricing while maintaining a high level of user satisfaction.

## Data Tables:

**Table 1: UserStorage**

| Feature Name | Feature Description                             | Feature Data Type | Comments              |
|--------------|-------------------------------------------------|--------------------|-----------------------|
| user_id      | Unique identifier for each user                | INT               | Primary Key           |
| storage_used | Amount of storage used in GB                   | FLOAT             |                       |
| last_sync    | Timestamp of the last data synchronization     | TIMESTAMP         |                       |
| plan_id      | Identifier for the pricing plan                | INT               | Foreign Key           |
| device_count | Number of devices linked to iCloud             | INT               |                       |

**Table 2: PricingPlan**

| Feature Name | Feature Description                             | Feature Data Type | Comments                    |
|--------------|-------------------------------------------------|--------------------|-----------------------------|
| plan_id      | Unique identifier for each pricing plan        | INT               | Primary Key                 |
| price        | Monthly price for the plan                     | FLOAT             |                             |
| storage_limit| Maximum storage limit in GB for the plan       | FLOAT             |                             |
| user_count   | Number of users subscribed to this plan        | INT               |                             |

## Question

### Question 1:
- **Topics and Operations**: Join Operations  
- **Scenario**: To better understand our user engagement and storage usage, it's crucial to analyze the average storage used per pricing plan. This will help in evaluating whether our pricing tiers are aligned with user needs.  
- **Task**: Write an SQL query to calculate the average storage used per pricing plan, along with the price of the plan.

### Question 2:
- **Topics and Operations**: Conditional Logic
- **Scenario**: A key part of optimizing storage solutions involves analyzing the usage patterns of users, especially those nearing their storage limit. This information will be pivotal in designing better pricing models and storage solutions.  
- **Task**: Write an SQL query to find the total number of users per pricing plan who have used more than 90% of their storage limit.

### Question 3:
- **Topics and Operations**: Date Functions, Aggregation  
- **Scenario**: Monitoring the frequency of data synchronization across devices is crucial for ensuring smooth user experience. Understanding the last synchronization timestamps can provide insights into user engagement and potential issues.  
- **Task**: Write an SQL query to find the number of users who have not synchronized their data in Sep. 2023, grouped by pricing plan.