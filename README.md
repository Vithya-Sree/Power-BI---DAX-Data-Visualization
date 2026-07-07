# 📊 Retail Sales Performance & Logistics Optimization Dashboard

An end-to-end Power BI business intelligence solution to audit sales targets, isolate profit leaks, and optimize regional supply chains.

## 🎯 Project Overview
This project transforms raw transactional retail data into an interactive, four-page reporting suite. 
It bridges the gap between raw backend metrics and executive decision-making.

## ⚠️ Business Problem
The enterprise lacked visibility into monthly target fulfillment, suffered from hidden profit drains due to high-volume/negative-margin products, and lacked data-driven insights to optimize physical shipping and logistics routes.

## 📊 Dashboard Architecture & Charts
The reporting suite is divided into four dedicated dashboards:

### 1. Executive Summary
<img width="976" height="546" alt="image" src="https://github.com/user-attachments/assets/572b9c36-fdda-45bb-b3ca-fcaed22aef5a" />

* **KPI Cards:** Total Sales ($432K), Order Count (500), Total Target ($436K), and Average Profit.
* **Line Chart:** Sum of Amount by Month tracking seasonal trends.
* **Clustered Column Chart:** Sales Target Achievement by Category.
* **Horizontal Bar Chart:** Maximum Profit Margin by Sub-Category.

### 2. Sales Target Matrix
![Uploading image.png…]()

* **Matrix View:** Monthly financial ledger cross-referencing sales vs. targets.
* **Gauge Chart:** Total Target Progression vs. milestone boundary ($431.5K reached).
* **Multi-Row Card:** Minimum operational baseline thresholds per segment.

### 3. Product Deep Dive
![Uploading image.png…]()

* **Treemap:** Revenue market share distribution by sub-category.
* **Scatter Chart:** Profit vs. Quantity matrix mapping high-volume financial drains.
* **Donut Chart:** Peak profit margin efficiencies across product lines.

### 4. Logistics & Regional Hubs
![Uploading image.png…]()

* **Funnel Chart:** Transaction volume distribution ranked by State.
* **Bubble Map:** Geolocation plot mapping Total Sales by City across India.

## 📈 Key Business Insights
* **Target Variance:** Achieved 99% of global goals, missing the $436K target by a narrow $4K.
* **Segment Performance:** Electronics beat its target ($165.2K generated), while Clothing severely underperformed ($35K shortfall).
* **Profit Outliers:** High-volume items like Tables and Chairs operate below the zero-profit line, causing direct cash drains.
* **Supply Anchors:** Madhya Pradesh (101 orders) and Maharashtra (90 orders) stand out as the primary regional throughput hubs.

## 🚀 Strategic Recommendations
* Adjust pricing, renegotiate vendor costs, or bundle negative-margin furniture items with high-margin accessories (e.g., Handkerchiefs).
* Build localized fulfillment centers in Madhya Pradesh and Maharashtra to cut transit times and reduce last-mile shipping fees.

## 🛠️ Tools Used & Skills Demonstrated
* **Power BI Desktop:** Core platform for ETL, data modeling, and reporting.
* **Data Modeling:** Built relational schemas connecting transactions, targets, and locations.
* **DAX Formulas:** Developed calculated columns (`Category Type`, `Revenue per Order`, `Sales Category`) and dynamic measures (`Order Count`, `YTD Sales`, `Average Profit`).

## 🏁 Conclusion
This dashboard successfully unifies disparate retail data into actionable strategies. By tackling target blindness, highlighting negative-margin items, and mapping out logistics hubs, it equips management to plug profit leaks and scale operations efficiently.

