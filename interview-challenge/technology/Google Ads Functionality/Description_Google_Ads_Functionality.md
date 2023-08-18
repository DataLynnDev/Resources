# Business Problem Statement:
In order to maintain Google Ads' market leadership and improve the effectiveness of our ad targeting, we need to refine our algorithmic understanding of how users interact with ads and how these interactions correlate with advertiser-specified keywords. Our goal is to maximize ad relevance, ensuring advertisers receive better value for their bids and users are shown ads more tailored to their interests.


## Data Tables:

**Table 1: UserInteractions**

| Column Name | Description                       | Feature Type |
|-------------|-----------------------------------|--------------|
| UserID      | Unique ID for each user           | Categorical  |
| WebPageID   | ID of the webpage visited         | Categorical  |
| SessionTime | Time user spent on a given page   | Numerical    |
| AdClicked   | ID of the ad clicked by the user  | Categorical  |


**Table 2: AdInformation**

| Column Name | Description                       | Feature Type |
|-------------|-----------------------------------|--------------|
| AdID        | Unique ID for each advertisement  | Categorical  |
| KeywordList | List of keywords associated       | Categorical  |
| AdvertiserID| ID of the advertiser              | Categorical  |
| BidAmount   | Amount bid for the advertisement  | Numerical    |

**Table 3: WebContent**

| Column Name | Description                       | Feature Type |
|-------------|-----------------------------------|--------------|
| WebPageID   | Unique ID for each webpage        | Categorical  |
| Content     | Text content of the webpage       | Text         |


## Questions:

1. Given the `AdInformation` and `UserInteractions` tables, analyze the distribution of `BidAmount` for ads that are clicked on vs. those that are not. Are there any noticeable trends in the bidding amount for ads that are more frequently clicked?


2. Using the `WebContent` and `AdInformation` tables, create a model to determine how well the content of a webpage matches with the keywords of ads displayed on them. What factors play a significant role in ensuring a good match?


3. From the `UserInteractions` table, calculate the probability that if a user spends more than a certain threshold of time (`SessionTime`) on a webpage, they are more likely to click on an ad.


4. Imagine we are launching a new advertising campaign for a major advertiser. Using the `AdInformation` and `UserInteractions` tables, determine the predicted performance of the new campaign based on historical data of similar campaigns. You may use "electronics", "books" as the key words for the new advertising campaign.
