# E-commerce Product Return Analysis Using AI Assistant

### Decision-Driven Analytics | Power BI · DAX · Excel · Claude AI · MCP

---

## 📑 Table of Contents

- [📖 Project Background](#-project-background)
- [🎯 Business Problem](#-business-problem)
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

The business needs to answer four decisions:

1. **Why** are customers returning products most often?
2. **Where** is return risk concentrated across categories, price ranges and products?
3. **When** does return risk increase during the year?
4. **What should the business fix first** based on return volume, return rate and financial exposure?

The goal is not simply to report return numbers, but to identify the highest-priority problems that teams can investigate and act on.

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

These findings suggest a focused starting point: **sizing and product-page experience in Fashion, plus packaging / handling for high-damage categories**, rather than broad interventions across every return reason.

<img width="1387" height="747" alt="Executive dashboard" src="https://github.com/user-attachments/assets/c88e15eb-bc49-44fc-9f08-52a6a8d77458" />

---

# 📈 Insights Deep Dive

## 1. Three return problems drive most of the return burden

<img width="1082" height="486" alt="Return reasons" src="https://github.com/user-attachments/assets/97ed7405-28f4-45d7-9eea-4b8b65aa2684" />

**Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** contribute **629 of 1,113 returned units (56.5%)**.

**Why it matters:** the business can concentrate investigation and resources on three problems instead of treating all return reasons equally.

---

## 2. Fashion is the highest-risk category, with a strong sizing signal

<img width="1117" height="465" alt="Category return rate" src="https://github.com/user-attachments/assets/96c56433-8a69-4c59-8aef-7d2a377e501e" />

**Fashion has the highest return rate at 26.15%.** More importantly, **192 of 217 Wrong Size returned units (88%) come from Fashion**.

**Why it matters:** this makes **size charts, fit guidance and product-page information** a logical priority for investigation. The data identifies the pattern, but does not prove that sizing content is the root cause.

---

## 3. Return risk increases sharply in Q4

<img width="1047" height="417" alt="Monthly return rate" src="https://github.com/user-attachments/assets/4acc5ef3-1ea5-4a50-8413-bcf3a863a304" />

Return rate rises from **19.30% in September to 32.16% in December**, an increase of **12.86 percentage points**.

**Why it matters:** Q4 should be investigated for changes in **product mix, promotions, customer behavior and delivery pressure**. These are investigation hypotheses, not proven causal drivers from this dataset.

---

## 4. The ₹1K–5K range has the highest return rate

<img width="1037" height="536" alt="Price range return rate" src="https://github.com/user-attachments/assets/f256e067-f236-4698-a6b3-b269b9688dfe" />

The **₹1K–5K price band has a 23.28% return rate**, compared with **13.65% under ₹1K** — a **9.63 percentage-point difference**.

**Why it matters:** return risk is not simply “higher price = higher returns.” The ₹1K–5K segment deserves drill-down by category and return reason before any intervention is chosen.

---

## 5. Damage returns are concentrated in two categories

Electronics and Home & Kitchen contribute **139 of 184 Damaged Product returned units (~76%)**.

<img width="1272" height="752" alt="Diagnostic dashboard" src="https://github.com/user-attachments/assets/499c4a07-b057-40ff-8bd4-4acaf2d5d348" />

**Why it matters:** this narrows the operational investigation toward **packaging and delivery / handling** for these categories. Again, the dataset supports the concentration pattern, not proof of the exact operational cause.

---

# 💡 Business Recommendations

Recommendations are tied directly to the observed return patterns and framed as **proposed actions**, not realized outcomes.

| Priority | Team / Owner | Recommended Action | Expected Impact | KPI to Track |
|---|---|---|---|---|
| **1. Fashion sizing** | Product / Merchandising | Improve size charts, fit guidance and size recommendations on high-return Fashion pages. | Reduce Wrong Size returns in the highest-risk category. | Fashion return rate + Wrong Size return rate |
| **2. Product-page experience** | Merchandising / Content | Audit images, descriptions and specifications for SKUs driving Product Not As Expected returns. | Reduce expectation-gap returns on targeted SKUs. | Product Not As Expected return rate |
| **3. Damage prevention** | Operations / Logistics | Review protective packaging and delivery / handling for Electronics and Home & Kitchen. | Reduce Damaged Product returns and refund exposure. | Damaged Product return rate + refund amount |

### Prioritization Logic

Prioritize using:

**Return Volume + Return Rate + Financial Exposure**

Then validate the suspected root cause with operational evidence before implementation.

### Caveats & Assumptions

The analysis identifies **patterns and priority areas**, not proven causality. The current data does not include PDP version history, size-chart version, packaging type, carrier / handling details or customer complaint text needed to prove the exact root cause.

No realized savings are claimed because these recommendations have not been implemented and tested.

---

# ⚙️ Methodology & Technical Details

1. Reviewed and validated the raw e-commerce returns dataset.
2. Standardized return reasons and defined returned items using `Return_Quantity > 0`.
3. Built the Power BI model and DAX measures for return rate, returned units, refund amount and return timing.
4. Analyzed return patterns by reason, category, price range, month, subcategory and product.
5. Used drill-down analysis to identify concentrated priority areas.
6. Translated the evidence into business recommendations and measurable KPIs.

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
