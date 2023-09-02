# **Business Problem Statement**:
IBM's healthcare informatics team is working on developing a cutting-edge AI system to predict early disease detection, offer personalized treatment recommendations, and drive drug discovery. The system's effectiveness relies heavily on the accuracy and depth of insights derived from patient electronic health records, medical images, and genetic data. The ultimate aim is to improve patient outcomes and streamline the healthcare system's efficiency.

## **Data Table**:

**PatientData**

| Column Name | Description                                     | Feature Type    |
|-------------|-------------------------------------------------|-----------------|
| patient_id  | Unique identifier for each patient              | Categorical     |
| age         | Age of the patient                              | Numerical       |
| medical_img | Path to medical imaging data                    | Text            |
| genetic_data| Genetic markers and mutations                   | Categorical     |
| ehr_notes   | Electronic health record notes                  | Text            |
| treatment_hist | Past treatment details                         | Text            |
| disease_status | Disease status (early, advanced, none)         | Categorical     |
| drug_response | How the patient responded to drugs             | Categorical     |
| visit_date  | Date of the patient's last visit                | Date            |
| predicted_outcome | Predicted disease outcome based on model    | Categorical     |

## **Questions**:

1. **Scenario**: A frequent challenge in medical data analysis is the presence of outliers which might skew the results. Given the 'PatientData' table, can you determine any outliers especially with regard to the 'age' column, that might affect the accuracy of age-related disease predictions? Additionally, how would you handle them in this dataset?

2. **Scenario**: With the increasing volume of patient data, it becomes pivotal to efficiently extract specific insights. Using SQL, identify the patients with early disease detection who have not yet been subjected to any form of treatment according to 'ehr_notes'. What insights can you infer from the data about the delay in treatment initiation post early detection?

3. **Scenario**: Based on the 'PatientData' table, design a prediction model to determine the 'predicted_outcome' for a patient. Use relevant features from the dataset ensuring the model is robust and accurate. Once designed, explain the significance and impact of features like 'genetic_data' and 'medical_img' on the model's predictions.
   - *Target Variable*: predicted_outcome

4. **Progressive Scenario**: Utilizing your earlier model, integrate a module that can provide personalized treatment recommendations stored in 'treatment_hist' based on the 'predicted_outcome'. How can we ensure that the treatment recommendation aligns with the patient's genetic makeup given in 'genetic_data'?
