# Business Problem Statement:
Google has observed that certain search results are not yielding user engagement as expected, leading to user dissatisfaction. Therefore, there's a pressing need to analyze search results and user behavior to refine Google's search algorithms. We want to identify problematic search queries and fine-tune our algorithms to enhance user experience.

## Data Tables:

**Table: UserSearches**

| Feature Name | Feature Description                  | Data Type | Comments                           |
|--------------|--------------------------------------|-----------|------------------------------------|
| search_id    | Unique ID of the search              | int       | Primary Key                        |
| user_id      | ID of the user conducting the search | int       |                                    |
| query        | Search query entered by the user     | varchar   |                                    |
| timestamp    | Time of the search                   | datetime  |                                    |

**Table: ClickEvents**

| Feature Name | Feature Description                                | Data Type | Comments                       |
|--------------|----------------------------------------------------|-----------|--------------------------------|
| event_id     | Unique ID of the click event                       | int       | Primary Key                    |
| search_id    | ID of the search which led to this click           | int       | Foreign Key (UserSearches)     |
| link_position| Position of the link on the search results page    | int       |                                |
| time_spent   | Time the user spent on the resultant page (seconds)| int       |                                |
| return_flag  | Did user return to search results?                 | enum      | Options: YES, NO               |


## Interview Questions:

**Question 1**
*Topics and Operations:* Filtering, Grouping, Aggregation
*Scenario:* We want to find out which search queries have the least user engagement to identify potentially problematic search algorithms.
*Task:* List the top 5 search queries where users most frequently return to the search results without clicking on any link.

**Question 2**
*Topics and Operations:* JOIN, Filtering, Aggregation, Sorting
*Scenario:* Understanding user behavior after conducting a search is crucial. This will help in determining if the search results were relevant to the users or not.
*Task:* Find the average time users spend on pages for each search query. Also, list the search queries where users, on average, spend less than 10 seconds on the resultant pages.

**Question 3**
*Topics and Operations:* JOIN, Filtering, Window Functions
*Scenario:* It's critical to understand if the position of a link in search results affects user behavior. A higher click-through rate for top links might indicate the search algorithm's accuracy.
*Task:* For each search query, determine the link position that gets the most clicks.
