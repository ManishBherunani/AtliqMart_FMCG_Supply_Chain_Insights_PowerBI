# 📊 Atliq Mart Supply Chain Insights

## 📑 Table of Contents
- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Project Summary](#project-summary)
- [Project Objective](#project-objective)
- [Metric Understanding](#metric-understanding)
- [Data Structure Overview](#data-structure-overview)
- [Tools & Skills](#tools--skills)
- [Insights](#insights)
  - [1. Track Key Delivery Metrics](#1-track-key-delivery-metrics-maraug-2022)
  - [2. Evaluate Metrics Against Their Target for Customers](#2-evaluate-metrics-against-their-target-for-customers)
  - [3. City-Level Performance](#3-city-level-performance)
  - [4. Product-Wise Metric Check](#4-product-wise-metric-check)
- [Key Takeaways](#-key-takeaways)
- [Author & Contact](#author--contact)

---

## Project Overview
Atliq Mart, a fast-growing FMCG manufacturer headquartered in Gujarat, India, operates in **Ahmedabad, Surat, and Vadodara**.  
The company plans to expand into metro and tier-1 cities within the next two years and is focusing on strengthening its **supply chain efficiency**.

This project analyzes **daily delivery data across customers, products, and cities** to:
- Identify gaps in the supply chain  
- Improve delivery efficiency  
- Enable data-driven decisions to support expansion  

---

## Problem Statement
Atliq Mart has faced **customer dissatisfaction**, with some key customers not renewing contracts due to poor service.  
Key issues identified:
- Products not delivered **on time**  
- Products not delivered **in full**  

The supply chain analytics team was tasked with tracking:  
- **On-Time Delivery (OT %)**  
- **In-Full Delivery (IF %)**  
- **On-Time In-Full (OTIF %)**  

on a **daily basis**, against customer-defined targets.

---

## Project Summary
This project evaluates **delivery performance** by tracking:
- OT %, IF %, OTIF %, **Line Fill Rate (LIFR %)**, and **Volume Fill Rate (VOFR %)**  
- Performance across **customers, products, and cities**  
- Gaps between **actual results vs. target values**  

The insights guide **operational improvements** and highlight areas needing attention before expansion.

---

## Project Objective
1. **Track Key Delivery Metrics**  
   - OT %, IF %, OTIF %, LIFR %, VOFR % (daily basis).  

2. **Evaluate Metrics Against Customer Targets**  
   - Measure each customer’s performance against predefined targets.  

3. **Analyse City-Level Performance**  
   - Break down OT %, IF %, OTIF % by city to highlight regional gaps.  

4. **Product-Wise Analysis**  
   - Identify top & bottom performing products impacting fulfilment.  

---

## Metric Understanding
- **Line Fill Rate (LIFR %):** % of order lines shipped vs. total lines ordered.  
- **Volume Fill Rate (VOFR %):** % of quantity shipped vs. ordered.  
- **In-Full Delivery (IF %):** Order delivered only if all items match requested quantities.  
- **On-Time Delivery (OT %):** Order delivered only if all items arrive by the agreed time.  
- **On-Time In-Full (OTIF %):** Order delivered both on-time and in-full.  

---

## Data Structure Overview
**Data Source:** CSV files  
**Data Model:** Star schema → **2 Fact Tables + 4 Dimension Tables**

**Fact Tables:**
- `fact_order_lines` → Item-level transactions  
- `fact_order_aggregate` → Order-level aggregated metrics  

**Dimension Tables:**
- `dim_customers` → Customer & city details  
- `dim_products` → Product & category details  
- `dim_date` → Date hierarchy (daily, weekly, monthly)  
- `dim_targets_orders` → Customer-level target metrics  

---

## Tools & Skills
- 🔧 **Tools:** Power BI  
- 📊 **Skills:** Data Modelling, DAX, KPIs, Visualizations (charts, tables, slicers)  

---

## Insights

### 1. Track Key Delivery Metrics (Mar–Aug 2022)

**VOFR % (Volume Fill Rate)**  
- Avg: **96.59%** (target ≥97%)  
- Monthly variation: **96.51%–96.66%** → stable  
- Weekly variation: **96.07%–96.85%** → intermittent dips  
✅ Interpretation: Overall stability reflects strong fulfilment consistency.  

**LIFR % (Line Fill Rate)**  
- Avg: **65.96%**  
- Monthly variation: **65.69%–66.31%** → stable  
- Weekly variation: **63.66%–67.99%** → higher fluctuation  
✅ Interpretation: Performance improves with higher delivery volumes (e.g. July 96.60% → 65.89% vs. August 96.66% → 66.31%), confirming dependency between the two metrics. 

**IF % (In-Full Delivery)**  
- Avg: **52.78%** vs. target **76.51%**  
- Monthly variation: **52.04%–53.66%**  
- Weekly variation: **46.58%–55.40%**  
✅ Interpretation: Consistently under target; highlights systemic fulfilment gaps.  

**OT % (On-Time Delivery)**  
- Avg: **59.03%** vs. target **86.09%**  
- Monthly variation: **58.50%–59.57%**  
- Weekly variation: **57.35%–62.69%**  
✅ Interpretation: Consistently below target, highlighting fulfilment & on-time delivery gaps.  

**OTIF % (On-Time In-Full)**  
- Avg: **29.02%** vs. target **65.91%**  
- Monthly variation: **28.67%–29.39%**  
- Weekly variation: **27.10%–38.84%**  
✅ Interpretation: Persistent underperformance, reflecting systemic gaps in On-Time & In-Full delivery. 

---

### 2. Evaluate Metrics Against Their Target for Customers

**Overall Performance**  
-All customers fall below target for OT %, IF % and OTIF %, with consistent gaps indicating systemic issues in timeliness and completeness of orders.
- VOFR % strong (**95%–98%**) → most ordered volume delivered.  
- LIFR % variable (**52%–76%**) → challenges in fulfilling full line items.  

**Top Customers**  
- Propel Mart, Chiptec Stores, Atlas Stores, Viveks Stores, Expression Stores  
  - VOFR %: **97.5%–97.9%**  
  - LIFR %: **≥75.2%**
  - They also show smaller OT & IF Gaps, resulting in comparatively better OTIF % performance.

**Bottom Customers**  
- Coolblue, Elite Mart, Info Stores, Sorefoz Mart, Acclaimed Stores  
  - VOFR %: **95.1%–95.9%**  
  - LIFR %: **51.5%–58.9%**
  - •	These customers consistently appear at the bottom across multiple metrics.
- ⚠️ **Elite Mart & Sorefoz Mart** show the largest **IF Gaps (-32% to -35%)** and **OTIF Gaps (-39% to -42%)** → critical focus customers.  

**Metric-Wise Insights**  

- **IF % (In-Full Delivery)**  
  - Best: Logic Stores, Expression Stores, Atlas Stores, Propel Mart, Expert Mart (**-15.9% to -20.2% gap**)  
  - Worst: Elite Mart, Sorefoz Mart, Vijay Stores, Info Stores, Coolblue (**-26.3% to -35.1% gap**)  
  - ⚠️ Bottom customers also align with lower VOFR % (<96%) & LIFR % (<55%).  

- **OT % (On-Time Delivery)**  
  - Best: Propel Mart, Sorefoz Mart, Rel Fresh, Atlas Stores, Logic Stores (**-13.0% to -16.7% gap**)  
  - Worst: Lotus Mart, Coolblue, Acclaimed Stores, Info Stores, Expression Stores (**-18.6% to -49.2% gap**)  

- **OTIF % (On-Time In-Full)**  
  - Best: Logic Stores, Propel Mart, Atlas Stores, Expression Stores, Rel Fresh (**-27.7% to -31.5% gap**)  
  - Worst: Acclaimed Stores, Elite Mart, Lotus Mart, Coolblue, Info Stores (**-40.0% to -42.2% gap**)  

---

### 3. City-Level Performance
- **IF %:** Ahmedabad 54.20% (target 77.33%), Surat 52.55% (target 76.91%), Vadodara 51.56% (target 75.33%)
- Interpretation: Lower IF % across all cities is primarily due to weaker VOFR % and LIFR %, indicating incomplete order fulfilment.
  
- **OT %:** Ahmedabad 58.16% (target 85.83%), Surat 61.21% (target 86.27%), Vadodara 57.98% (target 86.17%)
-  Interpretation: Lower OT % across cities is linked to weaker LIFR %, meaning not all order lines were ready for dispatch on the agreed delivery date.
  
- **OTIF %:** Ahmedabad 29.33%, Surat 30.07%, Vadodara 27.78% vs. ~66% targets
- Interpretation: OTIF % performance is directly impacted by gaps in VOFR %, LIFR %, IF %, and OT %, leading to incomplete and delayed deliveries.

✅ All cities underperform need stronger supplier coordination, inventory availability and dispatch execution.  

---

### 4. Product-Wise Metric Check

**Top Products**  
- **VOFR %:** AM Biscuits 750, AM Curd 250, AM Milk 500, AM Ghee 150, AM Curd 100 (**96.62%–96.85%**)  
- **LIFR %:** Same leaders (**66.72%–68.05%**)  
- Observation: Higher VOFR % → higher LIFR %.  

**Bottom Products**  
- **VOFR %:** AM Butter 250, AM Butter 500, AM Biscuits 500, AM Tea 500, AM Tea 250 (**96.52%–96.36%**)  
- **LIFR %:** AM Butter 250, AM Biscuits 250, AM Tea 250, AM Butter 500, AM Ghee 250 (**63.52%–65.25%**)  
- Observation: Overlap of underperforming products (e.g. AM Butter 250 & 500, AM Tea 250) highlights supplier & fulfillment gaps.  

---

## 📌 Key Takeaways
- Strong **VOFR %** shows volumes are mostly fulfilled.  
- Weak **LIFR %, IF %, OT %, OTIF %** reveal systemic supply chain issues.  
- **Integrated improvements** across suppliers, inventory, dispatch, workforce scheduling to reduce delays, Balance ERP/WMS rule and last-mile delivery are essential.  
- Benchmarking top-performing customers/products can guide improvements.  

---

## Author & Contact
**Author:** Manish Bherunani  
**Role:** Data Analyst  
**Email:** manishbherunani@gmail.com  
**LinkedIn:** [linkedin.com/in/manish-bherunani-718b18117](https://www.linkedin.com/in/manish-bherunani-718b18117/)  
