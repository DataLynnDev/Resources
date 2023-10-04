# **Business Problem Statement:**

With the surge of content on Instagram, especially in Stories and Reels, Meta aims to ensure that user engagement is optimized. For this, the Stories and Reels Performance team is looking to understand:
1. The overall popularity and traction these features are getting.
2. Patterns of user interactions, and
3. Ways to further enhance user experience and content visibility.

## **Data Tables:**

**Table: StoryReelData**

| Feature Name  | Description                   | Data Type   | Comments                     |
|---------------|-------------------------------|-------------|------------------------------|
| user_id       | User's Unique Identifier      | int         | Primary Key                  |
| content_id    | Unique Identifier for content | int         |                              |
| content_type  | Type of the content            | enum        | Options: 'Story', 'Reel'     |
| post_date     | Date of posting               | date        |                              |
| view_count    | Number of views               | int         |                              |
| like_count    | Number of likes               | int         |                              |
| share_count   | Number of shares              | int         |                              |
| comment_count | Number of comments            | int         |                              |

## **Questions:**

**1. Topics & Operations:** Select, Group by, Aggregate functions (from "Reported Posts")
   
**Scenario:** The marketing team wants to understand the popularity of content types in the past month (Latest Day of post_date: 2023-10-02).

**Task:** Write an SQL statement to fetch the total views, likes, shares, and comments for each content type ('Story' and 'Reel') for the past month. Order the results by total views in descending order.


**2. Topics & Operations:** Rank, Group by, Order by, common table expressions (CTE)

**Scenario:** Discover which content type ('Story' or 'Reel') has garnered maximum user engagement within the top users over the past week, by analyzing likes and shares. This will aid in discerning influencer patterns and their impact across content types.

**Task:**
Find the top 3 users and associated content_types which have obtained the highest combined (likes + shares) within the past week, considering the summation of likes and shares across all contents of the same type by a user as a single entity.



**3. Topics & Operations:** Window Functions, Date Differences, Conditional Logic, Aggregation

**Scenario:** The team has observed that users who post consistently tend to generate more engagement. Instead of just looking for streaks, the team is now interested in understanding the average duration between postings for  top 5 users over the past six months.

**Task:** Using the StoryReelData table, calculate the average duration (in days) between the first and last post for top 5 users in the past six months. Provide results sorted by user_id.
