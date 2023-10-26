# Business Problem Statement:
In the Gmail Storage Optimization team, we constantly strive to ensure our users have a seamless email experience without having to worry about storage issues. With an increasing number of users running out of their allocated storage, it is imperative to study and analyze storage patterns. As a data analyst, your role is to identify common types of data bloat such as large attachments, frequent email senders, or patterns of storage use over time. Your analyses will help in suggesting features or prompts to users to manage their space better and predicting future storage issues.

## Data Tables:

**Table: Emails**

| Feature Name | Feature Description              | Data Type | Comments                                           |
|--------------|----------------------------------|----------|----------------------------------------------------|
| email_id     | Unique identifier for each email | int      | Primary Key                                        |
| sender_id    | ID of the sender                 | int      |                                                    |
| receiver_id  | ID of the recipient              | int      |                                                    |
| sent_date    | Date when the email was sent     | date     |                                                    |
| attachment_size | Size of the email attachment  | float    | Value in MB. 0.0 if no attachment.                 |
| content_size   | Size of the email content      | float    | Value in MB.                                        |

**Table: Users**

| Feature Name  | Feature Description                 | Data Type  | Comments                                         |
|---------------|-------------------------------------|-----------|--------------------------------------------------|
| user_id       | Unique identifier for each user     | int       | Primary Key                                      |
| email_address | Email address of the user           | varchar   |                                                  |
| total_storage | Total storage allocated to the user | float     | Value in GB                                      |
| used_storage  | Storage used by the user so far     | float     | Value in GB                                      |

## Questions:

1. **Topics and Operations:** Swap, Update  
   **Scenario:** The Gmail team realized that there was an error in calculating the 'used_storage' for users. For a subset of users, the 'total_storage' and 'used_storage' columns were swapped due to a system error.   
   **Task:** Write an SQL statement to swap the values of 'total_storage' and 'used_storage' for users where 'used_storage' is greater than 'total_storage'.

2. **Topics and Operations:** COUNT, DATE Functions, JOIN  
   **Scenario:** There's a suspicion that some users might be running out of storage because they receive emails with very large attachments.   
   **Task:** Report the top 5 users (based on email_address) who have received the maximum number of emails with attachments larger than 10MB in the last 30 days.

3. **Topics and Operations:** SUM, JOIN, Group By, Having  
   **Scenario:** Gmail wants to roll out a new feature to notify users when they are close to using up their storage. Before that, it's important to identify users who are at risk.  
   **Task:** Find all users whose total emails' content and attachment size combined in the last 6 months constitute more than 80% of their total_storage. List their email_address and the combined size of their emails. (limit the output to 5 rows)