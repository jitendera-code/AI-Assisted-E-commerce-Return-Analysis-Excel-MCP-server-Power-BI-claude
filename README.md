# E-commerce Product Return Analysis Using AI Assistant

### Decision-Driven Analytics | Power BI · DAX · Excel · Claude AI · MCP

> **Primary Business Decision:** Which return problems should the business prioritize first to reduce return risk and refund exposure?

---

## 📑 Table of Contents

- [📖 Project Background](#-project-background)
- [🎯 Business Problem](#-business-problem)
- [⭐ North Star Metrics](#-north-star-metrics)
- [🗂️ Data Structure / Data Model](#️-data-structure--data-model)
- [📊 Executive Summary](#-executive-summary)
- [📈 Insights Deep Dive](#-insights-deep-dive)
- [💡 Business Recommendations](#-business-recommendations)
- [⚙️ Methodology & Technical Details](#️-methodology--technical-details)
- [🚀 Future Improvements](#-future-improvements)
- [📂 Repository Structure](#-repository-structure)

---

# 📖 Project Background

An India-based e-commerce marketplace sells products across Fashion, Electronics, Home & Kitchen, Sports, Beauty and Books through multiple sales channels. Product returns create refund exposure, operational workload and customer-experience challenges.

Acting as a **Data Analyst**, the objective was to identify where returns are concentrated, understand the main return drivers, and translate the findings into focused actions for **Product / Merchandising and Operations / Logistics teams**.

The analysis focuses on:

**Return Drivers** · **Return Risk** · **Time Patterns** · **Action Prioritization**

---

# 🎯 Business Problem

The business needs to determine **which return problems deserve attention first** rather than treating every return reason equally.

The analysis answers four supporting questions:

1. **Why** are customers returning products most often?
2. **Where** is return risk concentrated across categories, price ranges and products?
3. **When** does return risk increase during the year?
4. **What should the business fix first** based on return volume, return rate and financial exposure?

### Decision Framework

**Business Problem → Decision → North Star Metrics → Analysis → Insights → Recommendations → KPI**

The goal is to move from **return reporting → diagnosis → prioritization → action**.

---

# ⭐ North Star Metrics

| Metric | Definition |
|---|---|
| **Return Rate %** | Returned orders ÷ total orders |
| **Returned Units** | Units with `Return_Quantity > 0` |
| **Refund Amount** | Refund value associated with returned units |
| **Average Return Days** | Average days between delivery and return |

These metrics keep the analysis focused on the scale, concentration, financial exposure and timing of the return problem.

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

<img width="1531" height="751" alt="Power BI data model" src="https://github.com/user-attachments/assets/12c22cb1-ef54-450d-bc6d-69e3a282ca3b" />

> Key modeling decision: `Order_ID` can repeat across product lines, so order-level KPIs use distinct order counts.

---

# 📊 Executive Summary

### **24.03% of orders were returned, and 56.5% of returned units came from just three problems.**

Out of **3,100 orders, 745 were returned**, representing a **24.03% return rate** and **1,113 returned units**. **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** together account for **629 returned units (56.5%)**.

**Fashion has the highest category return rate at 26.15%**, with **88% of Wrong Size returned units concentrated in Fashion**. Return risk also increases from **19.30% in September to 32.16% in December (+12.86 percentage points)**, indicating a clear period for deeper Q4 investigation.

**Decision supported:** start with a focused investigation into **Fashion sizing, product-page experience and damage prevention**, rather than broad interventions across every return reason.

<img width="1387" height="747" alt="Executive dashboard" src="https://github.com/user-attachments/assets/c88e15eb-bc49-44fc-9f08-52a6a8d77458" />

---

# 📈 Insights Deep Dive

## 1. Three return problems drive most of the return burden

<img width="1082" height="486" alt="Return reasons" src="https://github.com/user-attachments/assets/97ed7405-28f4-45d7-9eea-4b8b65aa2684" />

**Finding:** Product Not As Expected (228), Wrong Size (217), and Damaged Product (184) contribute **629 of 1,113 returned units (56.5%)**.

**Why it matters:** more than half of returned units are concentrated in three problems, making them the logical starting point for investigation and prioritization.

**Decision supported:** focus analysis and action planning on these three return problems first.

---

## 2. Fashion is the highest-risk category, with a strong sizing signal

<img width="1117" height="465" alt="Category return rate" src="https://github.com/user-attachments/assets/96c56433-8a69-4c59-8aef-7d2a377e501e" />

**Finding:** **Fashion has the highest return rate at 26.15%**, and **192 of 217 Wrong Size returned units (88%)** come from Fashion.

**Why it matters:** the pattern is highly concentrated, so Fashion is the strongest area for sizing-related investigation.

**Decision supported:** review **size charts, fit guidance and size recommendations** on high-return Fashion pages. The dataset identifies the pattern, but does not prove sizing content is the root cause.

---

## 3. Return risk increases sharply in Q4

<img width="1047" height="417" alt="Monthly return rate" src="https://github.com/user-attachments/assets/4acc5ef3-1ea5-4a50-8413-bcf3a863a304" />

**Finding:** Return rate rises from **19.30% in September to 32.16% in December**, an increase of **12.86 percentage points**.

**Why it matters:** December represents a materially higher-risk period and should not be treated like an average month.

**Decision supported:** investigate Q4 changes in **product mix, promotions, customer behavior and delivery pressure** before choosing a seasonal intervention. These are hypotheses, not proven causal drivers from this dataset.

---

## 4. The ₹1K–5K range has the highest return rate

<img width="1037" height="536" alt="Price range return rate" src="https://github.com/user-attachments/assets/f256e067-f236-4698-a6b3-b269b9688dfe" />

**Finding:** The **₹1K–5K price band has a 23.28% return rate**, compared with **13.65% under ₹1K** — a **9.63 percentage-point difference**.

**Why it matters:** return risk is not simply “higher price = higher returns.”

**Decision supported:** drill down the ₹1K–5K segment by **category and return reason** before selecting an intervention.

---

## 5. Damage returns are concentrated in two categories

**Finding:** Electronics and Home & Kitchen contribute **139 of 184 Damaged Product returned units (~76%)**.

<img width="1272" height="752" alt="Diagnostic dashboard" src="https://github.com/user-attachments/assets/499c4a07-b057-40ff-8bd4-4acaf2d5d348" />

**Why it matters:** the damage problem is concentrated enough to support targeted operational investigation rather than a marketplace-wide packaging change.

**Decision supported:** review **protective packaging and delivery / handling** for Electronics and Home & Kitchen. The dataset supports the concentration pattern, not proof of the exact operational cause.

---

# 💡 Business Recommendations

Recommendations are tied directly to the observed return patterns and framed as **proposed actions**, not realized outcomes.

| Priority | Team / Owner | Evidence | Recommended Action | Expected Impact | KPI to Track |
|---|---|---|---|---|---|
| **1. Fashion sizing** | Product / Merchandising | Fashion return rate **26.15%**; **88%** of Wrong Size units come from Fashion | Improve size charts, fit guidance and size recommendations on high-return Fashion pages. | Reduce Wrong Size returns in the highest-risk category. | Fashion return rate + Wrong Size return rate |
| **2. Product-page experience** | Merchandising / Content | **228** Product Not As Expected returned units | Audit images, descriptions and specifications for SKUs driving expectation-gap returns. | Reduce Product Not As Expected returns on targeted SKUs. | Product Not As Expected return rate |
| **3. Damage prevention** | Operations / Logistics | Electronics + Home & Kitchen account for **~76%** of Damaged Product units | Review protective packaging and delivery / handling for these categories. | Reduce Damaged Product returns and refund exposure. | Damaged Product return rate + refund amount |

### Prioritization Logic

**Return Volume + Return Rate + Financial Exposure → Validate Cause → Recommend Action → Track KPI**

This keeps recommendations evidence-led while avoiding unsupported claims about root cause or savings.

### Caveats & Assumptions

The analysis identifies **patterns and priority areas**, not proven causality. The current data does not include PDP version history, size-chart version, packaging type, carrier / handling details or customer complaint text needed to prove the exact root cause.

No realized savings are claimed because these recommendations have not been implemented and tested.

---

# ⚙️ Methodology & Technical Details

1. **Data quality:** reviewed and validated the raw e-commerce returns dataset.
2. **Return definition:** standardized return reasons and defined returned items using `Return_Quantity > 0`.
3. **Data modeling:** built the Power BI model and supporting dimensions.
4. **North Star metrics:** created measures for return rate, returned units, refund amount and return timing.
5. **Analysis:** compared return patterns by reason, category, price range, month, subcategory and product.
6. **Decision support:** used concentrated patterns and drill-down analysis to prioritize business actions and KPIs.

### Technical Skills

| Area | Skills |
|---|---|
| **Excel** | Data review, validation, filtering, structured analysis |
| **Power BI** | Data modeling, KPI cards, slicers, drill-down analysis, dashboards |
| **DAX** | Return rate, returned units, refund amount, average return days, time-based measures |
| **Business Analytics** | KPI analysis, prioritization, root-cause hypotheses, business storytelling, recommendations |
| **AI-Assisted Analytics** | Claude AI, MCP-based model inspection, DAX development and validation |

---

# 🚀 Future Improvements

- Add packaging, carrier, seller and customer-feedback data to validate root causes.
- Run before-vs-after tests for each intervention and measure KPI movement.
- Add automated weekly return-performance reporting.
- Add drill-through views for priority SKUs and subcategories.

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
