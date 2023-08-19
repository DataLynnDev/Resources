# Business Problem Statement:

"Facebook's event platform is continuously growing, and with the integration of various calendars and recommendation systems, the company's main objective is to enhance user engagement with events. The platform is striving to provide users with the most relevant event recommendations while helping event organizers extend their reach. There is also an aim to seamlessly integrate these events into users' calendars, ensuring that users never miss out on events they're interested in. To achieve these goals, our team needs a proficient data scientist who can analyze our data and make insightful recommendations."



## Data Table:

| Column Name | Description                                      | Feature Type      |
|-------------|--------------------------------------------------|-------------------|
| user_id     | Unique identifier for a user                     | Categorical       |
| event_id    | Unique identifier for an event                   | Categorical       |
| event_type  | Category of the event (e.g., Concert, Workshop)  | Categorical       |
| event_date  | Date of the event                                | Date              |
| rsvp_status | Whether the user has RSVP'd to the event         | Categorical       |
| friends_attending | Number of user's friends attending the event | Numerical         |
| calendar_integration | If the event is integrated into the user's calendar | Boolean    |
| event_organizer_id | Unique ID for the event organizer           | Categorical       |
| event_popularity | Number of total RSVPs for the event          | Numerical         |
| user_activity | Number of events user has RSVP'd to in the past month | Numerical  |



## Questions:

1.
   **Question:** Imagine that you noticed some irregularities in the `rsvp_status` column where certain `event_id` have an unusually high number of RSVPs in comparison to others. How would you investigate the authenticity of these high RSVP numbers and ensure they are not spam or system-generated anomalies?



2.
   **Question:** Using the data, can you design a recommendation strategy where if a user's friends are attending an event (`friends_attending` > 3), that event gets recommended to the user, especially if it's not integrated into their calendar (`calendar_integration` = False)? Please implement this using SQL.


3.
   **Question:** Event organizers claim that concerts (`event_type` = Concert) tend to have more popularity (`event_popularity` > 1000) than workshops. Using statistical methods, how would you validate or refute this claim?



4.
   **Question:** Event organizers have recently requested that events which are already in a user's calendar (`calendar_integration` = True) should have a higher priority in the recommendation list. Using the data available, design an experiment to determine if prioritizing these events indeed increases overall user engagement with the platform.

