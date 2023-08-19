# Business Problem Statement
At Meta, maintaining the authenticity and security of user accounts on Facebook is a top priority. Data science plays a pivotal role in safeguarding the platform against fraud and malicious activities. The key challenge is to effectively detect fake accounts, identify compromised accounts, and minimize harmful actions on the platform, while ensuring genuine user experiences are not affected.



## Data Tables

**Table: `user_activity_log`**

| Column Name         | Description                                           | Feature Type      |
|---------------------|-------------------------------------------------------|-------------------|
| user_id             | Unique identifier for a user                          | Numeric           |
| timestamp           | Date and time of the activity                         | DateTime          |
| activity_detail     | Detail of activity (like, share, comment, etc.)       | Categorical       |
| device_id           | Identifier for the device used for the activity       | Numeric           |
| ip_address          | IP address from where the activity was initiated      | String            |

**Table: `account_metadata`**

| Column Name         | Description                                           | Feature Type      |
|---------------------|-------------------------------------------------------|-------------------|
| user_id             | Unique identifier for a user                          | Numeric           |
| account_creation_date | Date when the account was created                    | Date              |
| friend_count        | Number of friends the user has                        | Numeric           |
| reported_count      | Number of times the user has been reported            | Numeric           |
| profile_picture     | If the user has a profile picture or not (1 or 0)     | Binary            |



## Questions

1. **Scenario**: Your team has observed a surge in reports against newer accounts for suspected fraudulent activity. You suspect that these might be bots or fake accounts.

 **Question**: Using the `account_metadata` and `user_activity_log` tables, identify accounts created in the last 30 days that have a high frequency of activities but fewer friends and no profile picture.

2. **Scenario**: There's been an uptick in reported activities stemming from specific IP addresses.

 **Question**: Using the `user_activity_log`, can you identify any patterns or anomalies related to the frequency or type of activities from these IP addresses over the last 7 days? What insights can you draw about the possibility of these being compromised accounts versus bots?

3. **Scenario**: You want to implement a feature that flags suspicious user activities for review.

 **Question**: Based on the data from both tables, how would you design an early-warning system that identifies potential fraudulent or malicious actions on the platform? What metrics would you use to measure its effectiveness and false positive rate?

4. **Scenario**: Recent feedback suggests that legitimate accounts are sometimes getting flagged and their activities limited, affecting user experience.

 **Question**: Using the data, how would you optimize the current detection mechanisms to minimize false positives, ensuring that genuine users are not adversely affected? What additional data might be helpful to further refine this mechanism?
