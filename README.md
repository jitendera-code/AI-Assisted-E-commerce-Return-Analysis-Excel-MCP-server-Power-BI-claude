# E-commerce Product Return Analysis Using AI Assistant

### Decision-Driven Data Analytics | Power BI · DAX · Excel · Claude AI · MCP

## 1. Background & Overview

### Business Context
An India-based e-commerce marketplace sells products across Fashion, Electronics, Home & Kitchen, Sports, Beauty and Books through multiple sales channels. As the business grows, product returns create refund exposure, operational workload and customer-experience challenges.

### Business Problem
The business needs a clear, data-driven view of **why customers return products, where return risk is concentrated, when return risk increases, and which return problems should be addressed first**.

Without this visibility, product, merchandising and operations teams may spend resources addressing individual return cases without knowing which issues have the greatest business impact.

### Core Business Question
> **Which return problems should the business fix first to reduce customer returns and refund exposure?**

### Analytical Approach
**Business Problem → Metrics → Analysis → Insight → Recommendation → Success KPI**

### Key Metrics
- Return Rate %
- Returned Units
- Refund Amount
- Average Return Days
- Category / Product Return Rate
- Return Reason

---

## 2. Data Structure & Data Model Overview

### Dataset Overview

| Area | Details |
|---|---|
| **Period** | 1 Jan 2025 – 31 Dec 2025 |
| **Order-line rows** | 4,286 |
| **Unique Orders** | 3,100 |
| **Products** | 104 |
| **Customers** | 850 |
| **Grain** | One row represents one product line within an order |
| **Return condition** | `Return_Quantity > 0` |

### Key Data Domains

- **Orders:** order date, quantity, price, discount, delivery and return information
- **Customers:** customer segment, city and state
- **Products:** product, category, subcategory and brand
- **Returns:** return flag, return quantity, return date and return reason
- **Financials:** unit price, unit cost, shipping fee and refund deductions

### Power BI Data Model

The Power BI model uses **Fact_Orders** as the central fact table with supporting dimensions for:

- Date
- Product
- Customer
- Channel
- Payment Method
- Return Reason

### Data Model Screenshot

**Add your Power BI Data Model / Relationships screenshot here.**

Suggested image path:
` screenshots/data_model.png `

### Key Modeling Decision

Because `Order_ID` can repeat across product lines, order-level KPIs use **DISTINCTCOUNT(Order_ID)** rather than row counts.

---

## 3. Executive Summary

### Overall Return Performance

- **745 of 3,100 orders were returned → 24.03% return rate.**
- **1,113 returned units** were recorded.
- **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** account for **629 of 1,113 returned units → 56.5%** of return volume.

### Where is the Risk Highest?

- **Fashion:** 26.15% return rate — highest category.
- **Electronics:** 21.74% return rate — second highest category.
- **₹1K–5K:** 23.28% return rate — highest price band.

### When Does Risk Increase?

Return rate rises from **19.30% in September to 32.16% in December**, an increase of **12.86 percentage points**.

### Executive Takeaway

**Returns are concentrated in a small number of return problems and high-risk areas. The business should prioritize targeted interventions instead of treating every return equally.**

> Root-cause conclusions are treated as hypotheses because the available dataset does not contain direct customer feedback, PDP-content history, packaging type or carrier-level evidence.

---

## 4. Insights Deep Dive

### Insight 1 — Three return reasons drive most of the return volume

**Finding:** Product Not As Expected, Wrong Size and Damaged Product represent **56.5% of returned units**.

**Why it matters:** These three problems provide the clearest starting point for intervention because they represent a large share of the return burden.

**Investigation direction:**
- Product Not As Expected → product images, descriptions and specifications
- Wrong Size → size charts and fit guidance
- Damaged Product → packaging and delivery/handling

![Return Reasons](screenshots/return_reasons.png)

### Insight 2 — Fashion has the highest return risk

**Finding:** Fashion records a **26.15% return rate**, the highest category.

**Supporting evidence:** **192 of 217 Wrong Size returned units come from Fashion → 88%**.

**Why it matters:** Fashion is the strongest area for deeper sizing and product-expectation investigation.

![Category Return Rate](screenshots/category_return_rate.png)

### Insight 3 — Return risk increases sharply toward year-end

**Finding:** Return rate increases from **19.30% in September to 32.16% in December**.

**Why it matters:** The business should investigate what changes during Q4, including product mix, promotions, customer behavior and delivery pressure.

These are **investigation hypotheses, not proven causal drivers**.

![Monthly Return Rate](screenshots/monthly_return_rate.png)

### Insight 4 — Mid-priced products have the highest return rate

**Finding:** The **₹1K–5K price band has a 23.28% return rate**, compared with **13.65% for products under ₹1K**.

**Difference:** **9.63 percentage points**.

**Why it matters:** This segment deserves a deeper category-by-return-reason drill-down.

![Price Range Return Rate](screenshots/price_range_return_rate.png)

### Insight 5 — Damaged returns are concentrated in specific categories

**Finding:** Electronics and Home & Kitchen contribute **139 of 184 Damaged Product returned units → ~76%**.

**Why it matters:** Packaging and delivery/handling investigations can be focused on these categories rather than applied broadly across the catalog.

### Diagnostic Analysis

The Power BI diagnostic view drills into **product, subcategory, return reason, discount and return timing** to move from:

**What is happening? → Where should the business investigate? → What should be fixed first?**

---

## 5. Recommendations

| Priority | Return Problem | Recommended Action | Stakeholder | Success KPI |
|---|---|---|---|---|
| **1** | Product Not As Expected | Improve product-page images, descriptions and specifications | Merchandising / Content | Product Not As Expected rate |
| **2** | Wrong Size | Improve size charts and fit guidance, prioritizing Fashion | Fashion / Merchandising | Wrong Size rate + Fashion return rate |
| **3** | Damaged Product | Audit packaging and delivery/handling for high-damage products | Operations / Logistics | Damage return rate + Refund Amount |

### Prioritization Logic

Recommendations are prioritized using:

**Return Volume + Return Rate + Financial Exposure**

The objective is to focus business effort on problems that are large enough to matter and specific enough for a team to act on.

### Validation Before Implementation

The analysis identifies **where to focus**, but operational teams should validate the underlying cause before implementing a permanent change. For example, packaging recommendations should be checked against packaging specifications and carrier/handling records.

### Success Measurement

After implementation, compare:

- overall return rate before vs. after;
- priority return-reason rate before vs. after;
- Fashion return rate before vs. after sizing improvements; and
- refund exposure before vs. after the intervention.

No realized savings are claimed because no intervention has yet been executed.

---

## Tools & AI-Assisted Workflow

**Power BI · DAX · Excel · Claude AI · MCP**

Claude was used as an **analytical assistant** for data exploration, Power BI semantic-model inspection through MCP, DAX development/debugging, validation and hypothesis development.

The analyst remained responsible for the business question, KPI definitions, analysis design, interpretation, prioritization and final validation.

## Portfolio Evidence

- [`docs/PORTFOLIO_STORY.md`](docs/PORTFOLIO_STORY.md) — decision-driven project story
- [`analysis/ANALYSIS_NOTES.md`](analysis/ANALYSIS_NOTES.md) — analytical evidence
- [`analysis/BUSINESS_RECOMMENDATIONS.md`](analysis/BUSINESS_RECOMMENDATIONS.md) — recommended actions
- [`data/DATA_DICTIONARY.md`](data/DATA_DICTIONARY.md) — field definitions
- [`docs/PROJECT_SCOPE.md`](docs/PROJECT_SCOPE.md) — project scope
- [`powerbi/README.md`](powerbi/README.md) — dashboard explanation
- [`powerbi/dax/MEASURES.md`](powerbi/dax/MEASURES.md) — DAX evidence
- [`PowerBI_Claude_MCP_Setup_Guide.pdf`](PowerBI_Claude_MCP_Setup_Guide.pdf) — AI/MCP setup evidence

## Repository Structure

```text
├── README.md
├── PowerBI_Claude_MCP_Setup_Guide.pdf
├── analysis/
│   ├── ANALYSIS_NOTES.md
│   └── BUSINESS_RECOMMENDATIONS.md
├── data/
│   ├── DATA_DICTIONARY.md
│   └── README.md
├── excel/
│   ├── Book1.csv
│   └── README.md
├── powerbi/
│   ├── README.md
│   ├── Return analysis.pbix
│   └── dax/
│       └── MEASURES.md
├── screenshots/
│   ├── README.md
│   ├── excuctive_summary.png
│   ├── Product_details.png
│   ├── return_reasons.png
│   ├── category_return_rate.png
│   ├── monthly_return_rate.png
│   └── price_range_return_rate.png
└── docs/
    ├── PORTFOLIO_STORY.md
    ├── PROJECT_SCOPE.md
    └── RESUME_BULLETS.md
```

## Next Step

**What I'd build next:** automated weekly return reports so the e-commerce team can track return-rate changes, top return reasons, returned units and refund exposure on a recurring basis.

## Interview Summary

> “I treated product returns as a business decision problem rather than only a dashboard exercise. I analyzed return rate, return reasons, category, price range and time patterns, then drilled into product and subcategory performance to identify where the business should focus. The top three return reasons represented 56.5% of returned units. I translated those findings into targeted actions for merchandising and operations, while keeping root-cause statements as hypotheses because the available data cannot prove causality.”

## Author

**Jitender Yadav**  
Data Analyst | SQL | Power BI | Excel | Business Analytics
