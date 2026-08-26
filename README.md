# AI-Assisted E-commerce Return Analysis
### Power BI · DAX · Excel · Claude AI · MCP

> **Business question:** What is driving e-commerce returns, where is the biggest return exposure, and what should the business fix first?

## Executive Summary

E-commerce returns create refund exposure and operational cost. This project analyzes order and return data to identify the biggest return drivers, understand where return rates are concentrated, and turn those findings into prioritized business actions.

**Headline finding:** Three return reasons — **Product Not As Expected, Wrong Size, and Damaged Product** — account for **629 of 1,113 returned units (56.5%)**.

| KPI | Result |
|---|---:|
| Total Orders | 3,100 |
| Returned Orders | 745 |
| Return Rate | 24.03% |
| Returned Units | 1,113 |
| Refund Amount | ₹44.07L |
| Net Sales | ₹2.14Cr |
| Average Return Days | 13.78 |

**Business implication:** The biggest opportunity is not simply reducing returns overall; it is focusing first on the return problems with the highest combination of volume, rate, and financial exposure.

> *Dashboard screenshots and the final business-report document can be added to this repository.*

---

## Business Problem

The business needs to understand why customers return products and where intervention could reduce return volume and refund exposure.

This analysis answers:

- Which return reasons drive the most returned units?
- Which categories, subcategories, and products have high return rates?
- How does return rate vary by price range and month?
- Which return problems have the largest financial impact?
- What are the most likely root-cause areas based on available evidence?
- Which actions should the business prioritize?
- How should success be measured after the fixes?

---

## Key Findings

### 1. Product Not As Expected is the largest return driver

- **228 returned units** — the highest return-reason volume.
- The problem appears across multiple categories, making product expectation/listing quality an important area to investigate.
- **Root cause:** Listing/PDP or product-content issue is a **hypothesis**, not a proven causal finding.

**Recommended action:** Audit high-return product pages and improve descriptions, images, specifications, and expectation-setting.

**Success KPI:** Product Not As Expected return rate.

### 2. Wrong Size is strongly concentrated in Fashion

- **217 returned units**.
- The subcategory analysis shows a strong concentration of Wrong Size returns in Fashion-related products.
- This makes sizing and fit guidance a practical area for investigation.

**Recommended action:** Improve size charts, fit guidance, and product-specific sizing information.

**Success KPI:** Wrong Size return rate / Fashion return rate.

### 3. Damaged Product is a significant return and refund problem

- **184 returned units**.
- Damage is concentrated in product areas where packaging and handling can reasonably affect outcomes.
- **Root cause:** Packaging/Logistics is a **hypothesis** that requires operational data for validation.

**Recommended action:** Review packaging and delivery-handling processes for high-damage products.

**Success KPI:** Damaged Product return rate and refund amount.

---

## Business Impact

The top three return reasons represent **56.5% of all returned units**. Their listed refund amounts total approximately **₹23.18L**, or about **52.6% of total refunds**.

Refunds of **₹44.07L** represent approximately **20.5% of Net Sales (₹2.14Cr)**, highlighting material financial exposure from returns.

The analysis therefore prioritizes return reduction using three signals:

1. **Return volume** — how many units are affected.
2. **Return rate** — how frequently the problem occurs.
3. **Financial impact** — refund exposure.

---

## Recommendations

| Priority | Problem | Recommended Fix | Success KPI |
|---|---|---|---|
| 1 | Product Not As Expected | Improve high-return product listings and expectation-setting | Product Not As Expected return rate |
| 2 | Wrong Size | Improve size charts and fit guidance | Wrong Size / Fashion return rate |
| 3 | Damaged Product | Review packaging and handling for high-damage products | Damaged Product return rate + refund amount |

Priorities are based on the combination of return volume, return-rate evidence, and financial impact available in the model.

---

## Dashboard & Analysis

The Power BI report follows a business-story sequence rather than presenting charts without context:

**What happened → Where is the problem → What pattern do we see → What might explain it → What should the business do?**

### Executive analysis

- KPI cards for Orders, Returned Orders, Return Rate, Refund Amount, and related performance measures
- Monthly Return Rate trend
- Return Rate by Price Range
- Returned Units by Return Reason
- Return Rate by Category

### Diagnostic analysis

- Subcategory × Return Reason heatmap
- Product-level return detail table
- Returned Units by Channel
- Average Return Days
- Average Discount %

> **Dashboard images will be added to the repository separately.**

---

## Data & Methodology

**Grain:** Order-line level.

The Power BI semantic model follows a **star-schema approach** with `Fact_Orders` as the central fact table and supporting dimensions:

- `Dim_Date`
- `Dim_Product`
- `Dim_Return_Reason`
- `Dim_Channel`
- `Dim_Customer`
- `Dim_Payment_Method`

### Workflow

1. Prepared and cleaned the order/return data.
2. Built the star-schema semantic model.
3. Created DAX measures for return KPIs.
4. Calculated analytical fields such as return days where required.
5. Validated relationships and model logic.
6. Built visuals around the business questions.
7. Analyzed return reasons, products, categories, subcategories, price ranges, discounts, and time trends.
8. Prioritized problems using return volume, return rate, and refund impact.
9. Separated measured facts from root-cause hypotheses.
10. Converted findings into recommendations and success KPIs.

---

## AI-Assisted Power BI + MCP Workflow

Claude Desktop was connected to Power BI through the **Model Context Protocol (MCP)**.

### AI-assisted work

- Semantic-model inspection
- Table and relationship review
- DAX development and debugging
- Calculated-column/measure support
- Model validation
- Business-pattern investigation
- Root-cause hypothesis development
- Recommendation support

### Human-led work

- Data preparation and cleaning
- Visual selection and dashboard design
- Report layout and formatting
- Business storytelling
- Final interpretation and prioritization

This demonstrates a practical workflow where **AI accelerates repetitive analytical/modeling work while the analyst owns the business question, interpretation, and final communication**.

---

## Limitations

This is a portfolio analysis using a sample e-commerce dataset. The model identifies patterns and signals; it does not prove operational causality.

For example, a high `Product Not As Expected` return rate can indicate a listing/content issue, but proving that relationship would require additional evidence such as product-page versions, customer complaint text, packaging information, or controlled testing.

---

## What I Would Build Next

**Automated Weekly Return Report**

A future workflow would monitor:

- Return Rate changes
- Top return reasons
- Refund exposure
- High-risk products/categories
- Month-over-month movement
- Progress against recommendation KPIs

Additional operational data could then be used to validate the root-cause hypotheses and measure the effect of interventions.

---

## Tools & Skills

**Power BI · DAX · Excel · Power Query · Star Schema · Data Modeling · KPI Reporting · Data Visualization · Business Analysis · Claude AI · MCP**

---

## Project Files

The repository is intended to contain the final Power BI report, source data, dashboard screenshots, DAX documentation, and business-analysis documentation as they are added.

Suggested structure:

```text
AI-Assisted-E-commerce-Return-Analysis/
├── README.md
├── powerbi/
├── excel/
├── screenshots/
├── dax/
└── docs/
```

---

## Author

**Jitender Yadav**  
Data Analyst | Power BI | SQL | Excel | Business Intelligence

[GitHub](https://github.com/jitendera-code)
