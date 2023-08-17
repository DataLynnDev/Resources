# Business Problem Statement

The Customer Relationship Management (CRM) department of a leading telecommunications company is grappling with high customer churn rates, which are significantly impacting the company's profitability. Despite having a vast database of customer information, the CRM team lacks the necessary tools and expertise to leverage this data for anticipating and mitigating churn effectively. Recognizing the potential of data-driven decision-making, the CRM department's leadership has turned to Accenture for its expertise in advanced analytics. Their goal is to use their existing customer data to identify the customers most likely to churn, which would enable them to implement proactive retention strategies.

The task at hand involves undertaking a comprehensive data analysis exercise to identify indicators of churn. We need to examine these signals across different customer segments, integrate external market trends with churn indicators, and analyze churn patterns over time. Using these insights, we'll engineer features that accurately predict customer churn, build a predictive model, and subsequently, help the CRM department design strategies to enhance customer retention.

## Data Challenge Tables


**Table 1: Customer_Profile**



| Feature Name | Description |
| ------------ | ----------- |
| Customer_ID | Unique identifier for each customer |
| Age | Age of the customer |
| Gender | Gender of the customer |
| Location | Geographic location of the customer |
| Subscription_Type | The type of plan the customer has subscribed to |
| Tenure | The number of months the customer has stayed with the company |
| Churn | Whether the customer has churned or not |


**Table 2: Billing_Data**


| Feature Name | Description |
| ------------ | ----------- |
| Customer_ID | Unique identifier for each customer |
| Monthly_Charge | Monthly charges for the services provided |
| Total_Charges | The total amount charged to the customer for the entire tenure |
| Payment_Method | The method used by the customer to make payments |
| Late_Payments | The number of late payments made by the customer |

**Table 3: Customer_Service_Records**


| Feature Name | Description |
| ------------ | ----------- |
| Customer_ID | Unique identifier for each customer |
| Total_Calls | The total number of calls made by the customer to the service team |
| Total_Complaints | The total number of complaints logged by the customer |
| Resolved_Complaints | The number of complaints that were resolved |
| Unresolved_Complaints | The number of complaints that are unresolved |

**Table 4: Market_Trends**

This table incorporates the external factors and market trends.

| Feature Name | Description |
| ------------ | ----------- |
| Date | The date of the observation |
| Competitor_Offerings | The number of new offerings launched by competitors |
| Technological_Changes | The number of significant technological changes in the market |


## Questions for the Data Challenge

**1. "Identification of Churn Indicators"**

Utilizing the 'Customer_Profile', 'Billing_Data', and 'Customer_Service_Records' tables, extract key indicators that could potentially signal customer churn. Describe the peculiarities you might expect in each churn signal group.


**2. "Analysis of Churn Indicators Across Different Customer Segments"**

Using Python, identify patterns in the churn indicators across different customer demographics like age, location, or subscription type. Explain how your findings could refine the understanding of customer churn across different segments.


**3. "Investigation of the Impact of Complaint Resolution on Churn in High-Tenure Customers"**

Assume that you've noticed a higher churn rate amongst high-tenure customers who have unresolved complaints. Using Python, perform an analysis to confirm if unresolved complaints significantly influence the churn rate in high-tenure customers compared to those with resolved complaints.


**4. "Creating Customer Interaction Graphs"**

 Using Python, construct a graph data structure to map customers' interactions with the telecommunication service, specifically focusing on the total number of service calls made by customers. Explore and describe any emergent patterns in this graph that could signal churn.


**5. "Feature Engineering for Churn Prediction"**

Develop new features such as 'Average_Service_Complaints', 'Payment_Frequency_Change', and 'Usage_Decrease' ratios from the identified churn indicators.

**6. "Development and Optimization of Churn Prediction Model"**

 Implement a predictive model in Python using these features and elaborate on how this model will steer proactive customer retention strategies.