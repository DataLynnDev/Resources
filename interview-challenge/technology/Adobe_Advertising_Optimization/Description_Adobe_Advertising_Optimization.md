# **Business Problem Statement:**

As Adobe Advertising Cloud is poised to offer an end-to-end platform for managing and optimizing advertising campaigns using advanced AI and data science techniques, there is a constant need to refine our algorithms and strategies. The overarching business challenge is to maximize the return on investment for our advertising clients while providing them with a unified view of ad performance across various channels.

## **Data Tables:**

**Table 1: AdPerformance**

| Column Name  | Description                                       | Feature Type   |
|--------------|---------------------------------------------------|----------------|
| `CampaignID`   | Unique identifier for the advertising campaign    | Categorical    |
| `Channel`      | Channel where ad was displayed (e.g., Web, Mobile)| Categorical    |
| `AdSpend`      | Amount spent on the ad in USD                     | Numeric        |
| `Impressions`  | Number of times the ad was shown                  | Numeric        |
| `Clicks`       | Number of clicks on the ad                        | Numeric        |
| `Conversions`  | Number of conversions after clicking the ad       | Numeric        |
| `AdDuration`   | Duration for which the ad was displayed in seconds| Numeric        |

**Table 2: AudienceDemographics**

| Column Name   | Description                            | Feature Type   |
|---------------|----------------------------------------|----------------|
| `AudienceID`    | Unique identifier for the audience group| Categorical    |
| `CampaignID`    | Corresponding campaign ID               | Categorical    |
| `AgeRange`      | Age range of the audience               | Categorical    |
| `Gender`        | Gender of the audience                  | Categorical    |
| `DeviceType`    | Device used (e.g., Tablet, Smartphone)  | Categorical    |



## **Questions:**

1. Given the `AdPerformance` table, perform an exploratory analysis on ad campaigns across different channels. Derive insights on which channels are yielding the best return on investment. Visualize the correlation between AdSpend, Impressions, Clicks, and Conversions.



2. We suspect that not all campaigns are equally effective for different age ranges. From the `AudienceDemographics` and `AdPerformance` tables, identify which age range shows the highest conversion rate for each campaign. Based on this analysis, suggest how to adjust the advertising strategy for different campaigns to target optimal age ranges.



3. Using the `AdPerformance` table, build a model predicting `Conversions` based on other available features. Clearly state the assumptions you've made and how you'll handle potential multicollinearity.

    - *Target Variable:* `Conversions`
    
4. We want to understand how different genders react to ads on different devices. Using the `AudienceDemographics` table, find out which gender, on average, has a higher conversion rate for each device type. Based on this analysis, recommend strategies to adjust ad targeting.