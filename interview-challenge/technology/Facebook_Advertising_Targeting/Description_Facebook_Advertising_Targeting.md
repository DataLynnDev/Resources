# **Business Problem Statement**:
Due to the ever-changing nature of user behaviors and interests, there's a pressing need to continually evaluate and optimize the targeting algorithms for our Facebook Advertising. This ensures that ads are served to the most appropriate audience, leading to better user experience and enhanced ad revenue.

## **Data Tables**:

**Table 1**: `UserAdEngagement`

| Column Name    | Description                                  | Feature Type  |
|----------------|----------------------------------------------|---------------|
| `userID`       | Unique identifier for a user                 | Numeric      |
| `adID`         | Unique identifier for an ad                  | Numeric      |
| `date`         | Date when the ad was shown                   | Date         |
| `isClicked`    | Whether the ad was clicked (1 for yes, 0 for no)| Binary     |
| `timeSpent`    | Time user spent on the ad (in seconds)       | Numeric      |
| `userSegment`  | Categorical user segment for targeting       | Categorical  |

**Table 2**: `AdCampaignInfo`

| Column Name    | Description                                  | Feature Type  |
|----------------|----------------------------------------------|---------------|
| `adID`         | Unique identifier for an ad                  | Numeric      |
| `campaignID`   | Unique identifier for an ad campaign         | Numeric      |
| `adCategory`   | Category of the ad (e.g., Fashion, Electronics) | Categorical |
| `startDate`    | Start date of the ad campaign                | Date         |
| `endDate`      | End date of the ad campaign                  | Date         |

## Questions

1. **Question 1** (Data Cleaning & Exploration):

**Scenario**:  
You've received the `UserAdEngagement` dataset. Before proceeding with the analysis, it's crucial to ensure data cleanliness and integrity.

**Task**:
Identify and handle any missing values and outliers in the `timeSpent` column. Additionally, derive insights about the `userSegment` distribution and its influence on `isClicked`.

2. **Question 2** (SQL Queries):

**Scenario**:  
You've been asked to evaluate the performance of different ad campaigns and their respective categories.

**Task**:  
Using the `UserAdEngagement` and `AdCampaignInfo` tables, identify the `adCategory` that has the second-highest average `timeSpent` for ads clicked (`isClicked`=1). Furthermore, find the `adCategory` where the maximum `timeSpent` on clicked ads is less than or equal to 300 seconds.

3. **Question 3** (Probability and Statistical Analysis):

**Scenario**:  
There's a hypothesis that users from two specific segments, let's say SegmentA and SegmentB, click on ads independently of each other.

**Task**:
Calculate the probability that a randomly selected user from SegmentA clicks on an ad and a randomly selected user from SegmentB does not click on the same ad. Validate this probability using both the formula and the data in `UserAdEngagement` table.

4. **Question 4** (Product & Business Sense):

**Scenario**:  
Considering that user engagement directly impacts ad revenue, there's an initiative to introduce an "Ad Feedback" button similar to the "like" button, allowing users to provide feedback on ads.

**Task**:  
Suggest potential advantages and pitfalls of introducing such a button. Furthermore, based on the `UserAdEngagement` dataset, propose key metrics to measure the effectiveness of this new feature.