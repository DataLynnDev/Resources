## **Business Problem Statement**

As a data scientist at Microsoft, you are part of the Channels and Teams division. Teams allows for the creation of different teams within an organization. Within these teams, users can create channels for more specific discussions. The business problem at hand is to optimize the usage of Teams and Channels by understanding user behavior, predicting user engagement, and identifying potential areas of improvement to enhance user experience and productivity.

## **Data Tables**

1. **UserActivity** (User ID, Login Time, Logout Time, Team ID, Channel ID, Activity Type, Activity Duration)
2. **UserDetails** (User ID, Joining Date, Role, Location)
3. **ChannelDetails** (Channel ID, Team ID, Creation Date, Channel Type)


### **Table 1: UserActivity**

| Column Name | Description |
|-------------|-------------|
| User ID | Unique identifier for each user |
| Login Time | The time when the user logged in |
| Logout Time | The time when the user logged out |
| Team ID | Unique identifier for each team |
| Channel ID | Unique identifier for each channel within a team |
| Activity Type | Type of activity performed by the user (e.g., message, call, file upload, etc.) |
| Activity Duration | Duration of the activity in minutes |

### **Table 2: UserDetails**

| Column Name | Description |
|-------------|-------------|
| User ID | Unique identifier for each user |
| Joining Date | The date when the user joined the organization |
| Role | Role of the user in the organization (e.g., manager, developer, analyst, etc.) |
| Location | Location of the user (e.g., Seattle, San Francisco, Remote, etc.) |

### **Table 3: ChannelDetails**

| Column Name | Description |
|-------------|-------------|
| Channel ID | Unique identifier for each channel |
| Team ID | Unique identifier for each team |
| Creation Date | The date when the channel was created |
| Channel Type | Type of the channel (e.g., project, department, social, etc.) |

## **Questions**

### **Question 1:**
   Given the UserActivity data, calculate the probability of a user logging in at least once during peak hours (9 AM - 5 PM). How does this probability vary across different roles and locations? 

### **Question 2:** 
   Using the UserActivity and UserDetails data, build a predictive model to forecast user engagement (measured by Activity Duration) for the next week. What features would you consider for this model? Explain the bias-variance tradeoff in the context of your model.

### **Question 3:** 
   Implement a function in Python that identifies the top 5 most active channels (based on total Activity Duration) for each team.

###  **Question 4:** 
   Using the output from Question 3 and the ChannelDetails data, can you identify any patterns or anomalies in the most active channels? For instance, are certain types of channels more active than others?

### **Question 5:** 
   Based on your findings from the previous questions, propose a strategy to improve user engagement on Teams and Channels. How would you communicate these findings and your proposed strategy to a non-technical stakeholder?

