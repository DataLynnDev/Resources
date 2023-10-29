# Business Problem Statement:
The objective is to analyze the App Store’s user engagement and its impact on the app download trends. Our goal is to optimize the recommendation algorithms to boost the download rates of high-quality apps while understanding the correlation between user reviews, search behaviors, and app downloads. By leveraging the data, we aim to refine search functionality and promotional strategies to enhance user satisfaction and drive more organic traffic to deserving apps.

## Data Tables:

Table 1: `AppDetails`

| Feature Name | Brief Feature Description         | Feature Data Type | Comments |
|--------------|-----------------------------------|-------------------|----------|
| app_id       | Unique identifier for each app    | INT               | PK       |
| app_name     | Name of the app                   | VARCHAR(255)      |          |
| category     | Category of the app               | ENUM              | Options: (Games, Productivity, Social Networking, Health & Fitness, Education) |
| download_count | Number of times app has been downloaded | INT       |          |
| rating       | Average user rating out of 5      | DECIMAL(2,1)      |          |
| price        | Price of the app (USD)            | DECIMAL(5,2)      |          |

Table 2: `UserReviews`

| Feature Name | Brief Feature Description         | Feature Data Type | Comments |
|--------------|-----------------------------------|-------------------|----------|
| review_id    | Unique identifier for each review | INT               | PK       |
| app_id       | App being reviewed                | INT               | FK       |
| user_id      | Identifier for the reviewing user | INT               |          |
| review_text  | Text of the review                | TEXT              |          |
| review_rating| Rating given by the user (out of 5)| DECIMAL(2,1)     |          |
| review_date  | Date the review was made          | DATE              |          |

## Questions

## SQL Questions:

1. **Topics and Operations**: Join Operations
   - **Scenario**: We want to know the top 5 most downloaded apps in the "Games" category and their average user review ratings.
   - **Task**: Write an SQL query to find the names and download counts of the top 5 most downloaded apps in the "Games" category along with the average user review rating for each of these apps. Order the result based on download count in descending order.

2. **Topics and Operations**: Subqueries, Aggregate Functions
   - **Scenario**: We are interested in understanding the impact of user reviews on app downloads. Particularly, we want to know if apps with higher average ratings also have higher download counts.
   - **Task**: Write an SQL query to find the average user review rating and the download count for each app, only includes the top 5 results. Include apps with at least 10 reviews.

3. **Topics and Operations**: Conditional Logic
   - **Scenario**: We want to evaluate the price sensitivity among app categories. Particularly, we are interested in finding out the average download count for free vs paid apps in each category.
   - **Task**: Write an SQL query to find the average download count for free apps and paid apps within each app category. Display the result with category name, average download count for free apps, and average download count for paid apps.
