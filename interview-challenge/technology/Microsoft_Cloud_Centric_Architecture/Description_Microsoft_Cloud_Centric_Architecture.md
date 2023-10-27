# **Business Problem Statement:**

The Cloud-Centric Architecture team at Microsoft aims to ensure the seamless transition and operation of IT systems and applications in the cloud. Analyzing the adoption rates, performance metrics, and user feedback is crucial to guide architectural improvements, develop effective training materials, and devise robust promotional strategies. There is a need to identify patterns and insights from the data related to cloud-centric solutions which can help in understanding the areas of improvement and user satisfaction.

## **Data Tables:**

Table: CloudAdoption

| Feature Name  | Brief Feature Description       | Feature Data Type | Comments       |
|---------------|---------------------------------|-------------------|----------------|
| adoption_id   | Unique ID for each adoption     | INT               | Primary Key    |
| product_name  | Name of the cloud-centric product| VARCHAR(50)      |                |
| client_id     | Unique ID for each client       | INT               |                |
| adoption_date | Date of adoption                | DATE              |                |
| user_feedback | Feedback score from the user    | INT               | Score 1 to 5   |


**Table: PerformanceMetrics**

| Feature Name  | Brief Feature Description     | Feature Data Type | Comments       |
|---------------|-------------------------------|-------------------|----------------|
| metric_id     | Unique ID for each metric     | INT               | Primary Key    |
| adoption_id   | Refers to the adoption record | INT               | Foreign Key, references CloudAdoption.adoption_id |
| response_time | Response time of the application | FLOAT          | In milliseconds |
| error_rate    | Error rate of the application  | FLOAT            | As percentage  |
| uptime        | Uptime of the application      | FLOAT            | As percentage  |

## Questions:

**Question 1:**
* **Topics and Operations:** Filtering, Joining
* **Scenario:** We want to understand the performance of our cloud-centric products from the clients who adopted them.
* **Task:** Write a SQL query to fetch the `product_name`, `adoption_date`, `response_time`, and `user_feedback` for all products.

**Question 2:**
* **Topics and Operations:** Aggregation, Grouping
* **Scenario:** Aggregating performance metrics will provide an overview to compare between different products.
* **Task:** Write a SQL query to find the average `response_time`, and `error_rate` for each `product_name`. Sort the result based on average `response_time` in ascending order.

**Question 3:**
* **Topics and Operations:** Sub-query, Filtering
* **Scenario:** Identifying products with above-average performance metrics and positive user feedback can help in promoting these products.
* **Task:** Write a SQL query to find the `product_name` and `adoption_date` of products that have an `error_rate` less than the overall average `error_rate` and a `user_feedback` score of 4 or above.
