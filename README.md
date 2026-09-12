# E-commerce Return & Refund Analysis
### Decision-Driven Data Analytics | Power BI · DAX · Excel · Claude AI · MCP

> **Business decision:** Which return problems should the business fix first to reduce customer returns and refund exposure?

## Executive Summary

This project analyzes 2025 e-commerce order-line data to turn return data into **prioritized business actions**.

**Portfolio story:** Business Problem → Decision → North Star Metrics → Analysis → Insight / Why → Recommendation → Expected Impact

### North Star Metrics

| Metric | Definition | Why it matters |
|---|---|---|
| **Return Rate %** | Returned Orders ÷ Total Orders | Measures overall return risk |
| **Returned Units** | Sum of returned quantity | Shows problem scale |
| **Refund Amount** | Returned quantity × paid price after discount × refund factor | Quantifies financial exposure |
| **Average Return Days** | Return Date − Delivery Date | Shows return timing |

### Headline Insights

- **745 of 3,100 orders were returned → 24.03% return rate.**
- **1,113 units were returned.**
- **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** represent **629 returned units / 56.5%** of all returned units.
- The three priorities account for approximately **₹19.84L / 52.0%** of derived refund exposure.
- **Fashion has the highest returned-unit volume (392)** while **Electronics has the highest derived refund exposure (≈₹15.62L)**.

### Recommended Priority

1. **Product Not As Expected** → improve product-page images, descriptions and specifications.
2. **Wrong Size** → strengthen size charts and fit guidance, especially for Fashion/footwear.
3. **Damaged Product** → audit packaging and delivery/marketplace handling.

> These are evidence-based actions to test, not claims of proven causality.

---

## 1. Business Problem

The business needs to answer:

1. How large is the return problem?
2. Why are customers returning products?
3. Where are returns and refund exposure concentrated?
4. Which problem should be fixed first?

The goal is not to display every column or chart, but to support a business decision.

## 2. Decision-Driven Analysis

**Step 1 — Size:** establish Total Orders, Returned Orders, Return Rate, Returned Units and Refund Amount.

**Step 2 — Why:** standardize return reasons and identify the largest drivers.

**Step 3 — Where:** compare category, subcategory, product and channel patterns.

**Step 4 — Prioritize:** combine **return volume + return rate + financial exposure**.

**Step 5 — Recommend:** every recommendation uses **Action + Evidence + Owner + Success KPI**.

## 3. Dataset & Data Model

- Period: **1 Jan 2025–31 Dec 2025**
- Raw rows: **4,286**
- Unique orders: **3,100**
- Products: **104**
- Customers: **850**
- Grain: one product line inside an order

`Order_ID` can repeat, so order-level KPIs use `DISTINCTCOUNT(Order_ID)`.

A returned order is a distinct `Order_ID` where **`Return_Quantity > 0`**, producing **745 returned orders / 24.03%**.

## 4. Dashboard

### Page 1 — Executive Decision View

Answers: **What is happening with returns?**

- Return KPIs
- Monthly return trend
- Return reasons / Pareto
- Category performance
- Channel context
- Business filters

### Page 2 — Diagnostic / Action View

Answers: **Where should we investigate next?**

- Average Return Days
- Product return performance
- Top category/reason
- Subcategory × Return Reason
- Discount vs Return Risk
- Product detail

### Dashboard Screenshots

![Executive Dashboard](screenshots/executive_dashboard.png)

![Diagnostic Dashboard](screenshots/diagnostic_dashboard.png)

## 5. Insight → Meaning → Action

### Three reasons drive more than half of returned units

**Evidence:** Product Not As Expected = 228, Wrong Size = 217, Damaged Product = 184.

**Meaning:** A focused improvement program can address a large share of returns without trying to fix every reason simultaneously.

**Action:** Start with these three problems.

**KPI:** Overall Return Rate plus reason-specific return rates.

### Volume and financial priority are different

**Evidence:** Fashion leads returned-unit volume while Electronics leads derived refund exposure.

**Meaning:** A volume-only ranking can miss financially expensive problems.

**Action:** Use returned units and refund exposure together when prioritizing.

**KPI:** Refund Amount and refund contribution.

### Damage returns need operational validation

**Evidence:** Damaged Product contributes approximately **₹8.03L** in derived refunds.

**Meaning:** Damage is financially important enough to investigate.

**Action:** Audit packaging and handling for high-damage products.

**KPI:** Damage return rate + Refund Amount.

## 6. Recommendation Matrix

| Priority | Evidence | Action | Owner | KPI |
|---|---|---|---|---|
| **1** | Product Not As Expected: 228 units | Improve PDP images, descriptions and specifications | Merchandising / Content | Reason return rate |
| **2** | Wrong Size: 217 units + Fashion concentration | Improve size/fit guidance | Fashion / Merchandising | Wrong Size rate |
| **3** | Damaged Product: 184 units + ≈₹8.03L | Audit packaging and handling | Operations / Logistics | Damage rate + Refund Amount |
| **4** | Quality Issue: 143 units | Build vendor/product quality scorecards | Quality / Vendor Management | Quality return rate |
| **5** | Discount/return relationship needs testing | Review high-discount products with elevated returns | Pricing / Merchandising | Return rate by discount band |

## 7. Data Quality & Causality

- Return reasons are standardized before aggregation.
- Return flags contain inconsistent labels.
- Order-level KPIs use distinct `Order_ID`.
- `Return Days` = Return Date − Delivery Date.
- Refund Amount is derived from returned quantity, paid price after discount and refund deductions.
- High return percentages on tiny product volumes require caution.
- Channel concentration and discount relationships do **not** prove causation.
- The final period should be checked for completeness before interpreting a decline.

## 8. What the Data Cannot Prove

The dataset identifies patterns and priority areas, but does not prove operational root causes.

Causal validation would require evidence such as customer feedback, product-page history, packaging/carrier data, seller information or controlled tests.

## 9. AI-Assisted Workflow

Claude was used as an **analytical assistant**, not a substitute for the analyst, for data exploration, Power BI semantic-model inspection through MCP, DAX development/debugging, validation and hypothesis development.

The analyst remained responsible for business questions, KPI selection, dashboard design, interpretation, prioritization and final validation.

## 10. Technical Evidence

- [`analysis/ANALYSIS_NOTES.md`](analysis/ANALYSIS_NOTES.md)
- [`analysis/BUSINESS_RECOMMENDATIONS.md`](analysis/BUSINESS_RECOMMENDATIONS.md)
- [`data/DATA_DICTIONARY.md`](data/DATA_DICTIONARY.md)
- [`docs/PROJECT_SCOPE.md`](docs/PROJECT_SCOPE.md)
- [`powerbi/README.md`](powerbi/README.md)
- [`powerbi/dax/MEASURES.md`](powerbi/dax/MEASURES.md)
- [`PowerBI_Claude_MCP_Setup_Guide.pdf`](PowerBI_Claude_MCP_Setup_Guide.pdf)
- [`Return analysis.pbix`](Return%20analysis.pbix)

## 11. Repository Structure

```text
├── README.md
├── .gitignore
├── Book1.csv
├── Return analysis.pbix
├── PowerBI_Claude_MCP_Setup_Guide.pdf
├── data/
│   ├── README.md
│   └── DATA_DICTIONARY.md
├── analysis/
│   ├── ANALYSIS_NOTES.md
│   └── BUSINESS_RECOMMENDATIONS.md
├── powerbi/
│   ├── README.md
│   └── dax/
│       └── MEASURES.md
├── excel/
│   └── README.md
├── screenshots/
│   └── README.md
└── docs/
    └── PROJECT_SCOPE.md
```

## 12. Limitations & Next Steps

**Limitations:** no direct customer interview/feedback data; root causes remain hypotheses; historical data alone cannot prove intervention impact.

**Next steps:** add customer feedback, test interventions, measure post-intervention return rates and automate recurring return reporting.

## Portfolio Positioning

This project demonstrates that I can start with a business problem, define decision-focused KPIs, distinguish findings from insights, use evidence before recommendations, separate correlation from causation, prioritize actions and communicate in stakeholder language.

## Author

**Jitender Yadav**  
Data Analyst | SQL | Power BI | Excel | Business Analytics

[GitHub](https://github.com/jitendera-code)
