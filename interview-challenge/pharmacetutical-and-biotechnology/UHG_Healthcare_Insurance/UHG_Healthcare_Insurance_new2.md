# 1. Business Problem Statement
United Health Group (UHG), a major health insurance provider, seeks to enhance its risk management through advanced data analytics. Given the industry's complexities, understanding and managing the associated risk and cost of each insurance plan is critical. The objective of this interview challenge is to use UHG's provided data to construct a predictive risk model, enhancing UHG's decision-making and potentially leading to more personalized insurance solutions.

## 2. Dataset Description

**Table 1: `PlanData`**

The PlanData table contains details about various insurance plans that United Health Group offers.

| Column Name | Description |
| --- | --- |
| `plan_id` | Unique identifier for each insurance plan |
| `plan_name` | Name of the insurance plan |
| `plan_type` | Type of the insurance plan (e.g., HMO, PPO, EPO, POS) |
| `plan_premium` | The premium price of the insurance plan |
| `plan_deductible` | The deductible cost for the insurance plan |
| `plan_oop_max` | Out-of-pocket maximum/limit for the insurance plan |


**Table 2: `UserData`**

The UserData table has demographic information about the insured users.

| Column Name | Description |
| --- | --- |
| `user_id` | Unique identifier for each user |
| `age` | Age of the user |
| `gender` | Gender of the user |
| `location` | Residential location of the user |
| `plan_id` | Unique identifier of the plan user is subscribed to |
| `chronic_disease` | Indicates if user has a chronic disease |



**Table 3: `ClaimData`**

The ClaimData table includes details about insurance claims made by users.

| Column Name | Description |
| --- | --- |
| `claim_id` | Unique identifier for each claim |
| `user_id` | Unique identifier of the user who made the claim |
| `plan_id` | Unique identifier of the plan under which claim is made |
| `claim_date` | Date when the claim was made |
| `claim_amount` | Amount of the claim |
| `claim_reason` | Reason for the claim (e.g., hospitalization, prescription, etc.) |
| `claim_status` | Status of the claim (paid, rejected, etc.) |


## 3. Questions

**3.1. Identifying Risk Categories in Insurance Plans (Python)**

In the context of health insurance, the term "risk" often refers to the likelihood or probability that an insured individual will make a claim, as well as the probable cost of those claims. Risk is often influenced by a variety of factors, such as the individual's age, health conditions, lifestyle habits, and the specifics of their insurance plan.

For instance, older individuals or those with chronic diseases are typically at a higher risk of making claims due to health issues. Similarly, certain types of plans (like those with lower deductibles or out-of-pocket maximums) may also be associated with a higher risk, as individuals are more likely to make claims when they know they'll have to pay less out-of-pocket.

With these considerations in mind, your task is to use the historical data available in 'PlanData', 'UserData', and 'ClaimData' tables to **classify our insurance plans into risk categories**. What criteria would you use for this classification? Please explain the process and results of your classification strategy.

**3.2. Data Transformation and Target Creation (SQL)**

The target variable for our predictive model is 'total_claim_amount', which is the sum of all claim amounts made by a user under a specific insurance plan. Can you write an SQL query to create this target variable from the 'ClaimData' table? Explain your approach.

**3.3. Feature Selection (Python)**
Based on risk definition and the new target variable, what features from 'PlanData', 'UserData', and 'ClaimData' tables would you choose to include in the predictive model? Discuss the reasons behind your choices.

**3.4. Model Selection, Optimization, and Training (Python)**
Considering the features and target variable you've selected, propose a suitable predictive model to estimate the 'total_claim_amount'. Please provide your Python code for model training and hyperparameter optimization. Discuss your rationale behind choosing this specific model and your approach for hyperparameter tuning.

**3.5. Model Evaluation (Python)**

After training and optimizing your model, how would you assess its performance? Please provide your Python code to evaluate your model using appropriate metrics. Considering our business problem, explain why you chose these metrics and how they reflect the model's capability to predict 'total_claim_amount'.