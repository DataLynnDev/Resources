
## 1. Business Problem Statement

As a data scientist at CVS, you have been tasked with developing a predictive model to identify patients with chronic diseases who are at risk of non-adherence to their prescribed medications. Medication non-adherence can lead to adverse health outcomes and increased healthcare costs. CVS aims to leverage its data resources and advanced analytics to predict non-adherence early and intervene with personalized strategies to improve patient outcomes.

## 2. Dataset Description
### 2.1. Table 1: Patient Medication History ###
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
   
### 2.2. Table 2: Patient Demographics and Clinical Data ###
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

#### **Answer 3.1.1.**
The given Python script uses SQL queries to handle duplicate entries in the 'Patient_Medication_History' table of a SQLite database. The specific duplicates it targets are those with identical 'patient_id', 'prescription_id', and 'prescribed_date' fields. These duplicates are problematic as they might represent unintentional repetition of the same information, thus leading to data redundancy and potential bias in subsequent analysis.

#### **Answer 3.1.2.**

The provided Python script performs a series of operations to combine data from the 'Patient_Medication_History' and 'Patient_Demographics_Clinical' tables, and then calculate and append a new feature: 'avg_medication_count'. This feature represents the average number of medications prescribed per patient.


#### **Answer 3.2.1.**

**Limitations**:
Accuracy measures the proportion of **correct predictions** (adherence or non-adherence) out of the total predictions made. However, in the context of medication adherence, the dataset is often **imbalanced**, meaning there may be a significant imbalance between adherent and non-adherent instances. This can lead to misleading results because a high accuracy can be achieved by simply predicting the majority class (e.g., non-adherence) without capturing the importance of correctly identifying the minority class (e.g., adherence).

An **alternative** evaluation metric that can better capture the importance of adherence is **balanced accuracy**. Balanced accuracy takes into account the imbalanced nature of the dataset by calculating the average of the recall (true positive rate) for both the positive class (adherence) and the negative class (non-adherence). It provides a more comprehensive evaluation of the model's performance in capturing both classes, regardless of their imbalance.

#### **Answer 3.2.2.**

**Trade-offs**：
 **Precision** measures the proportion of correctly predicted positive instances (adherence) out of **all instances predicted as positive**. It focuses on minimizing false positives, which means it emphasizes the accuracy of positive predictions. On the other hand, **recall** measures the proportion of correctly predicted positive instances out of **all actual positive instances**. It focuses on minimizing false negatives, which means it emphasizes capturing all positive instances.

In the context of evaluating an adherence prediction model, both precision and recall are relevant, but **the importance of each metric depends on the specific problem and its associated costs and consequences**. If correctly identifying true positive cases (adherence) is crucial, such as in situations where non-adherence can have severe consequences, then recall becomes more relevant. However, if minimizing false positive cases (false alarms) is important, such as in situations where unnecessary interventions or actions may result from false predictions, then precision becomes more relevant.

To strike a balance between precision and recall, you can use the **F1-score**, which is the harmonic mean of precision and recall. It provides a single metric that combines both precision and recall, allowing you to assess the overall performance of the model.

#### **Answer 3.3.1.**

To engineer a new feature that captures the refill pattern for each patient's medication based on the Patient_Medication_History table, you can follow these steps:
- Sort the DataFrame: Sort the DataFrame by patient ID and prescribed date to ensure the data is in chronological order for each patient.
- Calculate the refill duration: Calculate the time difference between consecutive refill dates for each patient and medication. This will give you the duration between refills, indicating the refill pattern.
- Group the data: Group the data by patient ID and medication to perform calculations on each group separately.
- Compute statistical measures: Compute statistical measures on the refill duration, such as mean, standard deviation, minimum, maximum, and median. These measures will provide insights into the refill pattern for each patient and medication combination.
- Assign the computed measures: Assign the computed statistical measures to each patient and medication combination as the new feature, representing the refill pattern.

#### **Answer 3.3.2.**

To engineer a feature that quantifies the interaction between medication adherence and the presence of comorbidities, you can follow these steps:

- Merge the tables: Merge the Patient_Medication_History table and the Patient_Demographics_Clinical table based on the patient_id column. This will combine the information on medication adherence and comorbidities into a single DataFrame.
- Encode comorbidity presence: Create a binary feature that represents the presence or absence of comorbidities for each patient. You can encode it as 1 for patients with comorbidities and 0 for patients without comorbidities.
- Group the data: Group the data by the encoded comorbidity feature and calculate the average medication adherence for each group. This will give you the average adherence rate for patients with and without comorbidities.
- Create the interaction feature: Compute the difference between the average adherence rate of patients with comorbidities and the average adherence rate of patients without comorbidities. This difference represents the interaction between medication adherence and comorbidities.

#### **Answer 3.4.**

Given the CVS dataset with numerical features (Age, Income, Loan_Amount, Credit_Score) and categorical variables (Occupation, Education, Loan_Type), an appropriate initial model choice would be a Random Forest classifier. It effectively handles both types of features, captures feature interactions, provides feature importance insights, and is robust to overfitting. With its ensemble learning approach, it combines multiple decision trees for improved prediction accuracy.

#### **Answer 3.5.1.**

To determine the optimal hyperparameters for the Random Forest algorithm in predicting medication adherence, several approaches can be taken:

- **Grid Search Cross-Validation**: One approach is to perform a grid search cross-validation. This involves defining a grid of hyperparameter values to explore and evaluating the model's performance for each combination using cross-validation. The hyperparameter values that yield the best performance, such as accuracy or F1 score, can be selected as the optimal hyperparameters.

- **Randomized Search Cross-Validation**: Another approach is to use randomized search cross-validation. Instead of exhaustively searching all possible combinations, this approach randomly samples hyperparameter values from predefined distributions. It trades off exhaustive search for efficiency, allowing a wider exploration of hyperparameter space within a given computational budget.

- **Model-Based Optimization**: Model-based optimization techniques, such as Bayesian optimization, can be employed. These methods use surrogate models to approximate the performance of different hyperparameter configurations. By intelligently selecting hyperparameters based on previous evaluations, they can converge to optimal or near-optimal solutions with fewer evaluations compared to exhaustive search.

When selecting the best hyperparameters, there are trade-offs to consider:

- **Model Performance vs. Computational Cost**: Increasing the complexity of the Random Forest model by adjusting hyperparameters such as the number of trees or maximum depth can potentially improve performance. However, this comes at the cost of increased computational resources and longer training times.

- **Overfitting vs. Underfitting**: Hyperparameters like the maximum depth or minimum samples per leaf control the model's capacity. Increasing these values can lead to a more complex model that may overfit the training data, capturing noise instead of true patterns. On the other hand, setting them too low may result in underfitting, where the model fails to capture important relationships.

- **Generalization vs. Sensitivity**: Hyperparameter choices impact the model's ability to generalize to unseen data. It's important to strike a balance between a model that generalizes well across different datasets and one that is sensitive enough to capture the nuances of the specific problem at hand.

#### **Answer 3.5.2.**

- **Feature Importance**: Random forests provide a built-in feature importance measure that ranks the importance of each feature in the model. You can extract and analyze the feature importances to identify the most influential features in predicting medication adherence. This information can be presented to stakeholders to provide insights into the factors driving the predictions.

- **Individual Prediction Explanations**: Utilize techniques like **LIME** (Local Interpretable Model-Agnostic Explanations) or **SHAP** (SHapley Additive exPlanations) to provide explanations for individual predictions. These techniques highlight the contribution of each feature to the prediction for a specific instance, enabling stakeholders to understand the model's decision-making process.

- **Partial Dependence Plots**: Generate partial dependence plots to showcase the relationship between individual features and the model's predictions while marginalizing the effects of other features. These plots help stakeholders understand how changes in specific features affect the predicted outcome, promoting interpretability.
