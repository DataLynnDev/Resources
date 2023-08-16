# **Business Problem Statement:**

Amazon Kindle wants to enhance its user experience by better understanding reading habits and preferences. The goal is to improve book recommendations, forecast demand for upcoming releases, and provide insights to publishers about readers' behavior. As an experienced data scientist, you are presented with the challenge of extracting actionable insights from vast amounts of reading data.

## **Data Tables**:

1. **Table Name**: `User_Books`

| Column Name | Description                   | Feature Type |
| ----------- | ----------------------------- | ------------ |
| user_id     | Unique ID of the user         | Categorical  |
| book_id     | Unique ID of the book         | Categorical  |
| read_date   | Date the book was read        | Datetime     |
| rating_date | Date the book was rated       | Datetime     |
| rating      | Rating given by user (1 to 5) | Ordinal      |
| pages_read  | Number of pages read by user  | Continuous   |

2. **Table Name**: `Book_Info`

| Column Name   | Description                               | Feature Type   |
|---------------|-------------------------------------------|----------------|
| book_id       | Unique identifier for each book           | Categorical    |
| title         | Book title                                | Text           |
| genre         | Genre of the book                         | Categorical    |
| publication_date | Publication date of the book             | DateTime       |
| publisher_id  | Unique identifier for the book publisher  | Categorical    |

3. **Table Name**: `User_Demographics`

| Column Name | Description                                         | Feature Type   |
|-------------|-----------------------------------------------------|----------------|
| user_id     | Unique identifier for each user                     | Categorical    |
| age_group   | Age group of the user (e.g., 18-24, 25-34, etc.)    | Categorical    |
| country     | Country of the user                                 | Categorical    |

## **Questions**:

1. Given the `User_Books` table, can you identify patterns in readership over time? Visualize the monthly number of books read over the past year. Additionally, qualify how much demand is expected in the upcoming months.


2. Using the `User_Demographics` and `User_Books` tables, determine if certain age groups prefer certain genres. Provide a statistical measure to support your findings.


3. A publisher wants to launch a new book in the "Fantasy" genre. By utilizing the `Book_Info` and `User_Books` tables, predict the potential success (i.e., number of readers and ratings) of the book in the next 6 months. Furthermore, based on previous reading patterns, suggest the best time to release the book.


4. Users tend to rate books within hours of completing them. However, a discrepancy has been noticed where some users rate books days or weeks after completing them. Identify these anomalies from the `User_Books` table and provide an insight into potential causes.



