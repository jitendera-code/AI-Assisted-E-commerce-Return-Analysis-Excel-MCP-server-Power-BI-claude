# E-commerce Product Return Analysis Using AI Assistant

### Decision-Driven Analytics | Power BI · DAX · Excel · Claude AI · MCP

## 1. Background & Overview

### Business Context
An India-based e-commerce marketplace sells products across Fashion, Electronics, Home & Kitchen, Sports, Beauty and Books through multiple sales channels. Product returns create refund exposure, operational workload and customer-experience challenges.

### Business Problem
The business needs to understand **why customers return products, where return risk is concentrated, when return risk increases, and which problems should be fixed first**.

### Objective
Use return data to identify the biggest return drivers, locate high-risk product areas, and recommend targeted actions that can be measured after implementation.

## 2. Data Structure / Data Model

### Dataset Overview

| Metric | Detail |
|---|---|
| Period | Jan–Dec 2025 |
| Order-line rows | 4,286 |
| Unique orders | 3,100 |
| Products | 104 |
| Customers | 850 |
| Data grain | One product line per order |

### Main Data Areas

**Orders · Customers · Products · Pricing · Delivery · Returns**

### Power BI Data Model

The model uses **Fact_Orders** with supporting dimensions for **Date, Product, Customer, Channel, Payment Method and Return Reason**.

**Power BI Data Model / ERD:**

![Power BI Data Model](screenshots/data_model.png)

> Key modeling decision: `Order_ID` can repeat across product lines, so order-level KPIs use distinct order counts.

## 3. Executive Summary

The analysis shows that returns are concentrated in a small number of problems. **745 of 3,100 orders were returned (24.03%)**, and the top three reasons — **Product Not As Expected, Wrong Size and Damaged Product** — represent **56.5% of returned units**. Return risk rises sharply toward year-end, while **Fashion has the highest category return rate (26.15%)** and the **₹1K–5K band has the highest return rate (23.28%)**. These findings point to focused product, sizing and operational investigations rather than broad fixes.

![Executive Dashboard](screenshots/excuctive_summary.png)

## 4. Insights Deep Dive

### 1. Three return reasons drive most of the volume

**Finding:** Product Not As Expected (228), Wrong Size (217) and Damaged Product (184) account for **629 of 1,113 returned units (56.5%)**.

**Why it matters:** A small number of problems account for a large share of return volume, giving the business a focused starting point.

<img width="1082" height="486" alt="Return reasons" src="https://github.com/user-attachments/assets/97ed7405-28f4-45d7-9eea-4b8b65aa2684" />

### 2. Fashion has the highest return risk

**Finding:** Fashion has a **26.15% return rate**. Also, **192 of 217 Wrong Size returned units (88%) come from Fashion**.

**Why it matters:** Fashion is the strongest area for a deeper sizing and product-expectation investigation.

<img width="1258" height="462" alt="Category return rate" src="https://github.com/user-attachments/assets/96c56433-8a69-4c59-8aef-7d2a377e501e" />

### 3. Return risk increases sharply toward year-end

**Finding:** Monthly return rate rises from **19.30% in September to 32.16% in December**, a **12.86 percentage-point increase**.

**Why it matters:** Investigate Q4 changes such as product mix, promotions, customer behavior and delivery pressure.

<img width="1047" height="417" alt="Monthly return rate" src="https://github.com/user-attachments/assets/4acc5ef3-1ea5-4a50-8413-bcf3a863a304" />

### 4. The ₹1K–5K segment has the highest return rate

**Finding:** The **₹1K–5K** band has a **23.28% return rate**, versus **13.65%** for products under ₹1K.

**Why it matters:** Drill down by category and return reason before deciding on an intervention.

<img width="1037" height="536" alt="Price range return rate" src="https://github.com/user-attachments/assets/f256e067-f236-4698-a6b3-b269b9688dfe" />

### 5. Damage is concentrated in Electronics and Home & Kitchen

**Finding:** Electronics and Home & Kitchen contribute **139 of 184 Damaged Product returned units (~76%)**.

**Why it matters:** Focus packaging and delivery/handling checks on these categories.

![Diagnostic Dashboard](screenshots/Product_details.png)

## 5. Recommendations

| Priority | Action | Owner | Success KPI |
|---|---|---|---|
| **1** | Improve product-page images, descriptions and specifications | Merchandising / Content | Product Not As Expected rate |
| **2** | Improve size charts and fit guidance, prioritizing Fashion | Fashion / Merchandising | Wrong Size rate + Fashion return rate |
| **3** | Audit packaging and delivery/handling for high-damage products | Operations / Logistics | Damage return rate + Refund Amount |

### Prioritization

Prioritize actions using **return volume + return rate + financial exposure** so teams focus on problems that are significant and actionable.

### Caveats & Assumptions

The dataset identifies **return patterns and priority areas**, but it cannot prove operational causality. Claims about packaging, listings, sizing or logistics should be validated with additional operational evidence before implementation.

No realized savings are claimed because recommendations have not yet been implemented.

### Tools

**Power BI · DAX · Excel · Claude AI · MCP**
