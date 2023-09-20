# **Business Problem Statement**:
With the rise of streaming platforms and the competition among them, it is imperative for Amazon Studios to produce content that resonates with its audience and makes an impact in the industry. To make informed decisions, it's important to understand viewer preferences, the influence of marketing campaigns, and how these factors affect the success of a movie or TV show.

## **Data Tables**:

**Table Name: ViewerData**

| **Column Name**         | **Description**                           | **Feature Type**   |
| --- | --- | --- |
| ViewerID                | Unique identifier for each viewer         | Categorical        |
| AgeGroup                | Age group of the viewer (e.g., 18-24)     | Categorical        |
| Region                  | Region where viewer is from               | Categorical        |
| ShowID                  | Unique identifier for shows               | Categorical        |
| Rating                  | Viewer rating for the show (1-5)          | Numerical          |
| WatchDuration           | Duration in minutes the viewer watched    | Numerical          |

**Table Name: ShowData**

| **Column Name**         | **Description**                           | **Feature Type**   |
| --- | --- | --- |
| ShowID                  | Unique identifier for each show           | Categorical        |
| Genre                   | Genre of the show (e.g., Drama, Comedy)   | Categorical        |
| ReleaseDate             | Date when the show was released           | Date               |
| MarketingSpend          | Amount spent on marketing in USD          | Numerical          |

## Questions

1. **Data Cleaning & Exploration Question:**

**Scenario**:
You have been provided with the `ViewerData` and `ShowData` tables. The data has been sourced from various departments, and before diving into deeper analysis, it's essential to ensure that the data is clean and consistent.

**Task**:
Identify and rectify any outliers in the `Rating` column. Also, check for any missing values in both tables and impute them using a suitable strategy. Ensure that the `ReleaseDate` in `ShowData` table follows a unified format of "YYYY-MM-DD".

2. **SQL Queries Question:**

**Scenario**:
Amazon Studios wants to understand the relationship between marketing expenditure and viewer ratings for each show.

**Task**:
Using a Common Table Expression (CTE), create an intermediary table that joins the `ViewerData` and `ShowData` on `ShowID`. From this, derive the average rating for each show, and its associated marketing spend. Next, using an analytic function, rank shows based on average ratings. Lastly, identify any shows that have identical average ratings (duplicates).

3. **Probability and Statistical Analysis Question:**

**Scenario**:
Amazon Studios is curious if there's a statistically significant relationship between `MarketingSpend` and the average `Rating` a show receives.

**Task**:
Firstly, formulate a hypothesis to test this relationship. Calculate the correlation coefficient between `MarketingSpend` and `Rating`. Based on the coefficient, conclude if the relationship is significant or not. Implement the calculation using appropriate statistical tools or code.

4. **Product & Business Sense Question:**

**Scenario**:
A recently released show has garnered significant attention, but its ratings are not as expected. The show had a high marketing budget, but the return, in terms of audience ratings and engagement, is lower than the predicted metrics.

**Task**:
How would you approach this situation from a business perspective? What factors, apart from ratings, would you consider, and what recommendations would you provide to the content and marketing teams based on the data from `ViewerData` and `ShowData`?