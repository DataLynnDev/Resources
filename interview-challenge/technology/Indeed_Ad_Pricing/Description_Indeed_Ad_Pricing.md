# **Business Problem Statement:**
As the hiring manager for the Ad Pricing team at Indeed, we're looking to use predictive analytics to optimize our dynamic pricing models. The goal is to forecast the demand for job postings based on various factors, ensuring the most efficient pricing strategy for both Indeed and employers. To achieve this, we need a data scientist who understands the intricate balance of statistical, machine learning, and business intelligence.

## **Data Tables**

**Table: job_postings**

| Column Name  | Description                                      | Feature Type    |
|--------------|--------------------------------------------------|-----------------|
| job_id       | Unique ID for the job posting                    | Categorical     |
| job_category | Category of the job (e.g., IT, Finance)          | Categorical     |
| employer_id  | Unique ID for the employer.                      | Categorical     |
| location     | City or region of the job posting                | Categorical     |
| post_date    | Date when the job was posted                     | Date            |
| season       | Season when the job was posted (e.g., Spring)    | Categorical     |
| historic_demand | Average clicks for similar jobs in the past    | Continuous      |
| price        | Price charged for the job posting                | Continuous      |

**Table: employer_info**

| Column Name  | Description                                      | Feature Type    |
|--------------|--------------------------------------------------|-----------------|
| employer_id  | Unique ID for the employer                       | Categorical     |
| response_rate| Percentage of responses from candidates          | Continuous      |
| avg_price    | Average price previously paid for job postings   | Continuous      |

## **Questions:**

1. **Historical Data Analysis:** Based on the `job_postings` table, identify any trends or anomalies in the historic_demand for job postings. How does demand change with seasonality, job_category, and location?
   

2. **Predictive Modeling:** Using the `job_postings` table, build a predictive model to forecast the demand for a job posting. Ensure to validate your model's accuracy. Consider `historic_demand`, `job_category`, `location`, and `season` as your predictors. Your target variable will be the `price` charged for the job posting.


3. **Bayesian Approach:** Based on the employer's past `response_rate` from the `employer_info` table, what is the probability that an employer with a response rate of 60% will pay above the average price for a job posting?


4. **Advanced Insights with Joint Analysis:** Employers might have a trend in the amount they're willing to pay based on their historic response rates. Can you generate insights by joining the `employer_info` and `job_postings` table to estimate the potential price for a new job posting for a given employer?