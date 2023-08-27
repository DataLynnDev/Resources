# **Business Problem Statement:**
Microsoft's Office 365 suite offers numerous collaborative services like SharePoint and OneDrive. The Collaborative Filtering team is focused on enhancing the user experience by recommending relevant documents or files based on the actions of similar users or team members. The objective is to streamline productivity by reducing the time users spend searching for their required documents.


## **Data Table:**

**`UserActivity`**

| Column Name     | Description                                               | Feature Type      |
|-----------------|-----------------------------------------------------------|-------------------|
| UserID          | Unique identifier for each user                           | Categorical       |
| DocumentID      | Unique identifier for each document or file               | Categorical       |
| Timestamp       | Time when the user accessed/edited the document           | DateTime          |
| EditDuration    | Time duration user spent editing the document (in minutes)| Numerical         |
| DocumentType    | Type of document (e.g., Word, Excel, PowerPoint)          | Categorical       |
| DocumentSize    | Size of the document (in MB)                              | Numerical         |
| DocumentTags    | Tags associated with the document (comma-separated)       | Categorical       |
| PreviousAccess  | Last access timestamp of the document by any user         | DateTime          |


## **Questions:**

1. **Data Manipulation & Cleaning:**  
   _Scenario:_ You find out that some users have accessed certain documents even before these documents were tagged or categorized.
   
   Q: Filter the `UserActivity` table to identify records where the `DocumentTags` is missing, and provide a count of such records for each `DocumentType`.
   

2. **Probability and Statistics:**  
   _Scenario:_ Two teams A and B are using SharePoint. You observed that when a member of Team A edits a document, there's a 70% chance that a member of Team B will access it within the next week.
   
   Q: If 5 documents edited by Team A in a week are accessed by Team B, what's the probability that at least 4 of them were accessed within the next week?
   

3. **Machine Learning & Modeling:**  
   _Scenario:_ The Collaborative Filtering team wants to predict the `EditDuration` for a given document based on certain features to help improve the recommendation system.
   
   Q: Build a model using the features `DocumentType`, `DocumentSize`, and `PreviousAccess` to predict the `EditDuration`. Mention which is the target variable and the type of regression model you would use.


4. **Product Design & Analytics:**  
   _Scenario:_ The Collaborative Filtering team believes that users tend to access larger documents less frequently, which might affect the recommendation efficiency.
   
   Q: Based on the `UserActivity` table, analyze if there is a significant relationship between `DocumentSize` and the frequency of document access. If there is a relationship, how would you adjust the recommendation system?
   
