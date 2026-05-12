# Retail-Banking-Analytics-Excel
Retail banking analytics and Customer 360 BI tool. Built with Excel Power Pivot, DAX, and relational Star Schema data modeling.

# 📊 Retail Banking Analytics: Workforce Efficiency & Customer 360 Pipeline

**Author:** Aranyak Kumar Sharma  
**Domain:** Retail Banking, Wealth Management, Business Intelligence  
**Tools & Technologies:** Microsoft Excel (Power Pivot, DAX, Power Query, Dynamic Arrays, Advanced Data Modeling)  
**Scale:** 50,000+ Synthetic Banking Records 

---

## 📑 Executive Summary
In the competitive retail banking sector, transitioning from descriptive reporting ("what happened") to diagnostic and prescriptive analytics ("why it happened and what to do next") is the differentiator for revenue growth. 

This project is an end-to-end business intelligence solution architected entirely within Microsoft Excel. It deprecates fragile `VLOOKUP` architectures in favor of a robust Star Schema relational data model, transforming raw transactional logs into an executive-ready, interactive analytical engine.

The solution tackles two critical banking objectives:
1. **Workforce Optimization:** Evaluating Relationship Manager (RM) efficiency through diagnostic metrics.
2. **Revenue Extraction:** Uncovering trapped liquidity within the existing depository customer base to feed the wealth management cross-selling pipeline.

---

## 🏗️ Backend Engineering & Data Architecture
To ensure scalability, performance, and data integrity, the backend was engineered using standard enterprise dimensional modeling principles, leveraging Excel's internal Analysis Services engine (Power Pivot).

### The Star Schema Model
* **Fact Tables:** Engineered heavy, transactional tables including `Master_Sales_Data` and `Lead_Pipeline` to track granular events, sales volumes, and product assignments.
* **Dimension Tables:** Built unified lookup tables including `Customer_Dimension` (demographics, Indian standard Lakh income brackets, risk ratings) and `Calendar_Dimension` to enable macro-level cross-filtering.
* **OLAP Integration:** The 1-to-Many relational architecture allows Slicers and Timelines to cascade effortlessly across multiple distinct datasets simultaneously, enabling true "slice-and-dice" capabilities without file bloat.

### Advanced DAX & Analytical Logic
Beyond standard aggregations, custom Data Analysis Expressions (DAX) and dynamic formulas were utilized to build the analytical logic:
* **Custom KPIs:** Built precise measures for `Lead Conversion Rate`, `Target Achievement %`, and conditional ranking.
* **Dynamic Error Handling:** Implemented the `NA()` array manipulation technique. This ensures that complex visualizations—specifically the diagnostic scatter plots—remain mathematically and visually stable when subjected to rigorous executive filtering, preventing zero-value plotting errors.

---

## 📈 Dashboard 1: The RM Performance Scorecard
**Target Persona:** Branch Managers & Regional Directors

This dashboard moves beyond standard volume leaderboards to provide diagnostic insights into salesforce behavior.

### Key Features:
* **The Efficiency Matrix (Diagnostic Scatter Plot):** Plots RMs across four distinct quadrants mapping `Total Sales Volume` (Y-Axis) against `Lead Conversion Rate` (X-Axis). This isolates high-effort "grinders" from high-skill "closers," directly informing whether an RM requires top-of-funnel volume coaching or bottom-of-funnel closing training.
* **Dynamic RM Leaderboard:** A conditionally formatted, auto-sorting bar chart tracking absolute sales volume, instantly responsive to geographical and branch-level Slicers.
* **Executive KPI Ribbon:** Clean, high-contrast aggregations operating on a Corporate Trust color palette (Navy/Teal/White) for immediate performance benchmarking.

