# **Business Problem Statement:**
Zillow's Search Personalization team aims to provide an unrivaled experience by personalizing property recommendations for users. As we refine our model, we need to address various challenges in data processing, statistics, machine learning, and product analytics to enhance our recommendation system. We aim to understand user behaviors, such as clicked listings, search queries, and favorited properties, to provide the best-matched properties.

## **Data Tables:**

**Table `user_interactions`**

| Column Name | Description | Feature Type |
|------------|--------------|---------------|
| `userID` | Unique identifier for each user | Categorical |
| `propertyID` | Unique identifier for each property | Categorical |
| `interactionType` | Types: 'clicked', 'searched', 'favorited' | Categorical |
| `interactionDate` | Date of interaction | Datetime |
| `searchQuery` | The search query entered by the user (only valid for 'searched' type) | Text |

**Table `property_details`**

| Column Name | Description | Feature Type |
|-------------|--------------|---------------|
| `propertyID` | Unique identifier for each property | Categorical |
| `propertyType` | e.g. 'House', 'Apartment', 'Condo' | Categorical |
| `listingPrice` | Price at which property is listed | Numerical |
| `locationState` | The state in which the property is located | Categorical |

## **Questions:**

1. **(Data Manipulation & Cleaning)**
Given the `user_interactions` table, identify the states where users have shown the most interest by favoriting properties. Assume interest is directly proportional to the number of favorited properties. From this, can you tell me the percentage of users in the top interested state that have favorited a property?


2. **(Probability and Statistics)**
Users often search for properties using specific queries. Using the `searchQuery` from the `user_interactions` table, can you determine if there is a significant correlation between the length of a search query and the number of favorited properties? Design a hypothesis test to check the same.
   
3. **(Machine Learning & Modeling)**
Based on user interactions and property details, build a predictive model to forecast whether a property will be favorited by a user. Clearly specify your target variable. Evaluate its performance using relevant metrics.
    
    **Target Variable:** Whether a property will be favorited (Binary: Yes/No).
   

4. **(Product Design & Analytics)**
Assuming Zillow wants to prioritize and feature certain properties on the homepage, using data from both tables (`user_interactions` and `property_details`), how would you design an analytics-driven strategy to select which properties to feature? Outline the criteria you would consider.