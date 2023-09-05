# Business Problem Statement:
The Zillow Home Valuation Team has observed fluctuations in the Zestimate accuracy for various homes across the U.S. There's a need to assess, refine, and potentially improve the current Zestimate algorithm to provide more accurate estimations and cater to the dynamic real estate market.

## Data Table:
**Table: HomeData**

| Column Name      | Description                                                   | Feature Type |
|------------------|---------------------------------------------------------------|--------------|
| HomeID           | Unique identifier for each home                               | Categorical  |
| PhysicalAttrib   | Physical attributes of the home (e.g., # of rooms, sq. footage)| Continuous   |
| TaxAssessment    | Most recent tax assessment value                              | Continuous   |
| LastSoldPrice    | Last transaction price of the home                            | Continuous   |
| LastSoldDate     | Date of the last transaction                                  | Date         |
| Zestimate        | Current Zestimate value                                       | Continuous   |
| UrbanOrRural     | Classification as urban or rural                              | Categorical  |
| NearbyAvgPrice   | Average price of the 5 closest homes                          | Continuous   |
| State            | State in which the home is located                            | Categorical  |
| SavedCount       | Number of times home was saved by users                       | Continuous   |

## **Questions**:

1. **Data Manipulation & Cleaning Question**:  
**Scenario**: You've been informed that some of the homes in our database may have outdated Zestimates. By analyzing the gap between `LastSoldPrice` and `Zestimate`, and considering homes sold in the last 6 months, identify homes that might have outdated Zestimates and which states have the highest percentage of such homes.  


2. **Probability and Statistics Question**:  
**Scenario**: For each state, determine the variability (standard deviation) of the `NearbyAvgPrice` in urban and rural areas. How does this variability compare with the overall variability of Zestimate for these homes? And how might this information be relevant in refining the Zestimate algorithm?  


3. **Machine Learning & Modeling Question**:  
**Scenario**: You suspect that certain physical attributes of homes might be leading to inconsistencies in Zestimate values. Develop a predictive model using relevant features to predict the `Zestimate` value. While building this model, consider techniques to handle potential overfitting, especially given the rural and urban divide in the data. Clearly indicate which feature is your target variable.  
**Target Variable**: `Zestimate`  

4. **Product Design & Analytics Question**:  
**Scenario**: The number of times a home is saved (`SavedCount`) can be an indirect indicator of its popularity or demand. Suppose there's a new feature in the pipeline that would allow users to get instant notifications for homes with high `SavedCount`. How would you leverage the current data to determine the threshold for "high `SavedCount`"? Also, discuss potential implications on the Zestimate value for homes that get flagged with this feature.  

