# 1. Business Problem Statement

As a data scientist at CVS, you have been tasked with developing a predictive model to identify patients with chronic diseases who are at risk of non-adherence to their prescribed medications. Medication non-adherence can lead to adverse health outcomes and increased healthcare costs. CVS aims to leverage its data resources and advanced analytics to predict non-adherence early and intervene with personalized strategies to improve patient outcomes.

## 2. Dataset Description
**2.1. Table 1: Patient Medication History**
This table contains information about patients' medication history, including prescriptions and refill patterns.

   | Column name | Description |
   |-------------|-------------|
   | patient_id  | Unique identifier for each patient |
   | prescription_id         | Unique identifier for each prescription |
   | medication  | Name of the prescribed medication |
   | dosage      | Dosage strength of the medication |
   | quantity   | Quantity of medication prescribed |
   | prescribed_date  | Date when the medication was prescribed |
   | refill_date         | Date when the medication was refilled |
   | days_supply  | Number of days' supply for each prescription |
   | adherence      | Binary indicator (0 or 1) for medication adherence |
   
**2.2. Table 2: Patient Demographics and Clinical Data**
This table provides demographic and clinical information about the patients.

   | Column name | Description |
   |-------------|-------------|
   | patient_id  | Unique identifier for each patient |
   | age      | Age of the patient |
   | gender  | Gender of the patient (Male/Female) |
   | income      | Annual income of the patient |
   | location   | Geographic location of the patient (e.g., city, state) |
   | chronic_disease  | Indicator for the presence of a chronic disease |
   | comorbidity         | Indicator for the presence of comorbidities |
   | healthcare_utilization  | Number of healthcare visits in the past year |



## 3. Questions

**3.1. Data Manipulation**
- (3.1.1) In the Patient_Medication_History table, how would you identify and handle any duplicate entries for prescriptions, considering the columns such as patient_id, prescription_id, and prescribed_date?

- (3.1.2) Describe how you would join the Patient_Medication_History and Patient_Demographics_Clinical tables effectively. Once the tables are joined, you want to create a new feature that indicates the average number of medications prescribed per patient. How would you approach this?

**3.2. Metric Selection**
- (3.2.1) In the context of medication adherence, what are the limitations of using accuracy as an evaluation metric? Suggest an alternative metric that can better capture the importance of adherence.
- (3.2.2) Discuss the trade-offs between precision and recall in evaluating the adherence prediction model. Which metric would be more relevant for this problem, and why?

**3.3. Feature Engineering**
- (3.3.1) Given the Patient_Medication_History table, how would you engineer a new feature that captures the refill pattern for each patient's medication? Describe the steps you would take and the factors you would consider in creating this feature.

- (3.3.2) Suppose you want to analyze the relationship between medication adherence (from the Patient_Medication_History table) and the presence of comorbidities (from the Patient_Demographics_Clinical table). How would you engineer a feature that quantifies the interaction between these two variables? Discuss your approach and any transformations or calculations involved.

**3.4. Model Selection**
- With our CVS dataset containing both numerical features and categorical variables, what initial model would you choose and why? Consider the nature of the features and the task at hand.

**3.5. Model Optimization and Interpretation**
- (3.5.1) Continuing from the previous question, assuming you have selected a random forest algorithm to predict medication adherence, how would you determine the optimal hyperparameters for the model? Discuss different approaches you can take, and explain the trade-offs involved in selecting the best hyperparameters.

- (3.5.2) Imagine you have successfully optimized a random forest model for the CVS data challenge. However, the model's interpretability is equally important for stakeholders. How would you address the trade-off between model performance and interpretability? Discuss techniques or approaches you would use to enhance the interpretability of the random forest model without significantly sacrificing its performance.

**3.6. Business Insights**
- In the context of the CVS data challenge, you have developed a machine learning model to predict medication adherence. How would you translate the model's predictions into actionable insights for CVS? Discuss how you would communicate the findings to stakeholders and recommend specific interventions or strategies to improve medication adherence based on the model's outputs.
