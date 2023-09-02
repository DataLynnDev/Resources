# **Business Problem Statement:**

Indeed's mission is to help people find jobs. Our recommendation system is at the heart of this mission, aiming to suggest the most relevant job postings to job seekers. With a combination of user data and job listings, our recommendation engine has to be robust, efficient, and adaptable. Your challenge is to enhance our system's ability to make personalized job recommendations to our users.

## **Data Table:**

**JobRecommendations**

| Column Name | Description                       | Feature Type     |
|-------------|-----------------------------------|------------------|
| user_id     | Unique ID for every user          | Categorical      |
| job_id      | Unique ID for every job listing   | Categorical      |
| job_desc    | Description of the job listing    | Text             |
| user_prefs  | User's job preferences            | Text             |
| activity    | Past user activity for the job    | Categorical (Viewed/Not-Viewed, Applied/Not-Applied) |
| feedback    | User feedback for the job         | Categorical (Liked/Not-Liked) |
| job_category| Type of job (e.g. tech, finance)  | Categorical      |
| user_rating | User's rating for the job (1-10)  | Numerical        |
| job_salary  | Salary range offered by the job   | Numerical        |
| job_location| Location of the job               | Categorical      |


## **Questions:**

1. **Content-Based Filtering Challenge:**
    - Given the `job_desc` and `user_prefs`, can you build a model that scores how well a job matches a user's preferences? Use the `feedback` column as your target variable to train your model. What features would you derive from the text data, and how would you approach this problem?

2. **SQL Data Manipulation Challenge:**
    - Among the users who have a rating (`user_rating`) above 7 for tech jobs (`job_category = 'tech'`), can you identify those who have viewed but not applied to more than 3 jobs? Describe your approach using SQL queries.

3. **Collaborative Filtering Challenge:**
    - Using the `activity` and `feedback` columns, can you identify patterns or clusters of users who have similar preferences? How would you handle the cold-start problem for new users in this context?

4. **Hybrid Recommendation Challenge:**
    - Given your findings and models from the previous questions, how would you design a hybrid recommendation system to leverage both content-based and collaborative filtering? Take into consideration a user who has recently viewed multiple jobs but hasn't provided any feedback yet. How would you prioritize which jobs to recommend to them next?