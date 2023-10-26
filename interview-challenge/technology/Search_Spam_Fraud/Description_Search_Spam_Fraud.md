# **Business Problem Statement**:
*Gmail's Spam & Fraud Detection team has been working tirelessly to provide users with a top-notch experience by filtering out spam and fraudulent emails. However, with evolving tactics from spammers and fraudsters, the team needs to continuously assess and refine the spam detection algorithms. To support this, the team is seeking an experienced data analyst who can help analyze the effectiveness of current filters, detect patterns in false positives/negatives, and provide insights on potential improvements. This assessment is designed to test the candidate's ability to derive insights from data related to spam detection using SQL.*

## **Data Tables**:

**Table: Emails**

| Feature Name  | Feature Description                                      | Data Type     | Comments                             |
|---------------|----------------------------------------------------------|---------------|--------------------------------------|
| email_id      | Unique identifier for each email                        | int           | Primary Key                          |
| sender_id     | Unique identifier for the sender of the email            | int           |                                      |
| recipient_id  | Unique identifier for the recipient of the email        | int           |                                      |
| timestamp     | The time when the email was sent                        | datetime      |                                      |
| is_spam       | Whether the email was marked as spam (1) or not (0)     | enum          | Options: 1, 0                       |
| content       | Content of the email                                    | text          |                                      |
| subject       | Subject of the email                                    | varchar(255)  |                                      |


**Table: Feedback**

| Feature Name  | Feature Description                            | Data Type | Comments                             |
|---------------|------------------------------------------------|-----------|--------------------------------------|
| feedback_id   | Unique identifier for each feedback submission | int       | Primary Key                          |
| email_id      | Refers to the email being commented on         | int       | Foreign Key (references Emails)      |
| feedback_type | Type of feedback (false positive/negative)     | enum      | Options: "false_positive", "false_negative" |

## Questions:

**Question 1**:

**Topics and Operations**:
- COUNT
- JOIN
- GROUP BY
- Filtering with WHERE

**Scenario**:
As Gmail continues to improve its spam filters, understanding the false positive rates is crucial. False positives refer to legitimate emails that are mistakenly classified as spam. Analyzing the number of false positives per sender could provide valuable insights into any potential patterns or frequent senders being flagged incorrectly.

**Task**:
Find the top 5 senders with the highest number of false positive emails.

**Question 2**:

**Topics and Operations**:
- JOIN
- Date functions (extracting day)
- Conditional statements (CASE)

**Scenario**:
The Spam & Fraud Detection team wants to know if there is any specific day of the week when the false positives are most frequent. This could help in narrowing down any potential issues or understanding if external factors are influencing the results on certain days.

**Task**:
Calculate the number of false positive feedbacks for each day of the week.

**Question 3**:

**Topics and Operations**:
- JOIN
- Aggregation (SUM, COUNT)
- Filtering with HAVING

**Scenario**:
To further optimize Gmail's spam filter, it's essential to understand if any emails have received multiple feedback entries as false negatives. False negatives refer to spam emails that were not flagged by the system. Multiple feedback entries for the same email indicate high user dissatisfaction.

**Task**:
Identify emails that have received more than 1 feedback entries as false negatives.
