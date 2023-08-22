# **Business Problem Statement:**

At Meta, particularly in the Groups & Community Building team for Facebook, we recognize that groups play a pivotal role in user engagement and content discovery. With the increasing importance of Facebook groups, we aim to harness data science to enhance group recommendations, facilitate content moderation, and unravel the intricacies of group dynamics. The overarching objective is to create a more personalized, engaging, and safe space for our users. We're seeking a data scientist who can assist in these endeavors.

## **Data Tables Description:**

**1. Table: GroupActivity**

| **Column Name** | **Description** | **Feature Type** |
|------|-------|-------|
| `user_id` | Unique identifier for users | Integer |
| `group_id` | Unique identifier for groups | Integer |
| `activity_date` | The date of the activity | Date |
| `interaction_type` | Type of interaction (e.g., post, comment, like) | String |
| `content` | Text content of the post or comment | String |


**2. Table: GroupInfo** 

| **Column Name** | **Description** | **Feature Type** |
|------|-------|-------|
| `group_id` | Unique identifier for groups | Integer |
| `group_creation_date` | The date the group was created | Date |
| `group_category` | Category of the group (e.g., Music, Fitness) | String |
| `active_members` | Number of active members in the group | Integer |


## **Questions:**

1. **Question:** Facebook aims to increase user engagement through group suggestions. Given the `GroupActivity` table, how would you develop an algorithm or model to recommend groups to users based on their interaction types and content they engage with? What features would be essential for this task?


2. **Question:** Facebook aims to study group dynamics over time. Utilizing the `GroupInfo` and `GroupActivity` tables, assess the relationship between the `group_category` and the average number of interactions over months. How would this data assist in shaping Facebook's group promotion strategies?


3. **Question:** After assessing the group dynamics, a curious observation surfaces: certain categories have groups that are very active even if they were created recently, while some older groups witness dwindling activity. Using the `GroupInfo` and `GroupActivity` tables, delve into this observation. Highlight patterns and suggest potential product changes to revitalize older groups.