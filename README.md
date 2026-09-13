# E-commerce Product Return Analysis Using AI Assistant

### Decision-Driven Analytics | Power BI · DAX · Excel · Claude AI · MCP

---

## 📑 Table of Contents

- [📖 Project Background](#-project-background)
- [🎯 Business Problem](#-business-problem)
- [🗂️ Data Structure / Data Model](#️-data-structure--data-model)
- [📊 Executive Summary](#-executive-summary)
- [⚙️ Project Methodology](#️-project-methodology)
- [🛠️ Technical Skills Demonstrated](#️-technical-skills-demonstrated)
- [📈 Insights Deep Dive](#-insights-deep-dive)
- [💡 Business Recommendations](#-business-recommendations)
- [🚀 Future Improvements](#-future-improvements)

---

# 📖 Project Background

An India-based e-commerce marketplace sells products across Fashion, Electronics, Home & Kitchen, Sports, Beauty and Books through multiple sales channels. Product returns create refund exposure, operational workload and customer-experience challenges.

This project analyzes order, product, pricing, delivery and return data to identify the biggest return drivers, locate high-risk product areas, and translate findings into targeted business actions.

The analysis focuses on four decision areas:

**Return Drivers:** Understand the most common reasons customers return products.

**Return Risk:** Identify categories, products and price ranges with higher return rates.

**Time Patterns:** Understand when return risk increases during the year.

**Action Prioritization:** Determine which return problems should be addressed first using return volume, return rate and financial exposure.

---

# 🎯 Business Problem

The business needs a clearer understanding of **why customers return products, where return risk is concentrated, when return risk increases, and which return problems should be fixed first**.

Key business questions include:

- Which return reasons create the largest return burden?
- Which product categories have the highest return risk?
- How does return risk vary by price range and month?
- Which product/problem areas deserve deeper investigation?
- What actions should the business prioritize?

Answering these questions helps product, merchandising and operations teams focus resources on the return problems with the greatest business impact.

---

# 🗂️ Data Structure / Data Model

| Attribute | Details |
|---|---|
| Analysis Period | Jan–Dec 2025 |
| Order-line Rows | 4,286 |
| Unique Orders | 3,100 |
| Products | 104 |
| Customers | 850 |
| Data Granularity | One product line per order |

### Main Data Areas

**Orders · Customers · Products · Pricing · Delivery · Returns**

### Power BI Data Model

The model uses **Fact_Orders** with supporting dimensions for **Date, Product, Customer, Channel, Payment Method and Return Reason**.

![Power BI Data Model](screenshots/data_model.png)

> Key modeling decision: `Order_ID` can repeat across product lines, so order-level KPIs use distinct order counts.

---

# 📊 Executive Summary

The analysis shows that returns are concentrated in a small number of problems. **745 of 3,100 orders were returned (24.03%)**, with **Product Not As Expected, Wrong Size and Damaged Product** accounting for **56.5% of returned units**. **Fashion has the highest category return rate at 26.15%**, while return risk rises from **19.30% in September to 32.16% in December**. These findings point to focused product, sizing and operational investigations rather than broad fixes.

<img width="1387" height="747" alt="Executive dashboard" src="https://github.com/user-attachments/assets/c88e15eb-bc49-44fc-9f08-52a6a8d77458" />

---

# 🗂️ Dataset Overview

| Attribute | Details |
|---|---|
| Dataset | E-commerce Returns & Refunds |
| Analysis Period | January 2025 – December 2025 |
| Total Records | 4,286 order lines |
| Customers | 850 |
| Orders | 3,100 |
| Products | 104 |
| Primary Focus | Product Returns & Refund Exposure |
| Data Granularity | One row per order line |

---

# ⚙️ Project Methodology

1. Prepared and validated the raw e-commerce returns dataset.
2. Standardized return reasons and defined the return condition using `Return_Quantity > 0`.
3. Built Power BI measures for return rate, returned units, refund amount and return timing.
4. Analyzed return patterns by reason, category, price range, month and product.
5. Drilled into subcategory and product-level performance to identify priority areas.
6. Used the findings to develop evidence-based root-cause hypotheses and business recommendations.

---

# 🛠️ Technical Skills Demonstrated

| Category | Skills |
|---|---|
| **Excel** | Data review, validation, filtering, structured analysis |
| **Power BI** | Data Modeling, DAX Measures, KPI Cards, Interactive Dashboards, Slicers, Drill-down Analysis |
| **DAX** | Return Rate, Returned Units, Refund Amount, Average Return Days, Time-based measures |
| **Business Analytics** | Return Analysis, Root-Cause Hypotheses, KPI Analysis, Prioritization, Business Storytelling, Recommendations |
| **AI-Assisted Analytics** | Claude AI, MCP-based Power BI model inspection, DAX development and validation |

---

# 📈 Insights Deep Dive

## Return Reason Analysis

<img width="1082" height="486" alt="Return reasons" src="https://github.com/user-attachments/assets/97ed7405-28f4-45d7-9eea-4b8b65aa2684" />

The top three return reasons — **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** — account for **629 of 1,113 returned units (56.5%)**.

This gives the business a focused starting point: address the few problems responsible for the largest share of returns instead of treating every return reason equally.

## Category Return Risk

<img width="1117" height="465" alt="Category return rate" src="https://github.com/user-attachments/assets/96c56433-8a69-4c59-8aef-7d2a377e501e" />

**Fashion has the highest return rate at 26.15%.** A deeper drill-down shows that **192 of 217 Wrong Size returned units (88%) come from Fashion**, making sizing and fit guidance a priority area for investigation.

## Monthly Return Trend

<img width="1047" height="417" alt="Monthly return rate" src="https://github.com/user-attachments/assets/4acc5ef3-1ea5-4a50-8413-bcf3a863a304" />

Return rate rises from **19.30% in September to 32.16% in December**, an increase of **12.86 percentage points**. The business should investigate changes in Q4 such as product mix, promotions, customer behavior and delivery pressure.

These are **investigation hypotheses, not proven causal drivers**.

## Price Range Return Risk

<img width="1037" height="536" alt="Price range return rate" src="https://github.com/user-attachments/assets/f256e067-f236-4698-a6b3-b269b9688dfe" />

The **₹1K–5K price band has the highest return rate at 23.28%**, compared with **13.65% for products under ₹1K** — a **9.63 percentage-point difference**. This segment should be reviewed by category and return reason before selecting an intervention.

## Damage Concentration

Electronics and Home & Kitchen contribute **139 of 184 Damaged Product returned units (~76%)**. This narrows the operational investigation toward packaging and delivery/handling for these categories.

<img width="1272" height="752" alt="Diagnostic dashboard" src="https://github.com/user-attachments/assets/499c4a07-b057-40ff-8bd4-4acaf2d5d348" />

---

# 💡 Business Recommendations

Based on the analysis, the following actions should be prioritized:

### 🛍️ Product / Merchandising

- **Improve product-page images, descriptions and specifications** for Product Not As Expected returns.
- **Improve size charts and fit guidance** for Fashion, where Wrong Size returns are highly concentrated.

### 📦 Operations / Logistics

- **Audit packaging and delivery/handling** for products with high Damage return concentration, especially in Electronics and Home & Kitchen.

### 📊 Prioritization Logic

Prioritize using:

**Return Volume + Return Rate + Financial Exposure**

The objective is to focus resources on problems that are both significant and actionable.

### Caveats & Assumptions

The dataset identifies **return patterns and priority areas**, but it cannot prove operational causality. Claims about packaging, listings, sizing or logistics should be validated with additional operational evidence before implementation.

No realized savings are claimed because the recommendations have not yet been implemented.

---

# 🚀 Future Improvements

- Automate weekly return-performance reporting.
- Add operational data such as packaging type, carrier and customer feedback to strengthen root-cause validation.
- Measure before-vs-after KPI changes for each intervention.
- Add drill-through views for priority products and subcategories.

---

# 📂 Repository Structure

```text
├── README.md
├── analysis/
├── data/
├── excel/
├── powerbi/
├── screenshots/
└── docs/
```

