
# Business Problem Statement

As Netflix moves into a new paradigm with the introduction of an ad-supported plan, the overarching objective is to ensure that this model not only maintains but ideally enhances the user experience, whilst strategically maximizing ad revenue without impinging on content engagement. There is also a goal to use this new model as a lever to either upsell users to premium plans or retain them longer by offering an optimized experience.


## Data Tables

1. **Table Name: UserInteractions**

| Column Name    | Description                                       |
|----------------|---------------------------------------------------|
| account_id     | Unique identifier for a Netflix user account      |
| device_id      | Unique identifier for the device used             |
| login_date     | Date of login                                     |
| content_id     | Unique identifier for the content played          |
| ad_shown       | Boolean: if an ad was shown before/during content |
| ad_category    | Category of the advertisement shown               |
| watch_duration | Duration for which content was watched            |
| ad_clicked     | Boolean: if the ad was clicked                    |
| content_locked | Boolean: if the user interact with locked content |

2. **Table Name: ContentDetails**

| Column Name    | Description                                      |
|----------------|--------------------------------------------------|
| content_id     | Unique identifier for the content played         |
| title          | Name of the TV show or movie                     |
| genre          | Genre of the content (e.g., Action, Drama, etc.) |
| release_date   | Release date of the content                      |
| is_locked      | Boolean: if the content is locked due to licensing |


## Questions

1. Netflix is considering adjusting its advertising strategy. By utilizing the `UserInteractions` table, evaluate the relationship between the genre of the content being watched and the ad category that gets clicked the most. Could this relationship inform a targeted ad-placement strategy based on user preferences?


2. It's been noticed that some users engage less with ad-supported content. Using both `UserInteractions` and `ContentDetails` tables, derive insights into whether certain genres are more affected by ads than others. This might inform decisions on content acquisition or licensing in the future.


3. With a goal to upsell users to an ad-free plan, we need insights into patterns that might indicate a user's readiness to upgrade. By analyzing the `UserInteractions` table, can you pinpoint behavioral triggers (like frequency of interactions with locked content or frequency of ad interactions) that might suggest this readiness?


4. To optimize the viewer's experience and ad engagement, Netflix plans to conduct an A/B/C test concerning ad placement. Three user groups will be exposed to either pre-roll, mid-roll, or post-roll ads. Design the test and give your analysis and decisions.

