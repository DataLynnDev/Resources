# **Business Problem Statement:**
Instagram's Content Moderation Analytics team at Meta is responsible for ensuring user-generated content aligns with the platform's guidelines. Given the enormous volume of content shared every day, the team relies heavily on automated systems backed by machine learning models to filter out inappropriate content. However, these automated systems might sometimes flag benign content as inappropriate (false positives) or miss actual inappropriate content (false negatives). To ensure the reliability and accuracy of these systems, the team requires a data analyst who can measure and track the system's performance. The analysis will serve as feedback for the system to refine and recalibrate its models, thus improving its accuracy over time.

## **Data Tables:**

**1. ModerationLog**

| Feature Name     | Feature Description                                         | Data Type | Comments       |
|------------------|-------------------------------------------------------------|-----------|----------------|
| log_id           | Unique identifier for each log entry                        | int       | Primary Key    |
| content_id       | Identifier for the content being evaluated                  | int       |                |
| flagged_date     | The date the content was flagged by the automated system    | date      |                |
| review_date      | The date the content was reviewed by a human moderator      | date      |                |
| system_decision  | The decision by the automated system (flag or no flag)      | enum      | Options: "Flag", "No Flag" |
| moderator_decision| The decision by the human reviewer (inappropriate or not)   | enum      | Options: "Inappropriate", "Appropriate" |

**2. ContentDetails**

| Feature Name     | Feature Description                                         | Data Type | Comments       |
|------------------|-------------------------------------------------------------|-----------|----------------|
| content_id       | Unique identifier for each piece of content                 | int       | Primary Key    |
| user_id          | Identifier for the user who posted the content              | int       |                |
| post_date        | The date the content was posted                             | date      |                |
| content_type     | Type of the content (e.g., image, video, story)             | enum      | Options: "Image", "Video", "Story" |
| content_duration | Duration of content visibility (relevant for stories)       | int       | In hours; Default for non-stories is NULL |

## Questions

**Question 1:**  
**Topics and Operations:** Cumulative Operations

**Scenario:** The team wants to understand the trend of flagged content by the automated system over a period.

**Task:** For each day, compute the cumulative count of content flagged by the automated system up to and including that day. (You can use LIMIT to limit the output to up to 10 rows.)

**Question 2:**  
**Topics and Operations:** Grouping and Filtering

**Scenario:** It is essential to measure the accuracy of the automated system by comparing its decisions against those of human moderators.  

**Task:** For each content type (e.g., image, video, story), identify the number of false positives where the system flagged the content as inappropriate, but the human moderator deemed it appropriate. Also, identify the number of false negatives where the system didn't flag content, but the moderator deemed it inappropriate.  

**Question 3:**  
**Topics and Operations:** Joining Tables  

**Scenario:** The visibility duration of content might play a role in the accuracy of the automated moderation system. Specifically, stories that are visible for a shorter period might be at a higher risk of being misjudged by the system since they are temporary.  

**Task:** Join the `ModerationLog` and `ContentDetails` tables on the `content_id`. For content flagged by the system, compute the average content_duration for each content type. Also, compute the percentage of flagged content that is of type "Story" and has a content_duration less than 24 hours.