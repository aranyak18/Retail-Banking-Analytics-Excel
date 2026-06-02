# Retail Banking Analytics: Workforce Efficiency & Customer 360 Pipeline

**Author:** Aranyak Kumar Sharma  
**Tools Used:** Microsoft Excel (Power Pivot, DAX, Power Query, Dynamic Arrays)  
**Dataset:** 50,000+ Synthetic Banking Records  

---

## Project Overview
I built this project to solve a common problem in retail banking: moving away from slow, VLOOKUP-heavy spreadsheets to create a scalable analytics tool. This is a complete business intelligence solution built natively in Excel. It replaces standard flat-file reporting with a relational Star Schema, turning raw transactional data into interactive dashboards. 

The analysis focuses on two specific business objectives:
1. Measuring Relationship Manager (RM) performance and sales efficiency.
2. Identifying cross-sell opportunities within the existing depository customer base to feed the wealth management pipeline.

---

## Data Architecture & Backend
To make this tool scalable and prevent Excel from crashing under heavy data loads, I bypassed standard worksheets and built the backend using Power Pivot.

* **Star Schema Model:** I connected transactional fact tables (`Master_Sales_Data`, `Lead_Pipeline`) to dimension tables (`Customer_Dimension`, `Calendar_Dimension`). This 1-to-Many architecture allows Slicers to filter multiple datasets simultaneously without bloating the file size.
* **DAX Implementation:** I wrote custom DAX measures for metrics like Lead Conversion Rate and Target Achievement % instead of relying on basic Pivot Table aggregations.
* **Error Handling:** I used `NA()` array manipulation techniques to keep complex visualizations (like the scatter plots) mathematically stable when filtered, preventing zero-value plotting errors.

---

## Dashboard 1: RM Performance Scorecard
Designed for Branch Managers to assess salesforce behavior beyond just total volume.

* **Efficiency Matrix (Scatter Plot):** Maps Total Sales Volume against Lead Conversion Rate. This isolates high-effort RMs from high-skill closers, helping managers decide whether an RM needs top-of-funnel volume coaching or closing training.
* **Dynamic Leaderboard:** A conditionally formatted bar chart that tracks absolute sales volume and updates instantly based on geographical and branch-level Slicers.
* **KPI Ribbon:** Clean aggregations for immediate performance benchmarking.

  
<img width="1895" height="792" alt="RM DASHBOARD" src="https://github.com/user-attachments/assets/952c6222-4d50-497a-9fd8-ffff26237f3b" />


---

## Dashboard 2: Customer 360 & Wealth Pipeline
Designed to help sales leaders find hidden liquidity in the current portfolio.

* **Cross-Sell Target List:** Uses a Top-N backend filter with inline Data Bars to isolate the top 15 highest-balance depository clients (Savings/Current) who lack Wealth or Insurance products. This acts as an automated, prioritized call list.
* **HNW Heatmap:** Segments the portfolio by income bracket and risk rating, highlighting clusters of high-liquidity targets.
* **Prospect Tracking:** Relabels non-participating customers as "Untapped Prospects" to shift the focus from missing data to actionable sales targets.

  <img width="1894" height="793" alt="CUSTOMER 360 SCORECARD" src="https://github.com/user-attachments/assets/38ec93fb-5c5e-4812-be5e-48170c804f9b" />

  
---

## Technical Challenges Solved
Building a clean interface inside Excel required bypassing several native software limitations:

1. **Custom Grouping for Data Models:** Excel disables native grouping for Data Model fields. I solved this by writing custom calculated columns (`=IF(E2 < 500000, "1. 0-5L"...)`) directly in the source tables to force Pivot Tables to render standard Indian banking salary brackets.
2. **UI Master Switch Limitations:** Excel forces filter dropdown arrows onto Pivot Table headers. To remove these while keeping column names, I turned off 'Field Headers' and built locked, custom UI headers in a staging sheet before capturing the dashboard visuals.
3. **Linked Picture Stability:** Heavy conditional formatting combined with Excel's camera tool can cause XML corruption. I mitigated this by locking column widths, disabling auto-fit, and routing dynamic arrays through stable staging sheets.

---

## Business Value
1. **Targeted Coaching:** Leadership can allocate training resources based on actual conversion data (the Efficiency Matrix) rather than just looking at total sales.
2. **Actionable Lead Generation:** RMs get a mathematically ranked, highly liquid call list primed for cross-selling, bypassing the need for cold calling.
3. **Automated Scalability:** Because the dashboard runs on a Power Pivot engine, updating the reporting only requires appending new raw data and refreshing the model.
