# Business Problem Statement:
TikTok's eCommerce team is striving to optimize the marketing campaigns for various products within the TikTok platform. The primary objectives include identifying the ideal target audience, optimizing spending on marketing, predicting the users' behaviors, and evaluating the efficiency of different advertising channels. We aim to analyze the historical data to uncover insights that could drive higher engagement, increase daily active users (DAU), and generate more revenue through product sales. Specifically, the challenge is to understand how users interact with ads, identify any unusual behavior, and formulate strategies to boost eCommerce activities within the app.

## Data Tables:
#### Table 1: `user_activity`
| Column Name | Description                                    | Feature Type |
|-------------|------------------------------------------------|--------------|
| user_id     | Unique identifier for users                    | Categorical  |
| campaign_id | Unique identifier for marketing campaigns        | Categorical
| timestamp   | Timestamp of the activity                      | Datetime     |
| product_id  | Unique identifier for products                 | Categorical  |
| action_type | Action type (e.g., click, view, purchase)      | Categorical  |
| platform    | Platform where the activity occurred (e.g., iOS, Android) | Categorical |

#### Table 2: `marketing_campaigns`
| Column Name | Description                                      | Feature Type |
|-------------|--------------------------------------------------|--------------|
| campaign_id | Unique identifier for marketing campaigns        | Categorical  |
| start_date  | Start date of the campaign                       | Datetime     |
| end_date    | End date of the campaign                         | Datetime     |
| budget      | Budget allocated for the campaign                | Numeric      |
| channel     | Marketing channel (e.g., social media, email)    | Categorical  |

## Questions:

1. **SQL and Analytics**: Identify the top 3 products that have the most interactions from 2022-01-01 to 2022-12-31, and evaluate how different marketing channels have influenced these interactions. Then, propose a strategy to optimize marketing spend based on this analysis.

2. **Progressive Machine Learning & Modeling**:
   - a. Utilizing the `user_activity` and `marketing_campaigns` tables, develop a predictive model that could detect any unusual (or wired) behavior in users' interactions with products.
   - b. Analyze the importance of features within your model and identify the trade-offs between different hyperparameters such as learning rate. Explain your choice of algorithm (e.g., Random Forest, XGBoost).
   - c. Use the insights from the model to propose how we can improve the performance of the eCommerce activities within the TikTok platform.

3. **Product Design & Analytics**: Analyze the patterns of user behavior across different platforms (e.g., iOS, Android) and for different actions (e.g., click, view, purchase). Then, design a case study to test a new marketing strategy that could potentially increase DAU.
   - a. Outline the process of AB testing you would follow to validate this strategy.
   - b. Explain how you would measure success and the key metrics involved.

4. **Probability and Statistics Question**: Given a product and its marketing campaigns, estimate the probability of a user purchasing the product after viewing an ad. Use causal knowledge to explain how different factors might affect this probability.

