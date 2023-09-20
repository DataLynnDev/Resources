# **Business Problem Statement:**
With the rapid expansion of AWS, it's essential for the company to maintain optimal service performance and customer satisfaction. To ensure this, AWS needs to study the usage patterns of its services. This would help in resource allocation and optimizing costs. At the same time, analyzing system performance metrics is crucial to ensure uptime and efficiency. As a data analyst for the AWS team, your responsibility is to derive insights from data to achieve the above goals.

## **Data Tables:**

**info_data**

| Column Name   | Description                                  | Feature Type  |
|---------------|----------------------------------------------|---------------|
| user_id       | Unique identifier for the user               | Categorical   |
| service_id    | Unique identifier for AWS services           | Categorical   |
| usage_date    | Date of usage                                | Date          |
| duration      | Duration of service usage in hours           | Numeric       |
| cost          | Cost incurred for the service                | Numeric       |
| performance_score | System performance score (1 to 10)       | Numeric       |
| region        | AWS region                                   | Categorical   |
| feedback      | Customer feedback rating (1 to 5)            | Numeric       |

## **Question**

**Question 1: (Data Cleaning & Exploration)**

**Scenario:**
Upon receiving the AWS usage data, you notice there are some inconsistencies and gaps.

- Identify and address any missing values in the 'feedback' column.
- Discover and manage any outliers in the 'cost' column that might skew the analysis.
- Ensure the 'usage_date' column has a consistent date format across all records.

**Question 2: (SQL Queries)**

**Scenario:**
To make business recommendations, AWS needs a report on customer behavior.

- Using SQL window functions, rank users based on their total costs.
- Retrieve a list of users who used the service both in 'region A'(North) and 'region B'(South) without any repetition.
- Using a left join and then a right join, compare the results when you try to fetch records of 'user_id' from a hypothetical 'User_Details' table.
- Implement a CTE to fetch top 10 users with the highest performance score.

**Question 3: (Probability and Statistical Analysis)**

**Scenario:**
AWS often rolls out updates or patches. Assuming a normal distribution of rollouts across a month:

- Calculate the probability that a user receives more than three updates within a week.
- Then, implement this calculation programmatically to retrieve the result.

**Question 4: (Product & Business Sense)**

**Scenario:**
Recently, an AWS service has underperformed in terms of revenue. The actual revenue is 20% lower than the predicted revenue.

- Analyze the data and identify any patterns or reasons that might explain this shortfall. Consider factors like region, performance score, and user feedback.
- Propose strategies to bridge this revenue gap based on your findings.