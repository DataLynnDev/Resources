# **Business Problem Statement**:
Meta's advertising platform, Facebook, serves millions of ads to users globally every day. In a bid to maximize ad performance, improve targeting accuracy, and provide superior analytics to advertisers, there is an increasing demand for sophisticated data-driven strategies. As a data scientist in the Advertising & Targeting team, your role is to harness the power of data to better align ads with the right audience, fine-tune ad bidding strategies, and unearth hidden insights that can revolutionize ad performance metrics.

## **Data Tables**:

**1. User_Activity**

| Column  | Type     | Description                                                                 |
|---------|----------|-----------------------------------------------------------------------------|
| user_id | integer  | Unique identifier for the user                                              |
| date    | datetime | The date of the activity                                                    |
| ad_id   | integer  | Unique identifier for the ad shown                                          |
| click   | binary   | 1 if the user clicked on the ad, 0 otherwise                                |
| spend   | float    | Amount advertiser paid for the ad to be shown                               |

**2. Ad_Details**

| Column        | Type     | Description                                                         |
|---------------|----------|---------------------------------------------------------------------|
| ad_id         | integer  | Unique identifier for the ad                                        |
| advertiser_id | integer  | Unique identifier for the advertiser                                |
| category      | string   | The category of the ad (e.g., electronics, apparel, services)       |
| bid_amount    | float    | Initial bidding amount by the advertiser for the ad                 |

**3. User_Profile**

| Column            | Type     | Description                                                                          |
|-------------------|----------|--------------------------------------------------------------------------------------|
| user_id           | integer  | Unique identifier for the user                                                       |
| country           | string   | The country where the user is from                                                   |
| age_group         | string   | Age bracket of the user (e.g., 18-24, 25-34)                                        |
| preferred_category| string   | Category of ads the user is more likely to interact with based on historical data    |


## **Questions**:

1. You notice a potential discrepancy in ad clicks. Specifically, users within the age group 25-34 in the country 'USA' appear to be receiving a disproportionate number of ads from the 'electronics' category.
    - Based on the tables provided, can you derive the distribution of ad categories shown to this particular user segment over the past month? Additionally, provide insights into the click-through rate (CTR) for each of these categories.


2. The CEO of Meta believes that bidding amounts might influence ad performance, particularly in the apparel category.
    - Using the data available, can you assess the correlation between the `bid_amount` and the CTR for ads in the 'apparel' category? Would it be advisable for advertisers in this category to increase their bids based on your findings?


3. There's a potential hypothesis that users tend to engage more with their `preferred_category` of ads.
    - Validate this hypothesis. For users whose preferred category is 'services', calculate the CTR for when they are shown ads from the 'services' category vs. other categories. Extend this analysis for other preferred categories as well.


4. The ad team is interested in optimizing ad spend. They're curious if certain countries or age groups are more expensive to advertise to based on user engagement.
    - Can you analyze the average `spend` per click for each `country` and `age_group`? Identify any segments where the spend per engagement is considerably high.



