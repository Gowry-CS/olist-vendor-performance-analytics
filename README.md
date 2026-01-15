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

#### Vendor Category Filter – Targeted Risk Monitoring

A Vendor Category filter allows stakeholders to instantly isolate and analyse specific vendor segments:
- Top Vendors
- At-Risk Vendors
- Growth Potential Vendors
- Low Priority Vendors

The primary tactical use case is monitoring **At-Risk Vendors**, enabling leadership to track stabilisation efforts across financial and operational metrics.

#### GMV Concentration by Vendor Category (Bar Chart)

The clustered bar chart shows a highly concentrated sales distribution:
- **Top Vendors:** $8.9M
- **At-Risk Vendors:** $4.4M

Together, these two categories account for approximately **97% of total GMV** ($13.3M of $13.67M).

The At-Risk segment alone contributes **14.6× more GMV** than the combined sales of Growth Potential and Low Priority vendors, making it a critical focus area.

#### Top & Bottom Vendors by GMV

Analysis of the **Top 10 vendors by GMV** reveals a critical risk:
- Three of the top ten vendors are classified as **At-Risk**
- These vendors contribute over **$582K in GMV** but have lower average review scores (3.36–3.85)

In contrast, the **Bottom 10 vendors**—primarily Growth Potential—have negligible financial impact, with an average GMV of less than **$9**.

This comparison reinforces the strategic need to prioritise stabilising high-value At-Risk vendors rather than focusing on low-impact growth segments.

#### Diagnosing Vendor Performance Drivers (Scatter Plot)

Applying the Pareto Principle, analysis focused on the **542 vendors contributing to 80% of total GMV**.

The scatter plot maps:
- **X-axis:** Average Review Score
- **Y-axis:** Average Days to Handover
- **Bubble size:** Total GMV

Reference lines were set at:
- Average Review Score = 3.98
- Average Days to Handover = 3.67

Most high-GMV vendors cluster in the high-rating, timely-delivery quadrant, confirming alignment between customer satisfaction and operational efficiency.

Notably, a subset of high-GMV vendors shows strong review scores but slower handover times. These vendors represent a strategic opportunity: improving logistics efficiency could unlock additional GMV without risking customer churn.

### 🎯 Business Impact & Recommendations

- Given the At-Risk category's substantial GMV contribution, the immediate strategic focus must be on risk mitigation and stabilization for this group to protect **$4.4M in revenue**.
- Logistics improvements for high-demand vendors with delayed handovers present a low-risk growth opportunity and high immediate GMV acceleration opportunity.
- Leadership focus should prioritise high-impact vendors rather than evenly distributing improvement efforts.

### 🛠️ Tools & Skills Demonstrated

- SQL: Metric calculation, aggregation, segmentation
- Power BI: Explanatory and tactical dashboard design
- Analytical Thinking: Vendor segmentation, Pareto analysis, skew-aware benchmarking
- Business Communication: Translating data into leadership-level insights
