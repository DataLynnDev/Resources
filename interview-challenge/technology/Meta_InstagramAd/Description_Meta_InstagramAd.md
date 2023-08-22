# Business Problem Statement
Instagram is aiming to enhance the user engagement and experience by analyzing user interactions with posts, focusing on improving the advertisement targeting model, and optimizing the content recommendations. The problem includes understanding various user interactions, the effectiveness of advertisements, and identifying key trends in user behaviors.

## Data Tables

**Table 1: User_Interactions**

| Column Name      | Description                              | Feature Type  |
|------------------|------------------------------------------|---------------|
| user_id          | Unique ID for the user                   | Categorical   |
| post_id          | Unique ID for the post                   | Categorical   |
| interaction_type | Type of interaction (like, share, etc.)  | Categorical   |
| interaction_date | Date of interaction                      | Date          |

**Table 2: Advertisements**

| Column Name  | Description                               | Feature Type  |
|--------------|-------------------------------------------|---------------|
| ad_id        | Unique ID for the advertisement           | Categorical   |
| post_id      | Unique ID for the post containing the ad  | Categorical   |
| views        | Number of views on the ad                 | Numeric       |
| clicks       | Number of clicks on the ad                | Numeric       |
| date         | Date of ad display                        | Date          |

## Questions

1. **Analyzing Interaction Patterns:**
   - Instagram has noticed a significant drop in user interactions over the past month. Investigate the data and identify any specific trends or patterns that might explain this phenomenon.

2. **Optimizing Advertisement Effectiveness:**
   - Given the data on user interactions with posts and advertisement views and clicks, propose a strategy to improve ad targeting. How would you leverage user behavior and engagement to increase ad effectiveness?

3. **Content Recommendation Enhancement:**
   - Analyze the interaction data to identify what types of content are most engaging to the users. Propose a method to enhance content recommendation and increase overall user engagement.



