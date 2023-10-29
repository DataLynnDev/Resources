# **Business Problem Statement:**

Netflix's Content Delivery Network (CDN) is the backbone of delivering high-quality streaming content to users worldwide. It's imperative to continuously monitor, analyze, and optimize the CDN's performance to ensure a seamless viewing experience. In this context, we are faced with three critical areas of analysis:

1. Performance Metrics: Assessing the CDN's content load times across varying regions, times, and content types to identify performance disparities and improvement areas.
2. Traffic Analysis: Understanding the system's usage patterns, identifying bottlenecks, and detecting potential vulnerabilities to ensure uninterrupted service.
3. Cost-Benefit Analysis: Evaluating the costs associated with CDN maintenance or upgrades against the benefits derived from enhanced performance and reduced user complaints.

## **Data Tables:**

Table 1: **CDN_Logs**

| Feature Name | Brief Feature Description           | Feature Data Type | Comments                             |
|--------------|-------------------------------------|-------------------|---------------------------------------|
| log_id       | Unique log identifier               | int               | Primary Key                           |
| region       | Geographic region of the user       | varchar           |                                       |
| content_type | Type of content being accessed      | varchar           | Enum (Movie, Series, Documentary)     |
| load_time    | Time taken to load content (seconds)| float             |                                       |
| access_time  | Time of content access              | datetime          |                                       |
| user_id      | Identifier of the user             | int               |                                       |

Table 2: **CDN_Costs**

| Feature Name   | Brief Feature Description         | Feature Data Type | Comments                             |
|----------------|-----------------------------------|-------------------|---------------------------------------|
| cost_id        | Unique cost identifier           | int               | Primary Key                           |
| region         | Geographic region                 | varchar           |                                       |
| upgrade_cost   | Cost of CDN upgrade               | float             |                                       |
| maintenance_cost| Cost of CDN maintenance         | float             |                                       |
| month          | Month of the cost incurred       | date              |                                       |

## **SQL Questions:**

1. **Scenario:** The CDN_Logs table has recently been populated with new data. However, the content_type column entries have been inconsistently formatted. Standardizing these entries is crucial for accurate analysis.

   **Task:** Write a query to format the content_type column such that only the first letter is uppercase, and the rest are lowercase.

2. **Scenario:** Our CDN experiences varying load times. Identifying regions and content types with significantly higher load times can help prioritize optimization efforts.

   **Task:** Write a query to identify the regions and content types where the average load time is more than 2 seconds. Provide the average load time for each of these combinations and order the result by region, then by content type.

3. **Scenario:** To perform a cost-benefit analysis, understanding the costs incurred in different regions and correlating them with performance metrics is essential.

   **Task:** Write a query to calculate the total costs (sum of upgrade_cost and maintenance_cost) for each region from the CDN_Costs table. Join this with the previous query’s result to show the average load time alongside the total costs for each region and content type, ordering the result by total costs in descending order.
