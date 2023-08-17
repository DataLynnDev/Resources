# Business Problem Statement

Uber Freight seeks to revolutionize freight transportation by efficiently matching shippers and truck drivers using machine learning. The aim is to maximize truck utility, predict shipper demand, and dynamically adjust pricing. However, with the increasing competition and the intricacies of the shipping world, optimizing this matching and pricing is a complex challenge.

---

## Data Tables

**1. Trucks**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| truck_id | Unique identifier for each truck | Integer |
| truck_capacity | Truck's capacity | float |
| load_capacity | Truck's loading capacity | float |
| location | Current location of the truck | String |
| preferences | Preferred types of loads (e.g., fragile, heavy, etc.) | String |
| availability_status | Whether the truck is available or occupied | String |
| last_trip_duration | Duration of the last trip | Float |

**2. Loads**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| load_id | Unique identifier for each load | Integer |
| shipper_id | ID of shipper for the load | Integer |
| weight | Weight of the load | Float |
| type | Type of load (e.g., fragile, heavy, etc.) | String |
| destination | Destination of the load | String |
| origin | Origin of the load | String |
| days_before_deadline | Number of days before the load's delivery deadline | Integer |

**3. Pricing**

| Column Name | Description | Data Type |
|-------------|-------------|-----------|
| load_id | Refers to the load in "Loads" table | Integer |
| price | Price set for the load | Float |
| timestamp | Time when the price was set | DateTime |
| demand_index | Index indicating demand for that type of load (higher value indicates higher demand) | Float |

---

## Questions

1. Conduct an exploratory data analysis (EDA) of the `Trucks` and `Loads` datasets. Identify and visualize the most common types of loads, the distribution of truck capacities, and the frequency of trucks operating below 50% capacity.
    
2. Recent feedback has shed light on an alarming issue. When Uber Freight's pricing doesn't match demand, loads can remain unserved because shippers find them too expensive, or trucks can go underutilized if they're perceived as overpriced by shippers, leading to inefficiencies on both sides. Given the `Pricing` and `Loads` datasets, devise a predictive model to anticipate the demand of a load given the load information. How would past price and demand data inform a more dynamic and responsive pricing strategy? Which metrics would you employ to measure the success of the strategy?

3. Given the success of loyalty programs in various Uber domains, the Freight division is considering launching a "Freight Loyalty Pass" for regular shippers. Leveraging the historical load and pricing information, how would you shape this loyalty program? What would be the criteria for eligibility, and what kinds of benefits or discounts could be embedded without seriously undermining profits?