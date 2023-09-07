# **Business Problem Statement:**  
At PayPal, ensuring a positive brand perception is crucial. Given the rise of e-commerce and online payments, sentiment from platforms like Twitter, Reddit, and review sites can significantly influence potential users. By employing NLP techniques, we aim to extract, quantify, and interpret the sentiment related to PayPal's brand, helping us address issues and amplify positives in our marketing campaigns.

---

## **Data Table:**

**Social_Mentions**  

| Column Name  | Description                                                  | Feature Type         |
|--------------|--------------------------------------------------------------|----------------------|
| `user_id`    | Unique identifier for the user                               | Categorical (Nominal)|
| `platform`   | Platform where the mention was made (Twitter, Reddit, etc.)  | Categorical (Nominal)|
| `mention`    | Text of the mention                                          | Text                 |
| `timestamp`  | Time when the mention was made                               | Datetime             |
| `followers`  | Number of followers the user has on the platform             | Numeric (Continuous) |
| `region`     | Geographical region of the user                              | Categorical (Nominal)|

---

## **Questions:**

1. **Sentiment Distribution Analysis:**  
Given the `Social_Mentions` data from the past year, can you explore the distribution of sentiments across various platforms? While analyzing, ensure to highlight any anomalies or surprising patterns, possibly indicating emerging issues or trends.

2. **Identify Influential Users with Negative Sentiments:**  
An influential user's negative sentiment can significantly impact brand perception. By taking into consideration the `followers` column, create an algorithm to identify and rank users based on their influence and the negativity of their `mention`.

3. **Predictive Modeling for Sentiment Analysis:**  
Develop a predictive model to classify the sentiment of a `mention` as Positive, Neutral, or Negative. For this, treat the sentiment as the target variable (you might need an external tool/library to generate sentiment labels from the text). How would you ensure that this model is not overfitting and is generalizable across different regions?

    - *Target Variable: Sentiment (Positive, Neutral, Negative)*

4. **Impact of Region on Sentiment:**  
We are considering a new marketing campaign tailored to specific regions. Can you help identify if certain regions have a higher propensity for negative sentiments compared to others? Use statistical tests to confirm any observed differences.

