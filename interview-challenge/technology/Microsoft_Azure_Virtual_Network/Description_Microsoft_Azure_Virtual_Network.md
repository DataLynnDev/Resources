# **Business Problem Statement:**
The Azure Virtual Network team aims to improve the efficiency, security, and routing of data flow between various Azure services and resources. As the digital landscape becomes increasingly complex, understanding how to optimize these virtual networks for data science processes becomes paramount. Your role is to assist in the analysis, modeling, and design of these virtual networks based on the provided data.

## **Data Table:**
**VN_data**

| **Column Name**      | **Description**                                              | **Feature Type** |
|----------------------|--------------------------------------------------------------|------------------|
| `Resource_ID`        | Unique ID for Azure resource                                 | Categorical      |
| `Network_Type`       | Type of network (e.g., private, public)                      | Categorical      |
| `Traffic_Volume`     | Average daily data flow (in GB)                              | Numerical        |
| `Connection_Count`   | Number of connected Azure resources                          | Numerical        |
| `Error_Rate`         | Percentage of data packets lost or errored during transfer   | Numerical        |
| `Route_Changes`      | Number of times routing paths have been altered              | Numerical        |
| `Resource_Type`      | Type of Azure resource (e.g., Database, Web App, Storage)    | Categorical      |
| `Response_Time`      | Average response time (in ms) for data requests              | Numerical        |
| `Security_Flag`      | Flag if any security breaches detected (1 for yes, 0 for no) | Binary           |
| `Region`             | Azure data center region                                     | Categorical      |

## **Questions:**

1. **Data Manipulation & Cleaning**:
    - Scenario: The team suspects some of the resources might have discrepancies in their data, which could be outliers. Given the `Traffic_Volume` and `Connection_Count` from the resources, can you identify possible outliers?
  
2. **Probability and Statistics**:
    - Scenario: With the increasing complexity of digital landscape, we observe certain resources experiencing higher error rates than others. Based on the `Error_Rate`, can you statistically validate if resources from a particular `Region` have a significantly different error rate than others?

3. **Machine Learning & Modeling**:
    - Scenario: The company wants to predict `Response_Time` based on various features to ensure efficient data flow. Build a model using the provided features, specifying `Response_Time` as the target variable. Evaluate its performance and recommend if any features might be causing overfitting.

4. **Product Design & Analytics**:
    - Scenario: Azure aims to launch a new feature for the Virtual Network. Given the data, how would you design a system that can automatically redirect traffic or change routes when the `Error_Rate` goes above a certain threshold? Additionally, prioritize between speed of delivery and quality of this end product.