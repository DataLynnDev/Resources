# Business Problem Statement:
With the proliferation of genres and authors on Amazon's Kindle platform, it is becoming increasingly important to understand the readers' preferences to optimize the user experience and sales strategies. The business problem for the data analyst is: **"Determine which genres and authors are most popular among Kindle users over the past year, and identify patterns in reading habits to improve the user interface and suggest promotions."**

## Data Tables:

**Table 1: BooksRead**

| Column Name | Description                               | Feature Type |
|-------------|-------------------------------------------|--------------|
| user_id     | Unique identifier for the user            | Nominal     |
| book_id     | Unique identifier for the book            | Nominal     |
| genre       | Genre of the book (e.g. Fiction, Romance) | Nominal     |
| author      | Author of the book                        | Nominal     |
| read_date   | Date the user finished the book           | Date        |

**Table 2: UserActivity**

| Column Name  | Description                                   | Feature Type |
|--------------|-----------------------------------------------|--------------|
| user_id      | Unique identifier for the user                | Nominal     |
| activity     | Type of activity (e.g. page_turn, bookmark)   | Nominal     |
| timestamp    | Timestamp of the activity                     | Date-time   |

## Questions

**1. Data Cleaning & Exploration Question:**

**Scenario:** Upon receiving the latest datasets, you noticed that some records in the `BooksRead` table have missing genres and authors, and the `read_date` has inconsistent formats.

**Question:** Using the `BooksRead` table, how would you address the missing genres and authors, and ensure the `read_date` is in a consistent format?

**2. SQL Queries Question:**

**Scenario:** The Kindle team wants to analyze the frequency of activities for each user on a given book.

**Question:** Using the `BooksRead` and `UserActivity` tables, write a SQL query that joins both tables on `user_id`, and retrieves the total count of each activity for each user and book. Rank the users based on the total activities they've done for each book. Only show the records with rank 1 (including ties).

**3. Probability and Statistical Analysis Question:**

**Scenario:** In an effort to gamify the Kindle reading experience, you're tasked with implementing a feature that rewards users based on their reading consistency.

**Question:** Given the `UserActivity` table, if a user turns a page every minute on average, what is the probability they will turn at least 50 pages in an hour? Use appropriate equations to calculate the probability and then code to simulate this event over 1000 trials.

**4. Product & Business Sense Question:**

**Scenario:** Recently, Kindle introduced a recommendation system, and stakeholders are keen to see its impact.

**Question:** Using data from the `BooksRead` table, how would you determine if users are reading more books from the genres recommended to them compared to before the introduction of the recommendation system? Provide a strategy and the types of analyses you would perform.
