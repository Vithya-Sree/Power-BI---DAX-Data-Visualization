# Power-BI---DAX-Data-Visualization
Project Overview
An enterprise-grade Power BI business intelligence dashboard designed to transform decentralized e-commerce transaction data, geographic logistics logs, and organizational targets into an interactive analytical tool. This analytics solution implements an efficient star-schema data model and advanced DAX metrics to track financial performance, measure budget variance, map product portfolio health, and audit regional profitability.

## 🎯 Business Objectives* 
*Variance Tracking:* Audit actual sales performance against corporate goals across distinct product categories.* 
*Profitability Mapping:* Isolate top-performing, high-margin items from sub-categories driving operational drag or loss.* 
*Temporal Trend Diagnostics:* Smooth chronological noise to isolate macroeconomic seasonality and growth cycles.* 
*Regional Insights:* Target localized profitability tracking within primary operational geographic hubs (e.g., Delhi territory).

## 🛠️ Tech Stack & Key Features* 
*BI Tool:* Microsoft Power BI Desktop* 
*Data Modeling:* Power Query (ETL), Relational Schema Design, Filter Context Optimization* 
*Analytical Calculations:* Data Analysis Expressions (DAX)* 
*Visualizations:* Custom Summary Cards, Clustered Bar/Column Charts, Multi-Axis Scatter Plots, Interactive Dropdown Slicers

## 📐 Data Architecture & Schema
The data architecture follows a structured star-schema relational model built on standard relational principles:
1. *List of Orders (Dimension Table):* Captures temporal and logistical metadata (Order ID, Order Date, Customer Name, City, State).
2. *Order Details (Fact Table):* Tracks raw transaction quantities (Amount, Profit, Quantity) and houses custom-engineered calculated metrics.
3. *Sales_Target (Dimension Table):* Contains monthly sales targets distributed by high-level category benchmarks.
4. *Calendar (DAX Generated Table):* A dedicated, continuous calendar dimension built to stabilize temporal reporting and run robust time-intelligence formulas.
   
### 🔗 Model Relationship Optimization
* Built a controlled, *Many-to-Many (:\)* relationship between Sales_Target and Order Details on the Category key.
* Configuration restricted to a *Single (Sales_Target filters Order Details)* cross-filter direction.
* This custom context protects data integrity, ensuring target budgets filter actuals seamlessly without causing double-counting or data inflation.

<img width="970" height="478" alt="image" src="https://github.com/user-attachments/assets/059d5a37-c5fc-48f2-b22f-cdd2c5c23a58" />

## 📝 Core DAX Formulas Applied#
## Time Intelligence Foundationdax
Calendar = 
VAR MinDate = MIN('List of Orders'[Order Date])
VAR MaxDate = MAX('List of Orders'[Order Date])
RETURN
ADDCOLUMNS (
    CALENDAR(DATE(YEAR(MinDate), 1, 1), DATE(YEAR(MaxDate), 12, 31)),
    "Year", YEAR([Date]),
    "Month Name", FORMAT([Date], "MMMM"),
    "Month Number", MONTH([Date]),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Year Month", FORMAT([Date], "YYYY-MM")
)


### Executive KPI Core Measuresdax
Total Sales = SUM('Order Details'[Amount])

Total Target = SUM('Sales_Target'[Target])

Order Count = DISTINCTCOUNT('List of Orders'[Order ID])

Average Profit in Delhi = 
CALCULATE(
    AVERAGE('Order Details'[Profit]),
    'List of Orders'[City] = "Delhi"
)

Profit Margin = DIVIDE('Order Details'[Profit], 'Order Details'[Amount], 0)

## 📈 Visual Matrix & Analytical Insights* 
## Executive Headline Cards (Summary KPI Block)
Four large number cards sit at the very top of the page to give managers a quick, two-second health check of the business:

   1. Total Sales ($431.5K): Shows the total amount of money the business brought in from all sales.
   2. Total Target ($435.9K): Shows the total sales goal set by the company. Comparing this to Total Sales shows we are just slightly short of our global target.
   3. Order Count (500): Shows the total number of customer orders processed by our team.
   4. Avg Profit Delhi ($43): Shows the average profit made on an order coming from Delhi. It helps monitor our performance in this key city.

<img width="560" height="97" alt="image" src="https://github.com/user-attachments/assets/aee7f877-5d4d-4cd1-b484-9379b8b9a6e2" />


## Core Analytical Charts

* Sales Target Achievement by Category (Column Chart):
  This chart compares actual sales numbers directly against our goals for each main department.
  It shows that Clothing and Electronics are doing great and meeting expectations, while Furniture is falling short of its sales goals.
  <img width="769" height="435" alt="image" src="https://github.com/user-attachments/assets/52a52845-02f6-43a9-94db-48b2cca55523" />
* Business Action: Managers should figure out why furniture isn't selling well or put more marketing money into the successful clothing and electronics departments.

* Maximum Profit Margin by Sub-Category (Horizontal Bar Chart):
  This chart ranks our specific products by their highest profit percentages rather than just total sales volume.
  It helps us spot "hidden heroes" like Handkerchiefs that make a great return on investment, while highlighting items at the bottom that are losing money.
  <img width="772" height="435" alt="image" src="https://github.com/user-attachments/assets/0114d3be-1022-438a-9782-12300a3adca5" />
* Business Action: The team should promote high-profit products more and talk to vendors to lower costs for items at the bottom of the list.
  
* Monthly Sales Trend (Line Chart):
  This chart tracks our sales month-by-month across the year.
  By looking at months instead of individual days, the line smooths out and shows us exactly when sales peak and when they drop.
  <img width="770" height="434" alt="image" src="https://github.com/user-attachments/assets/ff949215-a834-4895-95a0-85ead3c9c58c" />
* Business Action: This helps the logistics team order more inventory and hire extra staff ahead of time for high-demand shopping months.
  
* Portfolio Diagnostics (Scatter Plot):
  This chart places products on a grid based on two things: how many items we sell (X-axis) and how much profit they make (Y-axis).
  It separates our "superstars" (high sales, high profit) from "warning items" (selling in high quantities but making very little or negative profit).
  <img width="771" height="432" alt="image" src="https://github.com/user-attachments/assets/2b09a912-977d-48fe-a7c4-3cea2a0d8744" />
* Business Action: This tells us exactly where we need to raise prices or stop selling items that require a lot of work but don't bring back money.

<img width="783" height="450" alt="image" src="https://github.com/user-attachments/assets/373f2299-d0d8-45a4-922d-95ef67b26fc0" />


## 🚀 Key Takeaways & Impact
1. *Dynamic Drill-Down:* Integrated interactive *Year* and *Category* dropdown slicers, enabling leadership to audit precise performance windows instantly.
2. *Margin Optimization:* Highlighted high-efficiency products to guide targeted inventory changes and maximize returns per dollar spent.
3. 3. *Strategic Alignment:* Provided clear visual data showing where actual revenue lags behind targets, allowing leadership to re-evaluate underperforming pipelines.
      
## 📂 Project Structuretext
├── Data/
│   ├── List of Orders.csv
│   ├── Order Details.csv
│   └── Sales_Target.csv
├── Dashboard/
│   └── Sales_Performance_Dashboard.pbix
└── README.md
