# Business Problem Statement:

Google's Email Services team is interested in optimizing the performance and reliability of its Gmail service. An essential part of this process is identifying potential service disruptions proactively. Therefore, your task is to classify Gmail users into 'High_Risk', 'Medium_Risk' and 'Low_Risk' groups based on their interaction and usage patterns. This classification will help devise strategies that enhance service efficiency, minimize disruptions, and increase user satisfaction.

# Questions

## **1. "Statistical Profiling of Risk Groups in Gmail Users"**

Given Gmail's plethora of services, we observe unique interaction patterns among its users. With reference to the 'GmailUsageData' and 'GmailUserData' tables, could you statistically profile these user categories? Potential metrics may encompass email transmission frequency, chat interactions, login consistency, and accumulated email volume. Could you articulate the defining features of each group and the methodological approach employed to segment them?

## **2. "Correlational Analysis Between User Activities and Gmail Service Disruptions"**

Service interruptions may emerge from diverse sources, some potentially linked to user activities. Employing the 'GmailServiceDisruptionData' table, could you extract any associations between user activity patterns and service disruptions? Provide a correlation interpretation which could assist in user risk stratification and propose potential enhancements to the 'RiskGroup' classification according to your analysis.

## **3. "Infusion of External Tech Trends into Risk Group Analytics"**

External IT trends such as the escalation of data volume, cybersecurity threats, and shifts in technology adoption rates can mold user behavior and engagement with services. What methodology would you utilize to amalgamate this external data with our 'GmailUserData'? Give an analytic overview of how these external influencers could modify the risk profile of each user group, and any consequential recalibration required in the 'RiskGroup' classification.


## **4. "Investigation of Regional and Activity-Based Disruption Patterns"**
Service disruption patterns may vary across different user activities and geographical territories. By analyzing data from the 'GmailServiceDisruptionData' and 'GmailUserData' tables, could you investigate these patterns using statistical tools and techniques? Consider factors such as timing, frequency, and severity of disruptions. Rather than establishing correlation, focus on the descriptive statistics and visualizations that highlight any observable trends or patterns.

## **5. "Feature Engineering for Predictive Modeling"**
In preparation for creating a predictive model for 'RiskGroup' categorization, it's crucial to identify and engineer the right features. Analyze the 'GmailUserData' table and extract or create variables that may contribute to the risk profile of a user. This could involve generating new data attributes from existing ones, dealing with missing values, outliers, or applying transformations for improving model performance. Discuss your approach, rationale, and methods for feature engineering.

## **6. "Building a Predictive Model for Risk Group Categorization"**

Drawing on the insights and features you derived from preceding tasks, which variables would you flag as potential predictors for the 'RiskGroup' of Gmail users? How would you architect a predictive model that incorporates these features? Provide a methodological overview of how you would safeguard your model against overfitting. Based on the performance of your model, what potential amendments could be made to Gmail service optimization strategies to further enhance user satisfaction?

# Dataset table and Feature names
**'GmailUsageData'**

|Feature Name|Explanation|
|:-------------|:-----------|
|`User_ID`|Unique identifier for each Gmail user|
|`Login_Frequency`|The number of times the user logs into their Gmail account per given time period|
|`Email_Sent`|Number of emails sent by the user|
|`Email_Received`|Number of emails received by the user|
|`Chat_Usage`|Duration/frequency of using the chat feature|
|`Email_Storage`|Volume of emails stored in the user's Gmail account|
|`Spam_Interaction`|Interactions (like clicks) on spam emails by the user|
|`Ad_Clicks`|Number of Google ad clicks in the Gmail interface|
|`Attachments_Sent`|Number of attachments sent by the user|
|`Attachments_Received`|Number of attachments received by the user|

**'GmailUserData'**

|Feature Name|Explanation|
|:-------------|:-----------|
|`User_ID`|Unique identifier for each Gmail user|
|`User_Region`|Geographical location of the user|
|`Account_Age`|Duration since the user's account was created|
|`User_Active_Hours`|Typical hours of activity of the user on Gmail|
|`Device_Type`|Type of device used by the user for Gmail access (Mobile/Desktop)|
|`Browser_Type`|Browser used by the user for accessing Gmail|
|`Risk_Group`| Risk of the user, classified into high medium and low|

**'GmailServiceDisruptionData'**

|Feature Name|Explanation|
|:-------------|:-----------|
|`User_ID`|Unique identifier for each Gmail user|
|`Disruption_Duration`|Duration of service disruption experienced by the user|
|`Disruption_Type`|Type of disruption experienced (could be categories like login issues, email sending/receiving issues, etc.)|
|`Disruption_Time`|Time of service disruption|
|`Resolution_Time`|Time taken to resolve the disruption|

**'ExternalTechTrendsData'**

|Feature Name|Explanation|
|:-------------|:-----------|
|`Trend_ID`|Unique identifier for each recorded trend|
|`Trend_Type`|Type of IT trend (e.g., cybersecurity threat, technology adoption change)|
|`Trend_Impact`|Impact level of the trend|
|`Trend_Start_Date`|Start date of the trend|
|`Trend_End_Date`|End date of the trend|

# Question 1 Solution
For answering this question, we need to perform a detailed exploratory data analysis (EDA) on the 'GmailUsageData' and 'GmailUserData' tables. The methodological approach will consist of descriptive statistics, group-wise analysis and graphical representations (like box plots, histograms or scatter plots).

The key metrics of interest could be:
1. `Login_Frequency`
2. `Email_Sent`
3. `Chat_Usage`
4. `Email_Storage`

This would be conducted across different risk groups, as defined in `Risk_Group`.

**code block 1**

The `describe()` method in Pandas provides descriptive statistics that summarize the central tendency, dispersion, and shape of a dataset's distribution. This includes the mean, median, min, max, standard deviation, and quartiles of these features for each risk group.

The box plots visually show the distribution and variation in the metric for each risk group. They provide insights on the median (middle line in the box), IQR (interquartile range - represented by the box), and potential outliers (points beyond the whiskers).

Using these statistics and plots, we can observe and define the characteristics of each risk group.

Please note that the specific features and characteristics defining each risk group would depend on the actual data, and the code snippet provided above only gives a general guideline on how to approach this problem.


# Question 2 solution


To uncover any associations between user activity patterns and service disruptions, we will need to perform a correlational analysis. The activities can include Login Frequency, Email Sent, Chat Usage, etc., and these will be checked against the Disruption Duration from the GmailServiceDisruptionData table.

Firstly, we will need to merge the GmailServiceDisruptionData with GmailUsageData using the common field `User_ID`.

**code block 2**

Then, we calculate the correlation matrix for our DataFrame. Correlation ranges from -1 to 1, where values close to 1 indicate a strong positive correlation, values close to -1 indicate a strong negative correlation, and values close to zero indicate no correlation.

**code block 3 & 4**

The heatmap provides an overview of the correlations. It helps us to determine which variables are most related to each other and which ones are not related at all.

In our case, we are specifically interested in correlations with 'Disruption_Duration'. After this heatmap, you can inspect these correlation values closely to understand the relationships.

Note that the exact interpretation and which features to focus on would depend on the actual data and the correlation values calculated.

# Question 3 solution

1. **Mapping 'Trend_Type' to corresponding features in 'GmailUserData':** This could be done through a domain knowledge-driven approach, where we make assumptions about how different trend types might impact different aspects of user behavior. For example, a trend related to cybersecurity threats might impact 'Spam_Interaction' or 'Ad_Clicks', while a trend related to technology adoption might impact 'Device_Type' or 'Browser_Type'.

2. **Computing a 'Trend_Impact_Score':** This could be done by first determining the duration of overlap between the trend's start and end dates and the user's active period on Gmail (from 'Account_Age' and 'User_Active_Hours'). The more a user's active period overlaps with a high impact trend, the higher their 'Trend_Impact_Score' should be. Additionally, the score should be weighted by the 'Trend_Impact' of each trend.

3. **Adding 'Trend_Impact_Score' to 'GmailUserData':** This is straightforward and involves creating a new column in the 'GmailUserData' DataFrame.

4. **Normalizing the 'Trend_Impact_Score':** This is also straightforward and can be done using a min-max normalization to rescale the scores to the range [0, 1].

Given the abstract nature of this problem, we won't provide a fully concrete code solution here. Only the "Account_Age" is consider in this scenario. For different "Account_Age" and its relation to "Trend_Impact_Score": The logic in the provided code is that older accounts (greater than median age) are considered more exposed to a trend (related to account age), hence receiving a full trend impact. In contrast, younger accounts (less than median age) are considered less exposed, so they receive only half the impact. The underlying assumption might be that older accounts have seen more changes and are more prone to shifts in IT trends.

This new 'Trend_Impact_Score' can then be used to modify the risk profile of each user group. For example, if a user has a high 'Trend_Impact_Score', it indicates that they are more likely to be affected by current IT trends, so they might need to be moved to a higher risk group.

**code block 5 & 6**

If a user's 'Trend_Impact_Score' is 0, it suggests that, based on the data and the assumptions made in our analysis, this user is expected to be the least impacted by the current external IT trends. This could be due to various factors depending on how we've calculated the score, such as the user's behavior, their device type, the age of their account, etc.

On the other hand, if a user's 'Trend_Impact_Score' is 1, it suggests that this user is expected to be the most impacted by the current external IT trends. Again, the specific reasons for this would depend on the details of our analysis.


**Risk Group Recalibration:**
If the 'Trend_Impact_Score' is 1, the risk group of the user will be upgraded - 'Low' risk users will be reclassified as 'Medium' risk, and 'Medium' risk users will be reclassified as 'High' risk. 'High' risk users will remain in the 'High' risk group.

If the 'Trend_Impact_Score' is 0, there will be no change in the risk group.

The goal of this approach is to dynamically adjust the user risk group based on the influence of external tech trends. This methodology could potentially provide a more accurate, real-time representation of user risk. However, it assumes a direct and considerable impact of tech trends on user risk behavior, which should be verified by further analysis or industry knowledge.

**code block 7**

This proposed method to recalibrate the 'Risk_Group' feature based on the 'Trend_Impact_Score' is logical. However, it might be overly simplistic in real-world scenarios. Here are a couple of considerations:

1. Trend_Impact_Score: This score is currently binary (0 or 1), but real-world trends might have a range of impacts. It might be worth considering a more nuanced scoring system, like a scale from 0 to 1, with decimal points to better reflect the intensity of the trend impact.

2. Risk Group: The shift from Low to Medium or Medium to High could potentially oversimplify or exaggerate the risks involved. Not all users with a 'Low' risk level will instantly become a 'Medium' risk due to a trend's impact. It might be more accurate to use a numeric score to represent risk and adjust that score based on the Trend_Impact_Score.

That said, here is an updated version of your proposed methodology:

- Convert the 'Risk_Group' feature to a numeric scale (e.g., Low = 1, Medium = 2, High = 3).
- Create a 'Trend_Impact_Adjustment' score, which is a scaled version of the Trend_Impact_Score (for example, 0 to 0.5).
- Create a new 'Adjusted_Risk_Score' that sums the 'Risk_Group' and 'Trend_Impact_Adjustment'. You could also consider multiplication if you want the impact to be proportional to the existing risk.
- Reclassify 'Adjusted_Risk_Score' into new risk groups, if necessary, based on new thresholds.

Remember, the crucial point here is that any methodology we use should be validated. The newly calculated risk levels should indicate the actual observed risks (outcomes), or it could lead to incorrect conclusions and actions.

# Question 4 solution

1. **Data Preparation**: Load and merge the 'GmailServiceDisruptionData' and 'GmailUserData' tables.

2. **Exploratory Data Analysis**: Look for initial insights from the dataset by employing descriptive statistics and data visualizations.

3. **Disruption Analysis Based on Region and Activity**: Analyze the disruption patterns based on regions and user activities. You can also consider using the time series data to analyze disruption patterns over time.

**code block 7**


**Result Explanation**

The bar plots give a clear visualization of how disruption duration varies across different regions, user activity hours, and disruption types. For instance, if certain regions show longer average disruption durations, this could indicate the need for additional infrastructure or maintenance in those areas. Similarly, if disruptions are more frequent during specific user activity hours or for certain disruption types, these could be areas for Google's Email Services team to focus on for improving service reliability.

# Question 5 solution

1. **Merge DataFrames**: Merge 'GmailUserData', 'GmailUsageData', and 'GmailServiceDisruptionData' on 'User_ID'.
2. **Inspect Data**: Check the data types and non-null counts for each column.
3. **Data Cleaning**: Drop unnecessary columns like 'Disruption_Type'.
4. **Data Transformation**: Use one-hot encoding to transform categorical columns ('User_Region', 'Device_Type', and 'Browser_Type') into binary variables.
5. **Combine DataFrames**: Concatenate the one-hot encoded DataFrame with the original one.
6. **Final Clean Up**: Drop the original categorical columns and 'Disruption_Time' from the DataFrame.
7. **Final Inspection**: Check the data types and structure of the final DataFrame.

**code block 9 & 10**

The code merges the three tables that share 'User_ID', then checks the information of the resulting DataFrame. 'Disruption_Type' column gets dropped as it might not be significant for user risk prediction.

Next, the one-hot encoding process is initialized, and the transformation gets applied to 'User_Region', 'Device_Type', and 'Browser_Type'. A DataFrame is created from the encoded variables, and it gets concatenated with the original DataFrame. The original categorical features and 'Disruption_Time' are then dropped from the DataFrame.

Lastly, the final DataFrame's info is printed to review the final structure and data types before building the predictive model.

# Question 6 solution

**Predictive Variables:**
To determine the potential predictive variables for the 'RiskGroup' of Gmail users, we would need to evaluate the data available. Here are some possible features:

1. Frequency of login
2. Duration of usage per session
3. Number of sent and received emails
4. Size of attachments sent or received
5. Number of reported spam emails
6. Frequency of password changes
7. Usage of two-factor authentication
8. Level of interaction with promotions or social tabs

**Model Architecture:**
The provided code uses a Random Forest Classifier, a versatile algorithm that works well for both binary and multiclass classification problems. This algorithm creates a set of decision trees from a randomly selected subset of the training set, which then aggregates votes from different decision trees to decide the final class of the test object.

**Overfitting Safeguard:**
Random Forest inherently protects against overfitting by averaging out the bias of individual trees, given a sufficiently large number of trees. However, you can further guard against overfitting by:

1. Tuning model parameters like the number of trees (n_estimators) or tree depth (max_depth).
2. Using cross-validation methods (like k-fold cross-validation) to generate unbiased estimates of model performance.
3. Regularizing the model (if applicable).
4. Monitoring the performance of the model not only on the training set, but also on the validation set.

**code block 11 & 12**

**Model Evaluation and Improvement:**
The provided code calculates the F1 score as a measure of the model's performance. The F1 score is the harmonic mean of precision and recall and is a good metric when classes are imbalanced.

Based on the performance of the model, and particularly the feature importances output, potential improvement could be made to Gmail's service. For instance, if two-factor authentication usage and frequency of password changes are strong predictors of lower risk, Gmail could encourage these behaviors through user education or nudges. Similarly, if interaction with certain types of email correlates with higher risk, Gmail could improve its filtering or warning systems.

Please note that this is a general approach and should be adjusted as per the specific context and available data.
