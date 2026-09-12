# E-commerce Return & Refund Analysis
### Decision-Driven Data Analytics | Power BI · DAX · Excel · Claude AI · MCP

> **Business decision:** Which return problems should the business fix first to reduce customer returns and refund exposure?

## Executive Summary

This project analyzes 2025 e-commerce order-line data to turn return data into **prioritized business actions**.

**Portfolio story:** Business Problem → Decision → North Star Metrics → Analysis → Insight / Why → Recommendation → Expected Impact

### Decision

The business needs to decide **where to focus first** because not every return problem has the same operational or financial impact.

### North Star Metrics

| Metric | Definition | Why it matters |
|---|---|---|
| **Return Rate %** | Returned Orders ÷ Total Orders | Measures overall return risk |
| **Returned Units** | Sum of returned quantity | Shows problem scale |
| **Refund Amount** | Returned quantity × paid price after discount × refund factor | Quantifies financial exposure |
| **Average Return Days** | Return Date − Delivery Date | Shows return timing |

### Headline Business Insights

- **745 of 3,100 orders were returned → 24.03% return rate.**
- **1,113 units were returned**, making returns a material business problem.
- **Product Not As Expected (228), Wrong Size (217), and Damaged Product (184)** together represent **629 returned units, or 56.5% of all returned units**.
- The three priorities account for approximately **₹19.84L in derived refunds, or 52.0% of total refund exposure**.
- **Fashion has the highest returned-unit volume (392)**, while **Electronics has the highest derived refund exposure (≈₹15.62L)**. Volume and financial priority are therefore not always the same.

### What should the business do first?

**1. Product Not As Expected** — Improve product-page images, descriptions, specifications and expectation-setting for high-return products.

**2. Wrong Size** — Strengthen size charts and fit guidance, especially for Fashion and footwear.

**3. Damaged Product** — Audit packaging and delivery/marketplace handling for products with elevated damage returns.

These are **evidence-based actions to test**, not claims of proven causality.

---

## 1. Business Problem

The business can see that products are being returned, but needs to answer four practical questions:

1. **How large is the return problem?**
2. **Why are customers returning products?**
3. **Where are returns and refund exposure concentrated?**
4. **Which problem should the business fix first?**

The project is designed to answer those questions instead of displaying every available field without prioritization.

---

## 2. Analysis Framework

### Step 1 — Measure the size of the problem

Establish a baseline using Total Orders, Returned Orders, Return Rate %, Returned Units and Refund Amount.

### Step 2 — Explain the “why”

Standardize return reasons and use Pareto analysis to identify the largest return drivers.

### Step 3 — Explain the “where”

Compare category, subcategory, product and channel patterns to locate concentrated return problems.

### Step 4 — Prioritize

Prioritize issues using:

**Return volume + return rate + financial exposure**

### Step 5 — Recommend action

Every recommendation follows:

**Action + Evidence + Owner/Team + Success KPI**

---

## 3. Dataset & Data Model

### Source

The supplied Excel workbook covers **1 Jan 2025–31 Dec 2025** and contains:

- **4,286 order-line rows**
- **3,100 unique orders**
- **104 products**
- **850 customers**

### Data grain

One row represents **one product line inside an order**.

`Order_ID` can repeat because an order may contain multiple product lines. Order-level KPIs therefore use `DISTINCTCOUNT(Order_ID)`.

### Return definition

A returned order is counted as a distinct `Order_ID` where **`Return_Quantity > 0`**.

This produces **745 returned orders / 24.03% return rate** from 3,100 total orders.

The raw workbook contains inconsistent return-flag labels, so returned quantity is used as the analytical return condition after cleaning.

---

## 4. Dashboard

### Page 1 — Executive Decision View

**Question:** What is happening with returns at a business level?

Focuses on:
- Return Rate and returned-order KPIs
- Monthly return trend
- Return-reason distribution / Pareto
- Returns by category
- Sales-channel context
- Date, category and channel filters

### Page 2 — Diagnostic / Action View

**Question:** Where are the problems concentrated and what should be investigated next?

Focuses on:
- Average Return Days
- Product return performance
- Top Return Category
- Top Return Reason
- Subcategory × Return Reason analysis
- Discount vs Return Risk
- Product return-detail table

The second page is intended for diagnosis and action, not simply to repeat executive KPIs.

---

## 5. Key Insights

### Insight 1 — Three return reasons drive more than half of returned units

**Evidence:** Product Not As Expected = 228, Wrong Size = 217, Damaged Product = 184.

Together they account for **629 / 1,113 = 56.5%** of returned units.

**Business meaning:** The company can concentrate improvement efforts on a small set of major problems instead of trying to fix every reason at once.

**Recommendation:** Start with the three highest-impact return problems.

**Success KPI:** Overall Return Rate %, plus reason-specific return rates.

### Insight 2 — Volume priority and financial priority are not identical

**Evidence:** Fashion has the highest returned-unit volume, while Electronics has the highest derived refund exposure.

**Business meaning:** A volume-only ranking can miss financially expensive problems.

**Recommendation:** Combine returned units with refund amount when setting priorities.

**Success KPI:** Refund Amount and refund contribution by category/reason.

### Insight 3 — Fashion requires targeted size/fit investigation

**Evidence:** Wrong Size is one of the largest return reasons and Fashion has the highest returned-unit concentration.

**Business meaning:** Size and fit are a practical investigation area for Fashion/footwear.

**Recommendation:** Improve size charts, fit guidance and product-specific sizing information.

**Success KPI:** Wrong Size return rate and Fashion return rate.

### Insight 4 — Damage returns require operational validation

**Evidence:** Damaged Product contributes approximately **₹8.03L** in derived refunds, the largest refund contribution among individual standardized return reasons.

**Business meaning:** Damage is financially important enough to warrant operational investigation.

**Recommendation:** Audit packaging and handling for high-damage products.

**Success KPI:** Damaged Product return rate and refund amount.

> **Causality guardrail:** The current dataset shows patterns; it does not prove that a specific team, channel, packaging type, product page, or discount caused the return.

---

## 6. Recommendation Matrix

| Priority | Evidence | Action | Owner / stakeholder | Expected impact | KPI |
|---|---|---|---|---|---|
| **1** | Product Not As Expected: 228 units | Improve product images, descriptions and specifications | Merchandising / Content | Reduce expectation-related returns | Product Not As Expected rate |
| **2** | Wrong Size: 217 units + Fashion concentration | Improve size/fit guidance | Fashion / Merchandising | Reduce size-related returns | Wrong Size rate |
| **3** | Damaged Product: 184 units + ≈₹8.03L refunds | Audit packaging and handling | Operations / Logistics / Seller Ops | Reduce damage returns and refund leakage | Damage rate + Refund Amount |
| **4** | Quality Issue: 143 units | Create product/vendor quality scorecards | Quality / Vendor Management | Identify recurring quality problems | Quality return rate |
| **5** | Discount/return relationship needs testing | Review high-discount products with elevated return rates | Pricing / Merchandising | Avoid increasing risk through discounting | Return rate by discount band |

---

## 7. Data Quality & Assumptions

- Return reasons require standardization before aggregation.
- Return flags contain inconsistent labels.
- Order-level KPIs use distinct `Order_ID` because the dataset is at order-line grain.
- `Return Days` is defined as **Return Date − Delivery Date**.
- Refund Amount is derived from returned quantity, paid price after discount, and refund deductions.
- High-return percentages on tiny product volumes should be interpreted cautiously.
- Channel concentration does not prove channel causation.
- Discount/return relationships are associations until validated.
- The final period should be checked for completeness before interpreting a decline in monthly metrics.

---

## 8. What the Data Cannot Prove

This project can identify **where returns are concentrated and which patterns deserve action**, but it cannot prove operational root causes by itself.

Additional evidence would be required for causal conclusions, such as:

- Customer complaint/review text
- Product-page version history
- Packaging type
- Carrier and delivery-handling data
- Seller/vendor information
- Controlled A/B tests

This distinction is intentional: the project demonstrates analytical judgment without overstating correlation as causation.

---

## 9. AI-Assisted Workflow

Claude was used as an **analytical assistant**, not as a substitute for the analyst.

The workflow included:

- Excel data exploration and quality checks
- Power BI semantic-model inspection through MCP
- DAX development and debugging
- Model/measure validation
- Investigation of business patterns
- Support for hypothesis development

The analyst remained responsible for defining the business questions, choosing the North Star metrics, designing the dashboard, interpreting findings, prioritizing recommendations, and final validation.

### Why MCP mattered

MCP acted as the bridge between Claude and the Power BI semantic model, allowing the AI assistant to inspect the actual model structure, tables, fields, relationships and measures used in the analysis.

---

## 10. Technical Evidence

The README presents the decision story first. Technical detail is kept in supporting files:

- [`dax/MEASURES.md`](dax/MEASURES.md) — DAX logic and KPI definitions
- [`docs/ANALYSIS_NOTES.md`](docs/ANALYSIS_NOTES.md) — validated analytical notes
- [`docs/BUSINESS_RECOMMENDATIONS.md`](docs/BUSINESS_RECOMMENDATIONS.md) — recommendation logic
- [`docs/PROJECT_SCOPE.md`](docs/PROJECT_SCOPE.md) — scope and analytical rules
- [`docs/DATA_DICTIONARY.md`](docs/DATA_DICTIONARY.md) — field definitions
- [`PowerBI_Claude_MCP_Setup_Guide.pdf`](PowerBI_Claude_MCP_Setup_Guide.pdf) — MCP setup reference
- [`Return analysis.pbix`](Return%20analysis.pbix) — Power BI report file

---

## 11. Current Repository Structure

```text
├── README.md
├── Book1.csv
├── Return analysis.pbix
├── PowerBI_Claude_MCP_Setup_Guide.pdf
├── dax/
│   └── MEASURES.md
├── docs/
│   ├── ANALYSIS_NOTES.md
│   ├── BUSINESS_RECOMMENDATIONS.md
│   ├── DATA_DICTIONARY.md
│   ├── PROJECT_SCOPE.md
│   └── RESUME_BULLETS.md
└── screenshots/
```

The repository already separates analysis notes, DAX, business recommendations and supporting documentation. The remaining presentation improvement is to move the two dashboard images into a dedicated `screenshots/` folder with recruiter-friendly filenames and embed them in this README.

---

## 12. Limitations & Next Steps

### Limitations

- The dataset does not contain direct customer interview/feedback data.
- Root causes are analytical hypotheses rather than experimentally proven causes.
- Historical data cannot alone prove that a recommendation will reduce returns.

### Next Steps

- Add customer-feedback data.
- Test interventions such as improved size guidance or packaging.
- Track return-rate changes after implementation.
- Automate recurring return reporting.

---

## Portfolio Positioning

This project demonstrates that I can:

- Start with a business problem rather than a dataset alone.
- Define decision-focused KPIs.
- Separate findings from insights.
- Use evidence before making recommendations.
- Distinguish correlation from causation.
- Prioritize actions using return volume, risk and financial impact.
- Communicate recommendations in stakeholder language.
- Use Power BI, DAX, Excel, Claude and MCP as tools supporting the analysis.

## Author

**Jitender Yadav**  
Data Analyst | SQL | Power BI | Excel | Business Analytics

[GitHub](https://github.com/jitendera-code)
