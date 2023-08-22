# Business Problem Statement
The Facebook Marketplace team aims to enhance user engagement, ensure the authenticity and quality of listings, and optimize the recommendation engine for buyers and sellers. The overarching goal is to create a more personalized and efficient buying/selling experience while minimizing fraudulent activities. As part of these efforts, the team needs a seasoned data scientist to analyze the existing data, develop predictive models, and extract actionable insights.


## Data Table
| Column Name              | Description                                          | Feature Type  |
|--------------------------|------------------------------------------------------|---------------|
| user_id                  | Unique identifier for the user                       | Categorical   |
| item_id                  | Unique identifier for the item                       | Categorical   |
| category                 | Category of the listed item                          | Categorical   |
| price                    | Price of the item                                    | Numerical     |
| date_listed              | Date when the item was listed                        | Date          |
| date_sold                | Date when the item was sold                          | Date          |
| rating                   | Rating of the transaction (1 to 5)                   | Numerical     |
| status                   | Status of the listing (active, sold, removed)        | Categorical   |
| fraud_flag               | Flag indicating if the listing was fraudulent (0/1)  | Categorical   |
| buyer_rating             | Rating given by the buyer (1 to 5)                   | Numerical     |

## Questions

1. **Question:**
   - **Scenario:** The team is facing challenges with fraudulent listings on the Marketplace. Using the given data, identify patterns or behaviors that might suggest a listing is fraudulent.
   
2. **Question:**
   - **Scenario:** After identifying potential fraudulent listings, you want to create a predictive model to automatically flag suspicious listings. Using the features identified in the previous question, build a machine learning model to predict the `fraud_flag` for new listings. Explain the model's approach, and how you would evaluate its performance.
   - **Target Variable:** `fraud_flag` (Categorical)

3. **Question:**
   - **Scenario:** Now, the marketing team wants to boost user engagement by understanding which categories are most popular and how pricing affects the time it takes to sell an item. Analyze the relationship between `category`, `price`, and the time taken to sell an item. Propose strategies to sellers for pricing their items in different categories.

