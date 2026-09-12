# E-commerce Return & Refund Analysis

### Decision-Driven Data Analytics | Power BI · DAX · Excel · Claude AI · MCP

> **Business decision:** Which return problems should the business fix first to reduce customer returns and refund exposure?

## 1. Business Problem

An e-commerce business is experiencing product returns and refunds. The objective is to identify **where the return problem is concentrated, what is driving it, which issue should be addressed first, and how success should be measured**.

This project is therefore designed around a decision—not around building charts for their own sake.

## 2. Decision

**Which return problems should the business fix first to reduce customer returns and refund exposure?**

The analysis follows:

**Business Problem → Decision → North Star Metrics → Analysis → Insight / Why → Recommendation → Expected Impact**

## 3. North Star Metrics

| Metric | Definition | Why it matters |
|---|---|---|
| **Return Rate %** | Returned Orders ÷ Total Orders | Overall return-risk signal |
| **Returned Units** | Sum of returned quantity | Measures return volume |
| **Refund Amount** | Derived refund exposure from returned quantity, paid price and refund deduction | Measures financial impact |
| **Average Return Days** | Return Date − Delivery Date | Shows return timing |

## 4. Executive Summary — What I Found

- **745 of 3,100 orders were returned → 24.03% return rate.**
- **1,113 units were returned.**
- **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** account for **629 returned units / 56.5%** of all returned units.
- Those three priorities represent approximately **₹19.84L / 52.0%** of derived refund exposure.
- **Fashion has the highest returned-unit volume (392)** while **Electronics has the highest derived refund exposure (≈₹15.62L)**.

### What this means

The business does not need to attack every return reason at once. A focused improvement program should begin with the three largest priority problems while using both **return volume and financial exposure** to guide effort.

## 5. Analysis Approach

### Step 1 — Size the problem

Measure orders, returned orders, return rate, returned units, refund exposure and average return days.

### Step 2 — Understand why

Standardize return reasons and identify the biggest drivers.

### Step 3 — Find where

Compare categories, subcategories, products and channels to identify concentration.

### Step 4 — Prioritize

Rank problems using:

**Return volume + return rate + financial exposure**

### Step 5 — Recommend

Convert the priority problems into specific actions with an owner and measurable KPI.

## 6. Key Insights → Business Meaning

### Insight 1 — Three reasons drive more than half of returned units

**Finding:** Product Not As Expected = 228, Wrong Size = 217, Damaged Product = 184.

**Why it matters:** 56.5% of returned units are concentrated in these three issues, so improvement effort can be focused rather than spread across all return reasons.

**Action:** Start with these three problems.

**KPI:** Overall Return Rate and reason-specific return rates.

### Insight 2 — Volume and financial impact are not the same

**Finding:** Fashion leads returned-unit volume, while Electronics leads derived refund exposure.

**Why it matters:** A volume-only ranking can miss financially expensive return problems.

**Action:** Use both returned units and refund exposure when prioritizing.

**KPI:** Refund Amount and refund contribution.

### Insight 3 — Damage is an operational priority to investigate

**Finding:** Damaged Product contributes approximately **₹8.03L** in derived refunds.

**Why it matters:** The issue is financially material enough to justify operational investigation.

**Action:** Audit packaging and delivery/handling for high-damage products.

**KPI:** Damage return rate + Refund Amount.

## 7. Recommendations

| Priority | Evidence | Recommended action | Owner / Stakeholder | Success KPI |
|---|---|---|---|---|
| **1** | Product Not As Expected: 228 units | Improve product-page images, descriptions and specifications | Merchandising / Content | Product Not As Expected rate |
| **2** | Wrong Size: 217 units + Fashion concentration | Improve size charts and fit guidance | Fashion / Merchandising | Wrong Size rate |
| **3** | Damaged Product: 184 units + ≈₹8.03L | Audit packaging and handling | Operations / Logistics | Damage rate + Refund Amount |
| **4** | Quality Issue: 143 units | Build product/vendor quality scorecards | Quality / Vendor Management | Quality return rate |
| **5** | Discount/return relationship requires testing | Review high-discount products with elevated return rates | Pricing / Merchandising | Return rate by discount band |

> Root-cause recommendations are **hypotheses to test**, not proven causal conclusions.

## 8. Expected Business Impact

No intervention has been executed, so this project does **not** claim realized savings.

Instead, it identifies a measurable improvement opportunity:

- Top three return reasons cover **56.5% of returned units**.
- They represent approximately **52.0% of derived refund exposure**.
- Success should be evaluated through reductions in overall return rate, reason-specific return rates, returned units and refund exposure after interventions.

## 9. Dashboard

### Page 1 — Executive Decision View

Answers: **What is happening with returns?**

- North Star KPI cards
- Monthly return trend
- Return reason analysis
- Category performance
- Channel context
- Business filters

### Page 2 — Diagnostic / Action View

Answers: **Where should we investigate next?**

- Average Return Days
- Product performance
- Top category / reason
- Subcategory × Return Reason
- Discount vs Return Risk
- Product detail

### Dashboard Evidence

![Executive Dashboard](screenshots/excuctive_summary.png)

![Diagnostic Dashboard](screenshots/Product_details.png)

## 10. Data Quality & Assumptions

- Dataset covers **1 Jan 2025–31 Dec 2025**.
- Raw dataset contains **4,286 order-line rows**.
- There are **3,100 unique orders**, **104 products** and **850 customers**.
- One row represents a product line within an order.
- `Order_ID` can repeat, so order-level KPIs use `DISTINCTCOUNT(Order_ID)`.
- A returned order is identified using `Return_Quantity > 0`, giving **745 returned orders / 24.03%**.
- Return reasons are standardized before aggregation.
- `Return Days` = `Return_Date − Delivery_Date`.
- Refund Amount is derived from returned quantity, paid price after discount and refund deductions.
- High return percentages on very small product volumes require caution.
- The final period should be checked for completeness before interpreting a decline.

## 11. What the Data Cannot Prove

The dataset identifies patterns and priority areas, but it does not prove operational root causes.

Causal validation would require evidence such as customer feedback, product-page history, packaging/carrier data, seller/vendor information or controlled tests.

## 12. AI-Assisted Workflow

Claude was used as an **analytical assistant** for data exploration, Power BI semantic-model inspection through MCP, DAX development/debugging, validation and hypothesis development.

The analyst remained responsible for:

**Business question → KPI selection → analysis design → interpretation → prioritization → recommendations → final validation.**

## 13. Portfolio Evidence

- [`docs/PORTFOLIO_STORY.md`](docs/PORTFOLIO_STORY.md) — full decision-driven interview story
- [`analysis/ANALYSIS_NOTES.md`](analysis/ANALYSIS_NOTES.md) — analytical evidence
- [`analysis/BUSINESS_RECOMMENDATIONS.md`](analysis/BUSINESS_RECOMMENDATIONS.md) — prioritized actions
- [`data/DATA_DICTIONARY.md`](data/DATA_DICTIONARY.md) — field definitions
- [`docs/PROJECT_SCOPE.md`](docs/PROJECT_SCOPE.md) — business scope and KPI definitions
- [`powerbi/README.md`](powerbi/README.md) — dashboard explanation
- [`powerbi/dax/MEASURES.md`](powerbi/dax/MEASURES.md) — DAX evidence
- [`PowerBI_Claude_MCP_Setup_Guide.pdf`](PowerBI_Claude_MCP_Setup_Guide.pdf) — AI/MCP setup evidence
- [`Return analysis.pbix`](Return%20analysis.pbix) — Power BI report

## 14. Repository Structure

```text
├── README.md
├── .gitignore
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
│   └── Product_details.png
└── docs/
    ├── PORTFOLIO_STORY.md
    ├── PROJECT_SCOPE.md
    └── RESUME_BULLETS.md
```

## 15. Limitations & Next Steps

**Limitations:** no direct customer interview/feedback data; root causes remain hypotheses; historical data alone cannot prove intervention impact.

**Next steps:** add customer feedback, test interventions, measure post-intervention return rates and automate recurring return reporting.

## Interview Summary

> “I started with a business decision rather than a dashboard: which return problems should the business fix first? I defined four North Star metrics, analyzed the size, reasons and concentration of returns, and prioritized issues using return volume, return rate and financial exposure. The top three return reasons represented 56.5% of returned units, so I recommended focused actions for product-page quality, size guidance and packaging/handling, each tied to an owner and KPI. I treated root causes as hypotheses because the data shows patterns but does not prove causality.”

## Author

**Jitender Yadav**  
Data Analyst | SQL | Power BI | Excel | Business Analytics

[GitHub](https://github.com/jitendera-code)
