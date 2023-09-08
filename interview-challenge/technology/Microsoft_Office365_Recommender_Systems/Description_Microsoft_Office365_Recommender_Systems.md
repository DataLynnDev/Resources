# **Business Problem Statement:**  
Microsoft Office 365, especially PowerPoint, has been pioneering in integrating advanced recommender systems for enhancing user experience. One of its flagship features is the "Design Ideas" which suggests design layouts based on slide content. However, as with every AI-driven tool, there's room for improvement. The goal is to enhance the effectiveness of the "Design Ideas" feature by better understanding user preferences, and possibly reducing false recommendations.


## Data Table:

**SlideDesigns**

| Column Name   | Description                                    | Feature Type   |
|---------------|------------------------------------------------|----------------|
| `SlideID`     | Unique identifier for each slide               | Categorical    |
| `UserID`      | Unique identifier for the user                 | Categorical    |
| `SlideContent`| Text content of the slide                      | Text           |
| `DesignChosen`| The design layout chosen by the user           | Categorical    |
| `DesignRecommendations`| Designs recommended to the user         | Categorical (List)|
| `ClickCount`  | Number of clicks before selecting a design     | Numerical      |
| `TimeSpent`   | Time taken by the user to select a design      | Numerical      |
| `Feedback`    | User feedback (like, dislike, neutral) on the design selected | Categorical |
| `SimilarUsers`| Count of users with similar design choices     | Numerical      |



**Questions:**

1. **Data Manipulation & Cleaning:**  
   Scenario: When reviewing the `SlideDesigns` dataset, you notice that there are certain slides where the `DesignChosen` is not among the `DesignRecommendations`. This indicates a potential data inconsistency.  
   - How would you identify and handle these inconsistencies, especially if they are numerous? Can you clean this in the context of a larger dataset?


2. **Probability and Statistics:**  
   Scenario: Some users may not always be satisfied with the designs recommended. They might click through multiple designs before settling on one, or they might even reject all recommendations.  
   - Using the `ClickCount` and `Feedback`, can you hypothesize on the probability that a user will reject all recommendations based on initial design suggestions? And how does this relate to the overall satisfaction of users with the "Design Ideas" feature?

3. **Machine Learning & Modeling:**  
   Scenario: The goal of the "Design Ideas" recommender system is to minimize the time users spend selecting a design, ensuring a swift, seamless experience.  
   - Based on the `SlideContent`, `ClickCount`, and `TimeSpent`, can you create a model to predict the `DesignChosen` by the user? Clearly indicate which feature is your target variable.

4. **Product Design & Analytics:**  
   Scenario: By understanding patterns and user behaviors, it's possible to refine and introduce new design templates that cater to user preferences.  
   - Given the `DesignChosen`, `Feedback`, and count of `SimilarUsers`, can you come up with insights or suggestions to enhance the "Design Ideas" feature, ensuring more users are served designs they love? Additionally, could you devise an experimental design to test the effectiveness of introducing a new design template?
