Fleet Performance & Delivery Efficiency

📌 Project Overview

Fleet Performance & Delivery Efficiency is a Power BI data analytics project designed to analyze the performance of a logistics company's fleet. The dashboard focuses on delivery performance, fuel efficiency, route analysis, and transportation operations.

The objective is to help understand fleet usage and identify areas where transportation operations can be improved. 
DOC-20260928-WA0000

🎯 Objectives
Analyze total trips and delivery performance.
Measure On-Time Delivery %.
Calculate Fuel Efficiency.
Analyze delivery performance by route.
Monitor fuel consumption and distance travelled.
Analyze vehicle-related information using the Vehicle Master table.
Provide an interactive dashboard for transportation operations.

📊 Dataset

The project uses two main tables:

Trip Data

The Trip Data table contains:

Trip ID
Vehicle ID
Driver ID
Origin
Destination
Distance (km)
Fuel Consumed (liters)
Delivery Status
Delivery Date
Vehicle Master

The Vehicle Master table contains:

Vehicle ID
Vehicle Type
Capacity
Maintenance Cost

These fields are specified in the project requirements. 
DOC-20260928-WA0000

🧹 Data Cleaning & Modeling

The data was cleaned using Power Query.

Data Cleaning
Checked missing values.
Missing fuel-consumption values were handled using the average for the corresponding vehicle type.
Verified data types for numerical, text, and date fields.
Data Modeling

The Trip Data table was related to the Vehicle Master table using:

Vehicle_ID

The project specifically requires this relationship between Trips and Vehicle Master. 
DOC-20260928-WA0000

🧮 DAX Measures
Total Trips
Total Trips =
COUNTROWS('TRIP DATA')
On-Time Trips
On-Time Trips =
CALCULATE(
    COUNTROWS('TRIP DATA'),
    'TRIP DATA'[Delivery_Status] = "On-Time"
)
On-Time Delivery %
On-Time Delivery % =
DIVIDE(
    [On-Time Trips],
    [Total Trips]
)
Fuel Efficiency
Fuel Efficiency =
DIVIDE(
    SUM('TRIP DATA'[Distance_km]),
    SUM('TRIP DATA'[Fuel_Consumed])
)
Cost per km

The project specifies:

Cost per km =
(Fuel Cost + Maintenance Cost) / Distance

Since the dataset contains Fuel Cost and Maintenance Cost, this measure can be implemented using those fields. 
DOC-20260928-WA0000

📈 Dashboard Visualizations

The dashboard contains:

1. On-Time Delivery by Route

A bar/column chart showing the percentage of on-time deliveries for different routes.

2. Fuel Efficiency Trend

A line chart showing how fuel efficiency changes over the delivery dates/months.

3. KPI Cards

The dashboard can display:

Total Trips
On-Time Delivery %
Fuel Efficiency
Cost per km

Average Delivery Time was not included as a calculated KPI because the available dataset does not provide the start and end times needed to calculate actual delivery duration.

4. Delivery Performance Map

A map visual is used to analyze delivery locations/routes using:

Origin
Destination
Delivery Status
Route

The project specification requires a map showing delivery performance by route. 


🛠️ Tools & Technologies
Microsoft Power BI
Power Query
DAX
Data Visualization
Data Modeling

📌 Key Features
Interactive dashboard
Route-wise delivery analysis
On-time delivery monitoring
Fuel-efficiency analysis
Fleet and vehicle analysis
Cost-per-kilometre analysis
Interactive filtering using slicers
Geographic delivery visualization

📂 Project Structure
Fleet-Performance-Delivery-Efficiency/
│
├── Dataset/
│   ├── Trip Data
│   └── Vehicle Master
│
├── PowerBI/
│   └── Fleet_Performance.pbix
│
└── README.md

🚀 Expected Outcome

The final Power BI dashboard provides a consolidated view of fleet performance and delivery efficiency. It enables users to analyze routes, delivery status, fuel efficiency, and transportation costs to support better fleet and route management.

The intended output is a transport operations dashboard for optimizing routes and fleet usage. 
DOC-20260928-WA0000

👩‍💻 Project

Project Title: Logistics & Transportation — Fleet Performance & Delivery Efficiency
Tool: Microsoft Power BI
Domain: Data Analytics / Logistics & Transportation
