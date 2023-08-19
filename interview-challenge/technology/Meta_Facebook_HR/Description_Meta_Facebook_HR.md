# **Business Problem Statement:**

As the Talent Acquisition and HR Analytics team at Meta, we are deeply invested in understanding the dynamics and factors that affect our hiring and retention processes. Our aim is to optimize the recruitment pipeline and decrease employee churn by leveraging data-driven insights. Specifically, we want to evaluate the efficacy of our recent hiring campaigns, ascertain potential reasons for employee turnover, and measure the impact of various HR initiatives on employee satisfaction.


## **Data Tables:**

**Table Name: `applicant_data`**

| Column Name | Description | Feature Type |
|-------------|-------------|--------------|
| `applicant_id` | Unique ID of the applicant | Numeric |
| `source` | Source of recruitment (e.g., LinkedIn, Job Portal, Referral, etc.) | Categorical |
| `num_interviews` | Number of interviews conducted for the applicant | Numeric |
| `status` | Application status (Hired, Rejected, In Progress) | Categorical |
| `position` | Position applied for (e.g., Engineer, Manager, etc.) | Categorical |

**Table Name: `employee_data`**

| Column Name | Description | Feature Type |
|-------------|-------------|--------------|
| `employee_id` | Unique ID of the employee | Numeric |
| `hire_date` | Date the employee was hired | Date |
| `exit_date` | Date the employee left the company, if applicable | Date |
| `reason_for_exit` | Reason for leaving (e.g., Personal, New Opportunity, etc.) if they left | Categorical |
| `feedback_score` | Employee feedback score after 6 months from joining (1-10) | Numeric |


## **Questions:**

1. **Scenario:** You are presented with data from our recent hiring campaign. Utilizing the `applicant_data` table, identify the top 3 sources from which we received the highest number of applicants. Additionally, determine the source with the highest hire rate.
   

2. **Scenario:** One of our core objectives is to understand employee churn. Using the `employee_data` table, determine the average tenure of employees who left the company in the past year. Additionally, identify the most common reason for exit among these employees.
   

3. **Scenario:** Meta places a significant emphasis on employee feedback to evaluate the success of HR initiatives. Given the `employee_data` table, analyze the distribution of feedback scores. Determine if there's a particular score range (e.g., 1-3, 4-7, 8-10) that's predominant. Using this insight, infer potential HR interventions.
   

4. **Scenario:** We've noticed a trend where certain positions have a higher turnover rate than others. Utilizing both the `applicant_data` and `employee_data` tables, determine which position has the highest turnover within the first year of joining and hypothesize potential reasons based on the data.
   
