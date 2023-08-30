# **Business Problem Statement:**
Microsoft Azure's Blob Storage has become a core part of various organizations' data infrastructures. With the increasing amount of unstructured data like videos, backups, logs, and other documents, there's a need to optimize storage, improve access times, and ensure data quality for better analysis and processing. As a data scientist on the team, your role will be to analyze the usage patterns, detect anomalies, and model predictions for storage needs while ensuring that the storage system continues to meet the demands of its diverse user base.


## Data Table:
**BlobUsageData**

| Column Name     | Description                                              | Feature Type   |
|-----------------|----------------------------------------------------------|----------------|
| User_ID         | Unique identifier for each user                          | Categorical    |
| Blob_Type       | Type of Blob (e.g., video, backup, log, document)        | Categorical    |
| Upload_Date     | Date of blob upload                                      | Datetime       |
| Blob_Size_MB    | Size of the blob in MB                                   | Numerical      |
| Access_Count    | Number of times blob was accessed since upload           | Numerical      |
| Last_Access_Date| Date of the last blob access                             | Datetime       |
| Delete_Flag     | Whether the blob was deleted (0 for No, 1 for Yes)       | Categorical    |

## Questions

**Question 1:**
_You have been provided with the BlobUsageData for the last year. One key concern is optimizing storage._
- Which Blob_Type has the largest cumulative size uploaded in the past year?

**Question 2:**
_You're informed that videos and backups constitute the majority of our blob storage. These large blobs have varying access patterns._
- If you were to sample 5% of the videos and backups uploaded in the past year, what would be the probability distribution based on Access_Count?

**Question 3:**
_Given that we want to predict future storage needs, it's vital to understand the current patterns._
- Using Blob_Size_MB as the target variable, build a regression model taking into account other relevant features. Which features have the most impact on Blob_Size_MB?


