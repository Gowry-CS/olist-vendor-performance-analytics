<div align="center">
<h2>Olist Vendor Performance Analytics</h2>
</div>

<img src="Dashboard/Vendor Performance Dashboard.png" alt="Dashboard">

### 📊 Project Overview

This project analyses vendor performance using Brazilian e-commerce data from Olist to identify the best and worst performing vendors and explain *why* they perform the way they do. The dashboard is designed to support leadership-level decision-making by highlighting financially critical vendors and operational risks.

### 🧭 Business Context & Audience

- **Audience:** Olist Leadership (Executives, VPs)
- **Business Question:** Who are our best and worst vendors, and what actions should we prioritise to improve performance?
- **Dashboard Type:**  
  - **Explanatory:** Tells a clear, focused story using pre-attentive visuals  
  - **Tactical:** Highlights metrics that drive action (e.g. addressing late handovers for high-value vendors)

The dashboard is designed to support targeted intervention rather than broad optimisation, ensuring leadership attention is focused where financial impact is greatest.

### 🔍 Analytical Approach

Vendor performance was evaluated across both **financial contribution** and **operational quality** dimensions. Vendors were segmented using a two-by-two framework based on sales impact and customer satisfaction to ensure fair comparison and actionable insights.

### 🧪 Data Preparation & Vendor Segmentation

- **Gross Merchandise Value (GMV)** was calculated as:  
  **GMV = Product Price × Number of Items Sold**, representing each vendor’s sales contribution.
  
- **Operational efficiency** was measured using **Average Days to Handover**, defined as the time between:
  - `order_purchase_timestamp`
  - `order_delivered_carrier_date`  
  The overall vendor average was **3.67 days**.

- To ensure fair vendor comparison, two thresholds were applied:
  - **Median GMV ($832.41)** as the sales threshold  
    (chosen over the mean due to extreme sales skew ranging from <$10 to >$230K)
  - **Overall Average Review Score (3.98)** as the customer satisfaction benchmark

- Vendors were classified into four categories:
  - **Top Vendors:** High GMV + High Rating
  - **At-Risk Vendors:** High GMV + Low Rating
  - **Growth Potential Vendors:** Low GMV + High Rating
  - **Low Priority Vendors:** Low GMV + Low Rating

This segmentation formed the foundation of the `vendor_category_tbl` used across the dashboard.


**Project Scope**

1. Creating a centralized, structured dataset from raw Olist E-commerce data from 2016 to 2018. <br> 
2. Automating the data pipeline to support scalable and reproducible analysis. <br>
3. Providing actionable insights and recommendations to the Olist management to make informed decisions on Vendor Performance on the platform.<br>

**Objectives**

- Build an End-to-End Data Engineering Pipeline.

- Implement Vendor Performance Specific Statistics and Generate Insights.

- Visualize Vendor Performance as an Interactive Dashboard for Stakeholders. 


**Data Architecture**

This project was implemented in two main stages: Data Engineering and Data Analysis.

1. Data Engineering Pipeline

- Microsoft Fabric was selected as the optimal data engineering and analytics platform due to its provision of a unified, all-in-one Software-as-a-Service (SaaS) solution.

- Leveraging a Medallion Architecture, the systematic flow of data was ensured, guaranteeing progressive quality, governance, and reliability from raw ingestion to final analytical reporting.

2. Teck Stack
   
- Microsoft Fabric<br> 
- Lakehouses<br> 
- Notebooks (PySpark, PySparkSQL)<br>
- Pipeline Activities: Copy Data, ForEach, Teams Alert<br> 
- Dataflow Gen 2<br> 
- Power BI<br> 

3. Gold Lakehouse Schema

- Galaxy Schema with multiple interconnected Fact tables that share common dimension tables _(refer to documentation page 17)_.

- Created dimension tables (e.g., dim_customers, dim_sellers, dim_dates) and fact tables (e.g., fact_orders, fact_reviews) to allow flexible slicing and dicing of the data.

**Analysis**

- Vendor Metrics and Categorisations for performance benchmarking. 

- Creating a explanatory dashboard to provide stakeholders with a data visualisation for suitable business recommendations _(refer to Power BI Dashboard)_.

- Overall, the At-Risk Vendor category is an immediate priority that needs to be stabilised to mitigate critical customer churn.

- Details on Analysis can be found in the documentation pages 18 - 20.
