# Business Problem Statement:

**Event Recommendation & Calendar Integration for Enhanced User Experience**

Facebook's event platform aims to provide users with personalized event recommendations, ensuring that event organizers reach potential attendees effectively. With millions of events and an even greater number of users, how can Facebook leverage its vast datasets to drive both user engagement and organizer satisfaction?

---
## Data Tables:


| **Table Name** | **Column Name**  | **Description**                                 | **Feature Type**  |
|----------------|------------------|-------------------------------------------------|-------------------|
| `events`       | `event_id`       | Unique ID for each event                        | Numeric           |
|                | `organizer_id`   | ID of the event organizer                       | Numeric           |
|                | `event_type`     | Type of event (music, seminar, festival, etc.)  | Categorical       |
|                | `event_date`     | Date of the event                               | Date              |
|                | `attendees_count`| Number of attendees registered                  | Numeric           |
| `users`        | `user_id`        | Unique ID for each user                         | Numeric           |
|                | `joined_date`    | Date when user joined Facebook                  | Date              |
|                | `location`       | User's location                                 | Categorical       |
|                | `interests`      | List of user's interests                        | Text (List)       |
| `interactions` | `user_id`        | Unique ID for each user                         | Numeric           |
|                | `event_id`       | Unique ID for each event                        | Numeric           |
|                | `interaction_type` | User's interaction with event (view, click, attend)| Categorical  |

---

## Questions:

1. **SQL/Data Manipulation**:
   
   Given the recent launch of a new "Lantern Festival", event organizers are keen to understand user interaction.
   
   *a.* From the `events` and `interactions` tables, extract a list of users who viewed festival events but didn't attend.
   
   *b.* For the users identified in *a*, leverage the `users` table to pull their location and interests.


2. **Machine Learning & Modeling**:

   Event organizers would like to predict the potential success of their upcoming events.

   *a.* Utilizing the `events` and `interactions` tables, design a model to predict the attendees count of an event based on the event_type, past events’ attendees count, and user interactions. Describe the steps, features, and the model you would consider.

   *b.* Discuss the bias-variance trade-off for the model proposed in *a*.


3. **Product Design & Analytics**:

   Facebook is thinking of introducing an "Event Calendar" feature where users can plan their events ahead.

   *a.* How would you measure the success of this feature once implemented?
   
   *b.* Hypothetically, after launching the "Event Calendar", there was a 10% decrease in the number of users attending events. How would you investigate this and what potential reasons might explain this?

