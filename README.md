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

### 📌 Key Performance Benchmarks

The dashboard establishes a high-level performance baseline for all vendors:

- **Total GMV:** $13.76M
- **Average Vendor Review Score:** 3.98
- **Overall On-Time Delivery Rate:** 85%

These benchmarks provide the reference point for identifying outliers and prioritising intervention.

### 📊 Dashboard Walkthrough and Insights

#### KPI Cards – Performance at a Glance

The KPI cards provide immediate context by defining what “good performance” looks like across financial, customer satisfaction, and logistics dimensions.
