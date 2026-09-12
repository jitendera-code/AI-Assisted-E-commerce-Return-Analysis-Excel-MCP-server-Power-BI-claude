# E-commerce Product Return Analysis Using AI Assistant

### Decision-Driven Data Analytics | Power BI · DAX · Excel · Claude AI · MCP

## 1. Company Background

An India-based e-commerce marketplace sells products across Fashion, Electronics, Home & Kitchen, Sports, Beauty and Books through multiple sales channels. As the business grows, product returns create refund exposure, operational workload and customer-experience challenges.

The business has detailed order, product, pricing, delivery and return data, but needs a clear analytical view of **why customers return products, where return risk is concentrated, when return risk increases, and which problems should be addressed first**.

### North Star Metrics

| Metric | What it tells the business |
|---|---|
| **Return Rate %** | How frequently orders are being returned |
| **Returned Units** | The scale of the return problem |
| **Refund Amount** | The direct financial exposure from refunds |
| **Average Return Days** | How long customers take to return after delivery |

Supporting decision metrics include **return rate by category, return reason, price range, month and product**.

## 2. Business Problem

As the e-commerce business grows, product returns create pressure on **profitability, operations and customer experience**. However, the business lacks a clear, data-driven view of why customers return products, which product categories and price segments are most exposed, when return risk increases, and which return problems should be addressed first.

Without this visibility, product, merchandising and operations teams may spend resources addressing individual return cases without knowing which issues have the greatest business impact.

The business therefore needs an analytical framework to:

- quantify the major return reasons;
- determine where return risk is highest across products and categories;
- uncover price and time-based return patterns;
- identify the most important areas for investigation; and
- prioritize corrective actions using return volume, return rate and financial exposure.

### Core Business Question

> **Which return problems should the business fix first to reduce customer returns and refund exposure?**

## 3. Executive Summary

### Executive View — What is happening?

- **745 of 3,100 orders were returned → 24.03% return rate.**
- **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** account for **629 of 1,113 returned units → 56.5%** of return volume.
- Return rate rises sharply at year-end, reaching **32.16% in December** versus **19.30% in September** — a **12.86 percentage-point increase**.
- **Fashion has the highest category return rate at 26.15%**, followed by Electronics at **21.74%**.
- The **₹1K–5K price band has the highest return rate at 23.28%**, making it a segment worth deeper category and reason-level investigation.
  <img width="1387" height="747" alt="image" src="https://github.com/user-attachments/assets/c88e15eb-bc49-44fc-9f08-52a6a8d77458" />


### Product / Diagnostic View — Where should the team act?

The diagnostic analysis drills from category and return reason into **subcategory and product-level performance** so the business can identify which products and problem areas need investigation rather than treating every return equally.

### Executive Business Takeaway

**Focus the intervention on the few problems driving most returns, localize those problems to the highest-risk product areas, and measure the impact of targeted fixes.**
<img width="1272" height="752" alt="image" src="https://github.com/user-attachments/assets/499c4a07-b057-40ff-8bd4-4acaf2d5d348" />


> Root-cause statements in this project are **hypotheses**, not proven causes, because the dataset does not contain direct customer feedback, PDP-content history, packaging type or carrier-level evidence.

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
- For the priority return problems, assess whether the likely issue relates to the product, listing/PDP, packaging or logistics.
- Root-cause conclusions are treated as hypotheses because the dataset does not contain direct customer feedback or operational evidence.

### 5.4 Recommendations
- Recommend one specific fix for each priority problem.
- Prioritize fixes using return volume, return rate and financial exposure.

## 6. Key Insights → Business Meaning

### Insight 1 — Returns are concentrated in three major reasons
The top three return reasons account for **56.5% of returned units**. This gives the business a focused starting point instead of trying to address all return reasons simultaneously.
<img width="1082" height="486" alt="image" src="https://github.com/user-attachments/assets/97ed7405-28f4-45d7-9eea-4b8b65aa2684" />


### Insight 2 — Fashion has the highest return risk
Fashion has a **26.15% return rate**, the highest across categories shown. This makes Fashion a priority area for deeper product and sizing investigation.
<img width="1117" height="465" alt="image" src="https://github.com/user-attachments/assets/96c56433-8a69-4c59-8aef-7d2a377e501e" />


### Insight 3 — Year-end return risk increases sharply
The monthly return rate reaches **32.16% in December**, compared with **19.30% in September**. The business should investigate what changes during Q4, including product mix, promotions, customer behavior and delivery pressure. These are investigation hypotheses, not proven causes.
<img width="1047" height="417" alt="image" src="https://github.com/user-attachments/assets/4acc5ef3-1ea5-4a50-8413-bcf3a863a304" />


### Insight 4 — Mid-priced products need investigation
The **₹1K–5K band has the highest return rate at 23.28%**, while products under ₹1K are at **13.65%**. The difference is **9.63 percentage points**, so this segment deserves drill-down by category and return reason.
<img width="1037" height="536" alt="image" src="https://github.com/user-attachments/assets/f256e067-f236-4698-a6b3-b269b9688dfe" />


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

No realized savings are claimed because no intervention has been executed. Any financial improvement should be treated as a **proposed target or scenario** until a fix is implemented and measured.

## 9. What the Data Does Not Support

The dataset can show return patterns and priorities, but it cannot prove the **actual operational root cause** of each return. Claims such as “packaging caused the damage” or “the listing caused the mismatch” require additional evidence.

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
