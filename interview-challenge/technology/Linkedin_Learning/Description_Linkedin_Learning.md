# Business Problem Statement:
The LinkedIn Learning team is dedicated to delivering high-quality online courses to help professionals advance in their careers. The key to maintaining and enhancing the quality and relevance of the courses lies in understanding user engagement and course effectiveness. The data analyst role is crucial in this aspect as analyzing data pertaining to course completions, user feedback, and engagement levels will provide insights to improve the content and delivery of courses. By closely monitoring and analyzing these metrics, the team can tailor the course offerings to meet the users' needs and preferences, ensuring a beneficial learning experience.

## Data Tables:

**Table: CourseDetails**

| Feature Name | Brief Feature Description        | Feature Data Type | Comments   |
|--------------|----------------------------------|-------------------|------------|
| course_id    | Unique Identifier for a course   | INT               | Primary Key|
| course_name  | Name of the course               | VARCHAR(255)      |            |
| category     | Category of the course           | ENUM              | a. Options: Business, Technology, Creative Skills |
| level        | Difficulty level of the course   | ENUM              | a. Options: Beginner, Intermediate, Advanced   |
| duration     | Duration of the course in hours  | FLOAT             |            |
| release_date | The date the course was released | DATE              |            |

**Table: UserEngagement**

| Feature Name | Brief Feature Description          | Feature Data Type | Comments                       |
|--------------|------------------------------------|-------------------|--------------------------------|
| engagement_id| Unique Identifier for an engagement| INT               | Primary Key                    |
| course_id    | Identifier for a course            | INT               | Foreign Key, references CourseDetails(course_id) |
| user_id      | Identifier for a user              | INT               |                                |
| completion_rate | Percentage of course completed  | FLOAT             |                                |
| feedback_score  | User feedback score out of 10   | FLOAT             |                                |
| engagement_date | Date of engagement              | DATE              |                                |

## SQL Questions:

#### Question 1:
- **Topics and Operations**: Aggregation, JOIN
- **Scenario**: The team wants to understand the overall engagement and feedback for each category of courses offered.
- **Task**: Write a SQL query to calculate the average completion rate and average feedback score for each category of courses. Order the result by average feedback score in descending order.

#### Question 2:
- **Topics and Operations**: Common Table Expression (CTE), Sub-query
- **Scenario**: Upon reviewing the initial data, the team is interested in identifying courses that are below the average completion rate within their respective categories, to focus on their improvement.
- **Task**: Write a SQL query to identify the courses that have a below-average completion rate within their respective categories. Provide the course name, category, and the difference between the course’s completion rate and the average completion rate of its category.

#### Question 3:
- **Topics and Operations**: Window Functions, Ranking
- **Scenario**: The team also wants to know the top 3 courses in each category based on user feedback to highlight them on the platform.
- **Task**: Write a SQL query to retrieve the top 3 courses in each category based on the average feedback score. Provide the course name, category, and average feedback score.
