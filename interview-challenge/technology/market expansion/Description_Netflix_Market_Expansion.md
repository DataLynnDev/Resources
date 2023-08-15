# Business Problem Statement:

Netflix is in a phase of strategic expansion into new markets. While the company's streaming service is widely recognized globally, its footprint in certain regions remains small. As part of the Market Analysis & Expansion team, you'll be working to determine the feasibility and strategy for entering these new markets, considering regional demographics, content preferences, and local competition. Your role as a data scientist is to decipher which regions are most attractive for Netflix's expansion, and what kind of content might resonate best within those regions based on available data.


## Data Tables:

1. **Table 1: UserActivity**

| Column Name | Description                        | Data Type  |
|-------------|------------------------------------|------------|
| UserID      | Unique identifier for each user    | INT        |
| Region      | Geographical area of the user      | STRING     |
| GenreWatched| Type of content viewed by the user | STRING     |


2. **Table 2: RegionInfo**

| Column Name    | Description                                      | Data Type  |
|----------------|--------------------------------------------------|------------|
| Region         | Name of the region                               | STRING     |
| Population     | Total population of the region                   | INT        |
| MedianIncome   | Average income of people in that region          | FLOAT      |
| PrCompetitoresence | Presence of a competitive streaming service (1 for Yes, 0 for No) | INT |

3. **Table 3: UserInfo**

| Column Name      | Description                                               | Data Type  |
|------------------|-----------------------------------------------------------|------------|
| UserID           | Unique identifier for each user                           | INT        |
| Region           | Geographical area of the user (e.g., North America, Asia) | STRING     |
| ComedyHours      | Hours spent watching comedy genre                         | FLOAT      |
| DramaHours       | Hours spent watching drama genre                          | FLOAT      |
| ActionHours      | Hours spent watching action genre                         | FLOAT      |
| SciFiHours       | Hours spent watching sci-fi genre                         | FLOAT      |
| DocumentaryHours | Hours spent watching documentary genre                    | FLOAT      |
| HorrorHours      | Hours spent watching horror genre                         | FLOAT      |
| RomanceHours     | Hours spent watching romance genre                        | FLOAT      |
| LastActive       | Last date the user was active                             | DATE       |


## Questions:

1. Considering the UserActivity table, in which regions have users not been active for over 30 days? From these regions, based on the RegionInfo table, which have a significant competitor presence? This will help us identify areas where our market might be getting overshadowed by competitors.


2. Given the demographics and regional preferences, which genres in the UserActivity table are most popular in regions with a median income above a certain threshold (e.g., $50,000) in the RegionInfo table? This will guide our content acquisition and creation teams to produce or buy content that resonates with affluent audiences in potential new markets.


3. Netflix is considering introducing a new feature that will cater to regional preferences based on demographics. Based on the UserActivity and RegionInfo tables, design an A/B test to see if introducing localized content based on region and median income increases user engagement. What metrics would you use to measure success or failure? How would you ensure the regions chosen for the test are not biased by competitor presence?

4. Netflix is looking to expand new markets. Your manager asked you to proposed an expansion stratety. Specifically, your report should include the analysis for the following questions:

- Identify the regions where the average user has the highest hours of total viewing time. Would these regions represent a higher opportunity for expansion? What other factors should be considered?  
- How does the user activity in the regions where competitors have a strong presence? (number of users, viewing hours, etc.) Is it the same with regions where competitors have less presence? Does this signal a potential risk for Netflix's expansion in these regions?  
- Based on your findings from the opportunity and risk analysis, recommend a list of regions where Netflix should prioritize expansion. Justify your choices using data insights.
