# 📊 Power BI Case Study: E-Commerce & Logistics Performance Intelligence
> **Strategic Business Analytics & Logistics SLA Performance Audit**  

## 📌 Executive Summary

This end-to-end business intelligence case study was built using **Power BI Project (`.pbip`)** with a Kimball **Star Schema (`Dim_Date`)** and 100% **Explicit DAX Measures**.

Analyzing **113,270 customer orders** (**$23.16M revenue** and **$2.61M net profit**), this report addresses 3 fundamental management questions structured around: **Core Business Question $\rightarrow$ Empirical Data Proof $\rightarrow$ Key Findings $\rightarrow$ Strategic Recommendations**.

---

## ❓ QUESTION 1: WHICH PRODUCT CATEGORY DRIVES CASH FLOW, AND WHERE SHOULD INVENTORY BE FOCUSED?

### 📊 Empirical Evidence:
1. **Category Breakdown (Revenue & Volume):**
   - **`Office Supplies`:** Drives **$13,921,614.58 (60.10% of revenue)** and **133,884 units (60.10% of total volume)** across 68,111 orders.
   - **`Furniture`:** Generates 21.64% of revenue ($5.01M) | 48,053 units.
   - **`Technology`:** Generates 18.26% of revenue ($4.23M) | 40,929 units.

2. **Geographic Concentration (Top 3 Regions):**
   - **West:** 36,295 orders (32.13% volume | $7.42M revenue).
   - **East:** 32,260 orders (28.34% volume | $6.59M revenue).
   - **Central:** 26,314 orders (23.24% volume | $5.39M revenue).
   - *South:* 18,401 orders (16.30% volume | $3.76M revenue).
   - $\rightarrow$ **The Top 3 regions (West, East, Central) account for 83.75% of all orders (94,869 orders) and 83.70% of nationwide inventory throughput.**

### 💡 Conclusion:
- `Office Supplies` is the economic backbone of the enterprise. Any stock-out in this category directly jeopardizes over 60% of top-line cash flow.
- Warehouse expansion, 3PL logistics partnerships, and replenishment buffers must be strictly prioritized in **West, East, and Central**.

---

## ❓ QUESTION 2: DOES A >54% LATE RATE PROVE SHIPPING METHODS ARE FAILING, AND SHOULD TIERS BE CONSOLIDATED?

### 📊 Empirical Evidence:
- **System-Wide Alert:** **62,051 out of 113,270 orders were marked late (`Late delivery`), representing a 54.78% SLA breach rate**.
- **Customer Risk:** The retail **`Consumer`** segment carries the highest impact with **32,231 late orders (51.94% of all late shipments)**, directly threatening customer lifetime value (CLV) and NPS.

#### Breakdown of the 4 Shipping Classes:
| Shipping Tier | Promised SLA | Actual Delivery | Late Orders | Late Rate | On-Time Orders | Advance Shipping | Advance % |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **`Same Day`** | 0 days | 0.49 days | 2,880 | **46.56%** | 3,044 | 0 | 0.00% |
| **`First Class`** | 1 day | 2.00 days | 16,542 | **95.05%** | 0 | 0 | 0.00% |
| **`Second Class`** | 2 days | 3.96 days | 16,850 | **76.41%** | 4,320 | 0 | 0.00% |
| **`Standard Class`** | 4 days | 3.95 days | 25,779 | **38.12%** | 13,029 | **25,930** | **38.34%** |

- **`Same Day`:** Nearly half of all orders (46.56%) spill over into the next day despite customers paying premium rates.
- **`First Class`:** 100% of orders deliver consistently on Day 2 (`mean = 2.00 days`). A 1-day promise artificially tags 95.05% of shipments as failed SLAs.
- **`Second Class` vs. `Standard Class` Parity:** Both tiers take identically **~3.95 days** to deliver. Yet Second Class incurs a 76.41% late rate due to an unrealistic 2-day SLA, whereas Standard Class generates **25,930 early deliveries (`Advance shipping`: 38.34%)** against a 4-day SLA.

### 💡 Conclusion:
**TIER CONSOLIDATION OR CANCELLATION IS NOT REQUIRED.**  
Physical transit capabilities are performing solidly (First Class delivers within 2 days; Standard Class delivers in 3.95 days nationwide). The core failure is **"Unrealistic SLA Promising"**—promising delivery dates tighter than operational fulfillment physics allow.

---
## 🎯 STRATEGIC RECOMMENDATIONS
Recalibrating front-end promised delivery windows to match actual logistics lead times:
- `Same Day`: Keep at **0 days** (focus on hub picking efficiency).
- `First Class`: Update promised SLA from 1 day $\rightarrow$ **2 days**.
- `Second Class`: Update promised SLA from 2 days $\rightarrow$ **3 or 4 days**.
- `Standard Class`: Update promised SLA from 4 days $\rightarrow$ **5 days**.
