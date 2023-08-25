# **Business Problem Statement:**

In an era dominated by remote collaboration, Microsoft Teams aims to be the primary hub for both individual and group communication. By dissecting user behavior within chat threads and understanding collaboration patterns, particularly in the context of file sharing and threaded conversations, Microsoft endeavors to elevate the Teams experience, driving user engagement, and simplifying complex discussions.

## **Data Tables:**

1. **ChatActivity**

| Column Name   | Description                        | Feature Type  |
|---------------|------------------------------------|---------------|
| userID       | Unique Identifier for the user     | Categorical   |
| chatID       | Unique Identifier for the chat     | Categorical   |
| timestamp    | Time of the chat or activity       | Timestamp     |
| messageType  | Type of message (text, file, etc.) | Categorical   |
| messageLength| Length of the message in characters| Numeric       |

2. **ThreadedDiscussions**

| Column Name  | Description                       | Feature Type  |
|--------------|-----------------------------------|---------------|
| threadID     | Unique Identifier for the thread  | Categorical   |
| chatID       | Unique Identifier for the chat    | Categorical   |
| initiatorID  | userID who initiated the thread   | Categorical   |
| responseTime | Time taken to get a reply         | Numeric       |

3. **SharedFiles**

| Column Name  | Description                           | Feature Type  |
|--------------|---------------------------------------|---------------|
| fileID       | Unique Identifier for the file shared | Categorical   |
| chatID       | Identifier for the chat               | Categorical   |
| userID       | User who shared the file              | Categorical   |
| fileSize     | Size of the file in MB                | Numeric       |

## **Questions:**

1. **Scenario:** Microsoft Teams is exploring user engagement patterns, specifically those users who predominantly use text versus those who favor file sharing within chat conversations.
    - **Question:** Based on `ChatActivity` and `SharedFiles`, create a method to segment users into distinct behavioral clusters. Furthermore, if you were to visualize these clusters in a reduced dimension space, which techniques would you suggest?

2. **Scenario:** The effectiveness of threaded conversations is under the lens. There's a notion that certain threads initiate vibrant discussions, while others barely receive any responses.
    - **Question:** Using the `ThreadedDiscussions` and `ChatActivity` table, construct a model to forecast the likelihood of a thread receiving a response within 1 hour. Following your predictions, if there are instances where the model incorrectly forecasts, could you distinguish between instances where it falsely predicted a timely response versus when it inaccurately predicted a delayed response?