# **Business Problem Statement:**

Spotify Premium Family has been a popular offering, giving families an affordable way to access premium features. However, as the competition in the music streaming industry intensifies, there's a pressing need to ensure that Spotify Premium Family continues to deliver value to its users, retains them, and remains profitable. To achieve this, Spotify aims to enhance its understanding of user behavior, tailor its product offerings more effectively, and predict potential churn before it happens.


## **Data Table: `FamilyData`**

| Column Name     | Description                                                  | Feature Type      |
|-----------------|--------------------------------------------------------------|-------------------|
| family_id       | Unique ID for each family subscription                       | Categorical       |
| member_count    | Number of members in a family subscription                   | Numeric           |
| family_mix_usage| Average monthly plays of the Family Mix playlist             | Numeric           |
| parental_controls| Whether parental controls are enabled (1 for yes, 0 for no)  | Binary            |
| active_months   | Number of months the subscription has been active             | Numeric           |
| churned_last_month| Whether the family churned last month (1 for yes, 0 for no) | Binary            |
| avg_monthly_streams| Average number of streams by the family per month          | Numeric           |
| product_feedback| Feedback about the product (text data)                       | Text              |
| family_region   | Region where the family is based                             | Categorical       |
| monthly_payment | Amount the family pays per month for the subscription        | Numeric           |

## **Questions**

1. Spotify recently launched an update to the Family Mix playlist feature. You're given a dataset named `FamilyData`. Conduct an exploratory analysis on the `family_mix_usage` column to understand the impact of the recent update. What insights can you derive from the data regarding the usage of the Family Mix playlist after the update?


2. Spotify is curious about the relationship between the length of time families have been subscribed (`active_months`) and their likelihood to churn (`churned_last_month`). Using the `FamilyData` dataset, create a model to predict the likelihood of churn based on the number of active months. Clearly state which feature is the target variable and its type.


3. Your team is concerned about the revenue from families based in different regions. From the `FamilyData` dataset, write an SQL query to find the average `monthly_payment` for families from each `family_region`. However, there seems to be an error in the dataset: some families have a monthly payment of 0, which seems erroneous. Adjust your query to exclude these families. Additionally, upon visualizing the average payments in a bar graph, what insights or recommendations would you provide to the business?


