## Business Problem Statement

The Ads Measurement team at TikTok is looking to optimize the platform's advertising efficiency. By leveraging experimental design and causal inference, the team aims to assist advertisers in measuring and enhancing the true business value they generate through TikTok ads.

---

### Data Tables

**1. Table: `AdsPerformance`**

| Column Name | Description                              | Feature Type   |
|-------------|------------------------------------------|----------------|
| AdID        | Unique identifier for the advertisement  | Categorical    |
| Date        | Date of the advertisement displayed     | Date           |
| VideoType   | Type of video content in the ad          | Categorical    |
| Impressions | Number of times the ad was displayed    | Numerical      |
| Clicks      | Number of clicks on the ad              | Numerical      |
| Duration    | Average watch duration (in seconds)     | Numerical      |

**2. Table: `UserRetention`**

| Column Name | Description                                 | Feature Type   |
|-------------|---------------------------------------------|----------------|
| UserID      | Unique identifier for the user             | Categorical    |
| Date        | Date of user activity                      | Date           |
| AdID        | Ad the user interacted with                | Categorical    |
| Retention   | Whether the user returned the next day     | Binary         |

**3. Table: `AdContent`**

| Column Name   | Description                           | Feature Type   |
|---------------|---------------------------------------|----------------|
| AdID          | Unique identifier for the advertisement| Categorical    |
| ContentTheme  | Theme or category of the ad content   | Categorical    |
| AdBudget      | Total budget allocated for the ad     | Numerical      |
| TargetDemographic | Target audience for the ad         | Categorical    |
| CPA           | Cost per action for the ad            | Numerical      |

---

**Questions**:

1. **SQL & Data Manipulation**: Using the `AdsPerformance` table, give a SQL query that aggregates video type-based impressions and then compares these aggregated values to identify the most popular video type for advertising.

2. **Product Design & Analytics**: First, for each day, calculate percentage of users that show activities for at least 2 consecutive days. If the data in `UserRetention` table indicates a significant drop in day 2 retention rate for users who clicked on ads, how would you investigate the causes and recommend improvements to ensure TikTok ads are engaging and retaining users?

3. **Machine Learning & Modeling**: Using the `AdsPerformance` and `AdContent` tables, design a model to predict the CPA based on video type, content theme, impressions, clicks, average watch duration, ad budget, and target demographic. Discuss the trade-offs you might face when setting the learning rate of your model.

4. **Product Design & Analytics**: TikTok launch a new feature to all its advertisers. How to measure the userfulness of the new feature? i.e., whether it boosts ad performance in terms of CPA(cost per action). Answer the 2 subquestions:
  - A/B test is not available in this setting. How would you approach the problem?
  - Not all the advertisers adopt the feature. For non-adopter, they see and average of 5% increase in CPA, whereas the number is 2% for adopters. How to persuade adopters to continue to use the feature? (Hint: stakeholders want to see decrease in CPA. Despite lower than 5%, 2% is still an increase)
  
  
