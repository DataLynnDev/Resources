# **Business Problem Statement**:

A Content Delivery Network (CDN) is a network of distributed servers that deliver web content to users based on their geographic location, the origin of the content, and the content delivery server itself. Netflix, being a global streaming giant, has one of the most advanced CDNs to ensure that its vast user base has an uninterrupted and high-quality viewing experience.

Netflix has noted a decline in streaming quality for a subset of users during peak hours in certain geographical regions. This decline has led to a higher churn rate among these affected users. The company believes optimizing its CDN could alleviate this problem and improve user experience.

## **Data Tables**:

### Table 1: **UserStreamData**
| Column Name     | Description                                         | Data Type  |
|-----------------|-----------------------------------------------------|------------|
| userID          | Unique ID for the user                              | Integer    |
| streamDate      | The date of streaming                               | Date       |
| streamTime      | The time of day the user streamed content           | Time       |
| region          | Geographical region of the user                     | String     |
| bandwidth       | Bandwidth available during streaming                | Float      |
| resolution      | Resolution of the streamed content                  | Integer    |
| serverID        | ID of the server catering the user                  | Integer    |
| res_downgrade   | Whether the user downgrade resolution in this streaming session| Boolean   |

### Table 2: **ServerLoadData**
| Column Name | Description                               | Data Type  |
|-------------|-------------------------------------------|------------|
| serverID    | ID of the server                       | Integer    |
| region      | region of the server                      | String    |
| date        | Date                                   | Date       |
| peakLoad    | Maximum number of users at a given time| Integer    |
| avgLoad     | Average number of users during the day | Float      |


## **Questions**:

1. **Adaptive Streaming and User Experience**: From the `UserStreamData`, you have observed that users from a particular region during certain hours experience low bandwidth, causing their streams to frequently switch resolutions. Can you identify the peak hours and specific regions where this behavior is most prevalent, and suggest a potential solution using adaptive streaming principles?

2. **Server Load Distribution**: Based on the given server load from the `ServerLoadData`, identify any servers that might be consistently nearing their peak capacity. Using this information, propose a potential load balancing strategy to ensure a more even distribution of user requests across servers during peak hours. How would this likely affect users' streaming experiences, especially in terms of resolution consistency

3. **Optimizing Bandwidth Distribution**: By analyzing the `UserStreamData`, determine which regions have the most users facing bandwidth issues. Based on the identified regions, propose a strategy to optimize bandwidth distribution to enhance user experience, considering both peak and off-peak hours.

4. **Custom Question on Adaptive Streaming and Load Balancing**: Netflix plans to introduce a new 4K streaming option in selected regions. This will demand more from the CDN. Using the `UserStreamData` and `ServerLoadData` tables, simulate the potential impact on the CDN if 10% of users in a given region upgraded to 4K streaming. Which servers might be overwhelmed, and how might this impact adaptive streaming in those regions?