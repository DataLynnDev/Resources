# **Business Problem Statement**:
In order to enhance the user experience and job match efficiency on LinkedIn, it's crucial to analyze the interactions and engagements occurring on user profiles. This includes understanding the frequency and nature of profile views, connections, endorsements, and the categorization of skills which could potentially lead to better job matching and networking opportunities. As a data analyst at LinkedIn's Profile team, delving into the available data to derive insights and facilitate feature optimization is a key responsibility.

## **Data Tables**:

**Table 1: UserProfile**

| Feature Name  | Brief Feature Description          | Feature Data Type | Comments   |
|---------------|------------------------------------|-------------------|------------|
| profile_id    | Unique identifier for profiles     | int               | Primary Key|
| user_id       | Unique identifier for users        | int               |            |
| education     | User's education background        | varchar(255)      |            |
| work_experience| User's work experience            | varchar(255)      |            |
| skills        | Skills endorsed by others          | varchar(255)      |            |
| connections   | Number of connections              | int               |            |
| endorsements  | Number of endorsements             | int               |            |
| recommendations| Number of recommendations         | int               |            |
| views         | Number of profile views            | int               |            |
| last_updated  | Last updated date of the profile   | date              |            |

**Table 2: JobMatch**

| Feature Name  | Brief Feature Description       | Feature Data Type | Comments              |
|---------------|---------------------------------|-------------------|-----------------------|
| job_id        | Unique identifier for job posts | int               | Primary Key           |
| profile_id    | Profile ID of the user          | int               | Foreign Key           |
| job_title     | Title of the job post           | varchar(255)      |                       |
| skills_required| Skills required for the job     | varchar(255)      |                       |
| match_score   | Score based on skill match      | decimal(5,2)      |                       |
| applied       | If the user has applied or not  | enum              | Values: Yes, No       |

## **SQL Questions**:

**Question 1**

**Topics and Operations:**
* Selecting
* Comparing values within a column

**Scenario:**
The LinkedIn Profile team is interested in understanding the correlation between the number of connections and profile views. This understanding could potentially help in optimizing profile visibility features.

**Task:**
Write an SQL query to find out all the profile_ids where the number of connections is above the average number of connections.

**Question 2**

**Topics and Operations:**
* Joining tables
* Aggregation

**Scenario:**
Given the ongoing initiative to enhance job match efficiency, there is a need to analyze how well the skills of individuals are matching with the job opportunities available.

**Task:**
Write an SQL query to find the average match score for each profile_id from the JobMatch table, and display the result along with the corresponding skills from the UserProfile table.

**Question 3**

**Topics and Operations:**
* Sub-query
* Grouping and Ordering

**Scenario:**
The team wants to analyze the effectiveness of endorsements in improving job match scores. By identifying the top profiles with higher match scores, an analysis can be conducted to understand the role of endorsements.

**Task:**
Write an SQL query calculates the rank of each row based on the average match score in descending order. And display the result along with the total number of endorsements from the UserProfile table.