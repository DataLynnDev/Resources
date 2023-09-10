# **Business Problem Statement:**

Adobe's Content Intelligence tool, driven by Adobe Sensei, strives to offer users a seamless content creation and management experience. In order to achieve this, we need to continually enhance the efficiency and accuracy of our AI-powered features, especially the automated content tagging and categorization system. Our end goal is to ensure that our AI recommendations align with the content preferences and interests of our diverse user base. For this, we need to identify patterns, extract actionable insights from user interaction data, and integrate these findings into our AI model for improved content recommendations.

## **Data Tables:**

**Table 1: UserInteractions**

| Column Name | Description                     | Feature Type |
|-------------|---------------------------------|--------------|
| `UserID`      | Unique identifier for a user    | Categorical  |
| `ContentID`   | Unique identifier for content   | Categorical  |
| `InteractionType` | Type of interaction (viewed, liked, shared, etc.) | Categorical |
| `Duration`    | Time spent on content (in mins) | Numeric      |
| `Tag`         | AI generated content tag        | Categorical  |

**Table 2: ContentDetails**

| Column Name | Description                              | Feature Type |
|-------------|------------------------------------------|--------------|
| `ContentID`   | Unique identifier for content            | Categorical  |
| `ContentType` | Type of content (video, article, etc.)   | Categorical  |
| `PublishedDate` | Date when the content was published    | Date         |
| `TotalViews`  | Total number of views for the content    | Numeric      |
| `AvgRating`   | Average user rating (scale of 1 to 5)    | Numeric      |

## **Questions:**

1. **Data Manipulation & Cleaning**:
Given the `UserInteractions` table from multiple servers, identify the most frequent `Tag` associated with contents that have been viewed more than 100 times. How would you ensure consistency in these tags across different servers?


2. **Probability and Statistics**:
From the `UserInteractions` table, calculate a 95% confidence interval for the average `Duration` users spend on videos. Describe any potential outliers in the dataset and how they might affect this confidence interval.


3. **Machine Learning & Modeling**:
Given the two tables, `UserInteractions` and `ContentDetails`, build a predictive model to determine the `AvgRating` of a content piece based on user interactions. Ensure to clearly specify which feature you would treat as the target variable and how you would preprocess the data for this task. Additionally, based on the predicted `AvgRating`, how can Adobe Sensei adjust the tags for better content discoverability?

   - *Target Variable: AvgRating (Numeric)*

4. **Product Design & Analytics**:
Consider a scenario where users are consistently interacting with content tagged as "Photography" but are spending less than a minute on them. Using the `UserInteractions` table, identify such patterns and propose potential improvements to Adobe's Content Intelligence tool. How can these insights be utilized to enhance the content recommendation for the user?