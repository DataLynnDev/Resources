# **Business Problem Statement**:

Netflix wants to dig deeper into the intricacies of its marketing strategies. With various marketing channels, numerous campaigns, and a myriad of customer behaviors, the company wishes to find the most effective ways to engage potential subscribers. The objective is to use Marketing Mix Modeling (MMM) to decipher the nuances of these factors and provide a comprehensive strategy to ensure that every marketing dollar is spent efficiently.

## Data Tables:

1. **Table Name: Marketing_Spend**

| Column Name     | Description                                           | Data Type     |
|-----------------|-------------------------------------------------------|---------------|
| date            | Date of the marketing spend                           | DATE          |
| channel         | Name of the marketing channel (e.g., TV, Social Media)| VARCHAR       |
| amount_spent    | Amount spent on that channel on that date             | FLOAT         |
| campaign_id     | Unique identifier for specific campaigns             | INT           |
| campaign_type   | Type of campaign (e.g., teaser, full ad, collaboration) | VARCHAR      |
| target_audience | Demographics the campaign targets (e.g., 18-24, Families) | VARCHAR   |
| region          | Geographic region the campaign targets               | VARCHAR       |

2. **Table Name: User_Conversions**

| Column Name     | Description                                           | Data Type     |
|-----------------|-------------------------------------------------------|---------------|
| user_id         | Unique identifier for each user                       | INT           |
| date            | Date of conversion/purchase                           | DATE          |
| channel         | Marketing channel the user came from                  | VARCHAR       |
| subscription_id | Type of subscription chosen by the user               | VARCHAR       |
| device          | Device used by the user for conversion (e.g., Mobile, Desktop) | VARCHAR   |
| referral        | Was the conversion from a referral?                   | BOOLEAN       |
| trial_taken     | Did the user avail a trial version before subscribing?| BOOLEAN       |

3. **Table Name: User_Info**

| Column Name     | Description                                           | Data Type     |
|-----------------|-------------------------------------------------------|---------------|
| user_id         | Unique identifier for each user                       | INT           |
| age             | Age of the user                                       | INT           |
| gender          | Gender of the user                                    | VARCHAR       |
| country         | Country where the user is based                       | VARCHAR       |
| joined_date     | Date when the user first joined Netflix               | DATE          |
| referral_source | The source from which the user got to know about Netflix (e.g., Friend, Web Search) | VARCHAR  |
| preferred_genre | The user's most-watched genre on Netflix              | VARCHAR       |

## Questions:

1. Using the `User_Info` table, determine which age groups prefer which genres. How does this information correlate with the target audiences of different campaign types from the `Marketing_Spend` table?

2. Combining the Marketing_Spend and User_Conversions tables, determine the total spend of each marketing channel and calculate the Cost Per Acquisition (CPA) for each channel over the specified period. Can you infer which channel gave the best return on investment based on CPA?

3. From the `User_Info` and `User_Conversions` tables, analyze which marketing channels are most effective for different genders in various countries. Are there certain channels that resonate more with a particular gender in a specific region?

4. Using the three tables, develop a machine learning model that predicts the type of subscription a new user will choose. Consider factors like marketing channel, campaign type, target audience, user device, age, gender, and preferred genre. Evaluate the model's performance, and discuss its implications.

5. With insights derived from all tables, provide guidance for Netflix's marketing approach for the upcoming year. How should they adjust their campaigns based on user demographics and preferences, and the effectiveness of different marketing channels?
