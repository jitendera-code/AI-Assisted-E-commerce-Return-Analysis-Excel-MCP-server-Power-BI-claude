# E-commerce Product Return Analysis Using AI Assistant

### Decision-Driven Data Analytics | Power BI · DAX · Excel · Claude AI · MCP

## 1. Company Background

**Hypothetical company: ShopKart — an India-focused e-commerce marketplace.**

ShopKart sells products across Fashion, Electronics, Home & Kitchen, Sports, Beauty and Books through multiple sales channels. The business wants to reduce product returns because high returns create refund exposure, operational workload and poor customer experience.

### North Star Metrics

| Metric | What it tells the business |
|---|---|
| **Return Rate %** | How frequently orders are being returned |
| **Returned Units** | The scale of the return problem |
| **Refund Amount** | The direct financial exposure from refunds |
| **Average Return Days** | How long customers take to return after delivery |

Supporting decision metrics include **return rate by category, return reason, price range, month and product**.

> **Important:** ShopKart is a hypothetical company created for this portfolio project. The analysis uses the supplied e-commerce dataset.

## 2. Business Problem

ShopKart is facing a **24.03% order return rate**. The business can see that customers are returning products, but the management question is more specific:

> **Which return problems are driving the largest return burden, where are they concentrated, and which fixes should the business prioritize first?**

The business needs to:

- quantify return reasons and returned units;
- identify high-return product categories;
- identify price and monthly patterns;
- locate high-impact product/problem combinations;
- develop evidence-based root-cause hypotheses; and
- recommend specific fixes with measurable success KPIs.

## 3. Executive Summary

### Executive View — What is happening?

- **745 of 3,100 orders were returned → 24.03% return rate.**
- **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** account for **629 of 1,113 returned units → 56.5%** of return volume.
- Return rate is relatively stable through most of the year, but rises sharply at year-end, reaching **32.16% in December** versus **19.30% in September** — a **12.86 percentage-point increase**.
- **Fashion has the highest category return rate at 26.15%**, followed by Electronics at **21.74%**.
- The **₹1K–5K price band has the highest return rate at 23.28%**, indicating a segment worth deeper category/reason investigation.

### Product / Diagnostic View — Where should the team act?

The diagnostic analysis drills from category and return reason into **subcategory and product-level performance** so the business can identify which products need investigation rather than treating every return equally.

### Executive Business Takeaway

**Focus the intervention on the few problems driving most returns, localize those problems to the highest-risk product areas, and measure the impact of targeted fixes.**

> Root-cause statements in this project are **hypotheses**, not proven causes, because the dataset does not contain direct customer feedback, PDP-content history, packaging type, or carrier-level evidence.

## 4. Decision

**Which return problems should the business fix first to reduce customer returns and refund exposure?**

The analysis follows:

**Business Problem → Decision → Metrics → Analysis → Insight / Why → Recommendation → Success KPI**

## 5. Analysis Requirements

### 5.1 Categorisation
- Group return reasons into clear categories.
- Count returned units for each category.

### 5.2 Pattern Analysis
- Identify product categories/types with the highest return rate.
- Identify the most common return reason.
- Analyze return patterns by price range.
- Analyze monthly/time-based return patterns.

### 5.3 Root-Cause Assessment
- For the priority return problems, assess whether the likely issue relates to the product, listing/PDP, packaging, or logistics.
- Root-cause conclusions are treated as hypotheses because the dataset does not contain direct customer feedback or operational evidence.

### 5.4 Recommendations
- Recommend one specific fix for each priority problem.
- Prioritize fixes using return volume, return rate, and financial exposure.

## 6. Key Insights → Business Meaning

### Insight 1 — Returns are concentrated in three major reasons
The top three return reasons account for **56.5% of returned units**. This gives the business a focused starting point instead of trying to address all return reasons simultaneously.

### Insight 2 — Fashion has the highest return risk
Fashion has a **26.15% return rate**, the highest across categories shown. This makes Fashion a priority area for deeper product and sizing investigation.

### Insight 3 — Year-end return risk increases sharply
The monthly return rate reaches **32.16% in December**, compared with **19.30% in September**. The business should investigate what changes during Q4, including product mix, promotions, customer behavior and delivery pressure.

### Insight 4 — Mid-priced products need investigation
The **₹1K–5K band has the highest return rate at 23.28%**, while products under ₹1K are at **13.65%**. The difference is **9.63 percentage points**, so this segment deserves drill-down by category and return reason.

## 7. Recommendations

| Priority | Problem | Specific fix | Stakeholder | Success KPI |
|---|---|---|---|---|
| 1 | Product Not As Expected | Improve product-page images, descriptions and specifications | Merchandising / Content | Product Not As Expected rate |
| 2 | Wrong Size | Improve size charts and fit guidance for Fashion | Fashion / Merchandising | Wrong Size rate + Fashion return rate |
| 3 | Damaged Product | Audit packaging and delivery/handling for high-damage products | Operations / Logistics | Damage return rate + Refund Amount |

These fixes focus on the return reasons responsible for the largest concentration of returned units. Financial exposure is used as an additional prioritization lens.

## 8. Business Impact & Prioritization

- **24.03%** overall order return rate.
- **629 returned units / 56.5%** of all returned units come from the top three return reasons.
- **Fashion = 26.15%** return rate, the highest category in the analysis.
- **December = 32.16%** return rate, the highest month shown.
- **₹1K–5K = 23.28%** return rate, the highest price band shown.

The project does **not** claim realized savings because no intervention has been executed. Monthly refund exposure or savings should only be estimated after agreeing on the exact refund basis and validating the model figures.

## 9. What the Data Does Not Support

The dataset can show return patterns and priorities, but it cannot prove the **actual** operational root cause of each return. Claims such as “packaging caused the damage” or “the listing caused the mismatch” require additional evidence.

The project therefore uses **evidence-based root-cause hypotheses** and recommends what the business should validate next.

## 10. Dashboard

### Page 1 — Executive Decision View

Answers: **What is happening with returns?**

- North Star KPI cards
- Monthly return-rate trend
- Return reason analysis
- Category return rate
- Price-range return rate
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

## 11. Data Quality & Assumptions

- Dataset covers **1 Jan 2025–31 Dec 2025**.
- Raw dataset contains **4,286 order-line rows**.
- There are **3,100 unique orders**, **104 products** and **850 customers**.
- One row represents a product line within an order.
- `Order_ID` can repeat, so order-level KPIs use `DISTINCTCOUNT(Order_ID)`.
- A returned order is identified using `Return_Quantity > 0`, giving **745 returned orders / 24.03%**.
- Return reasons are standardized before aggregation.
- `Return Days` = `Return_Date − Delivery_Date`.
- Refund Amount is derived from returned quantity, paid price after discount and refund deductions.

## 12. AI-Assisted Workflow

Claude was used as an **analytical assistant** for data exploration, Power BI semantic-model inspection through MCP, DAX development/debugging, validation and hypothesis development.

The analyst remained responsible for the business question, KPI definitions, analysis design, interpretation, prioritization and final validation.

## 13. Portfolio Evidence

- [`docs/PORTFOLIO_STORY.md`](docs/PORTFOLIO_STORY.md) — decision-driven project story
- [`analysis/ANALYSIS_NOTES.md`](analysis/ANALYSIS_NOTES.md) — analytical evidence
- [`analysis/BUSINESS_RECOMMENDATIONS.md`](analysis/BUSINESS_RECOMMENDATIONS.md) — recommended actions
- [`data/DATA_DICTIONARY.md`](data/DATA_DICTIONARY.md) — field definitions
- [`docs/PROJECT_SCOPE.md`](docs/PROJECT_SCOPE.md) — project scope
- [`powerbi/README.md`](powerbi/README.md) — dashboard explanation
- [`powerbi/dax/MEASURES.md`](powerbi/dax/MEASURES.md) — DAX evidence
- [`PowerBI_Claude_MCP_Setup_Guide.pdf`](PowerBI_Claude_MCP_Setup_Guide.pdf) — AI/MCP setup evidence

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

## 15. Next Step

**What I'd build next:** automated weekly return reports so the e-commerce team can track return-rate changes, top return reasons, returned units and refund exposure on a recurring basis.

## Interview Summary

> “I treated product returns as a business decision problem rather than only a dashboard exercise. I categorized return reasons, analyzed return rate by product category, price range and time, identified the biggest return drivers, and used returned units, return rate and financial exposure to prioritize fixes. The top three return reasons represented 56.5% of returned units. I then translated those findings into targeted actions for merchandising and operations, while keeping root-cause statements as hypotheses because the available data cannot prove causality.”

## Author

**Jitender Yadav**  
Data Analyst | SQL | Power BI | Excel | Business Analytics
