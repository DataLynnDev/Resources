# **Business Problem Statement**:
IBM's Cognitive Computing team wants to enhance the capability of Watson by better understanding customer inquiries about a range of products. Specifically, we want to focus on the feedback generated for our products in the medical domain. This involves not just understanding the sentiment of the feedback but also categorizing them into specific problem areas, predicting the urgency of addressing the feedback, and determining the potential impact on future product upgrades.

## **Data Table**:

`Medical_Feedback`

| Column Name | Description | Feature Type |
|:-----------:|:-----------:|:------------:|
| `Feedback_ID` | Unique identifier for each feedback | Categorical |
| `Product_Name` | Name of the IBM medical product | Categorical |
| `Customer_Name` | Name of the customer providing feedback | Categorical |
| `Feedback_Text` | Text of the feedback | Textual |
| `Timestamp` | Time when the feedback was provided | Datetime |
| `Feedback_Type` | Type of feedback (e.g., Bug, Feature Request, General Feedback) | Categorical |
| `Image_Attachment` | Image provided by the customer (if any) | Image |
| `Feedback_Rating` | Rating provided by the customer on a scale of 1-10 | Numerical |
| `Urgency_Predicted` | Predicted urgency level (Low, Medium, High) | Categorical (Target Variable) |
| `Response_Time` | Time taken by IBM to respond to the feedback | Numerical |

## **Questions**:

1. **(Data Manipulation & Cleaning)**
   *Scenario*: You notice that several feedback entries in the `Medical_Feedback` table have missing `Feedback_Rating` values. However, you remember that a recent marketing survey (stored in another table) might contain some of these missing ratings.
   - How would you integrate the `Medical_Feedback` table with the marketing survey to fill the missing ratings?
   

2. **(Probability and Statistics)**
   *Scenario*: Your team is curious about the distribution of feedback types over time.
   - Based on the `Timestamp` and `Feedback_Type`, can you analyze the monthly trend of each feedback type and predict which month might see the highest number of 'Bug' type feedbacks?


3. **(Machine Learning & Modeling)**
   *Scenario*: Your product team is keen on prioritizing feedbacks. They believe that understanding the urgency is crucial.
   - Build a predictive model using the available features in the `Medical_Feedback` table to predict the `Urgency_Predicted` of each feedback. Remember to justify your choice of model.
     
   **Target Variable**: `Urgency_Predicted`


4. **(Product Design & Analytics)**
   *Scenario*: A consulting team at IBM is preparing a presentation for a new potential client in Healthcare Marketing for Cancer research in India. They need insights drawn from the feedback received about IBM's medical products.
   - Using the `Feedback_Text` and `Image_Attachment`, can you identify any recurring themes or patterns that might be of interest to the consulting team? Furthermore, can you use this information to propose a potential feature or enhancement for our medical products tailored to the Cancer research industry in India?