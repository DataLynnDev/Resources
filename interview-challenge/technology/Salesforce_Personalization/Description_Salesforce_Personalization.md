# **Business Problem Statement**:
To enhance the customer experience on Salesforce's Commerce Cloud platform, we aim to provide tailored product recommendations, marketing messages, and customized UI elements. By leveraging our extensive datasets, we can understand user behavior better and make predictive suggestions, making each user's experience feel unique and personal. The success of these initiatives relies heavily on advanced data science techniques and models.

## **Data Table**:

**UserBehavior**

| Column Name    | Description            | Feature Type     |
|----------------|------------------------|------------------|
| `UserID`       | Unique user identifier | Categorical      |
| `ProductID`    | Product browsed/bought | Categorical      |
| `Timestamp`    | Time of activity       | DateTime         |
| `ActivityType` | Browse or Purchase     | Categorical      |
| `Price`        | Product price          | Continuous       |
| `Platform`     | Mobile, Desktop, etc.  | Categorical      |
| `Location`     | User's location        | Categorical      |
| `AdClick`      | Was an ad clicked?     | Boolean          |
| `SessionTime`  | Time spent on platform | Continuous       |
| `PurchaseFreq` | Frequency of purchases | Continuous       |

## **Questions**:

1. **Data Manipulation & Cleaning**  
Given the `UserBehavior` table, there seems to be some irregularities with the `SessionTime`.

    **Scenario**: Due to a recent UI update, some users reported glitches that might have led to inaccurate `SessionTime` recordings.

    - Identify potential outliers in `SessionTime` and discuss how you'd manage them, particularly in sessions where an `AdClick` was recorded.

2. **Probability and Statistics**  
We want to explore the relationship between `SessionTime` and the frequency of purchases (`PurchaseFreq`).

    **Scenario**: Stakeholders believe there's a positive correlation between these two variables.

    - Using statistical analysis, test if longer session times lead to higher purchase frequencies.

3. **Machine Learning & Modeling**  
We aim to better understand and predict a user's likelihood to click on an ad (`AdClick`).

    **Scenario**: Marketing teams suggest that `SessionTime` and `Platform` are good predictors for ad clicks.

    - Using the relevant features from `UserBehavior`, build a model to predict `AdClick`. Clearly state the target variable and its type.

4. **Product Design & Analytics**  
To evaluate the impact of our tailored product recommendations:

    **Scenario**: Preliminary feedback suggests users from specific `Locations` interact differently with product recommendations after an `AdClick`.

    - Analyze the data to see if there's a significant variation in `ActivityType` post `AdClick` across different `Locations`.
