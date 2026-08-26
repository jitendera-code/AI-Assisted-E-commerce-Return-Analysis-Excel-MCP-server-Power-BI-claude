# AI-Assisted E-commerce Return Analysis

### Power BI · DAX · Excel · Claude AI · MCP

An end-to-end e-commerce return analysis project that identifies the main drivers of product returns, measures financial impact, investigates patterns, and translates the findings into actionable business recommendations.

The project also demonstrates an **AI-assisted Power BI workflow**, using Claude Desktop connected to Power BI through the **Model Context Protocol (MCP)** to inspect the semantic model, work with DAX, validate model logic, and support analysis.

---

## 🎯 Business Problem

Product returns create revenue leakage and operational costs for e-commerce businesses. This project answers:

- Which return reasons drive the most returned units?
- Which categories, subcategories, and products have high return rates?
- How does return rate vary by price range and month?
- Which return problems have the largest financial impact?
- What are the likely root-cause areas?
- Which actions should the business prioritize to reduce returns?

---

## 📊 Executive Snapshot

| KPI | Result |
|---|---:|
| Total Orders | 3,100 |
| Returned Orders | 745 |
| Return Rate | 24.03% |
| Refund Amount | $4.41M |
| Average Return Days | 13.78 |

### Top Return Reasons

| Return Reason | Returned Units |
|---|---:|
| Product Not As Expected | 228 |
| Wrong Size | 217 |
| Damaged Product | 184 |

These metrics are from the Power BI model and are used to frame the business investigation.

---

## 🔎 Key Business Findings

### 1. Product Not As Expected

- Highest return volume at **228 returned units**.
- Indicates a major opportunity to investigate product expectations, descriptions, imagery, specifications, or product experience.
- **Root cause is a hypothesis**, not proven by the available data.

**Recommended action:** Audit high-return product listings and improve product descriptions, images, specifications, and expectation-setting.

**KPI:** Product Not As Expected return rate.

### 2. Wrong Size

- **217 returned units**.
- Strongly visible in the product/subcategory analysis, particularly around Fashion-related products.

**Recommended action:** Improve size charts, fit guidance, and product-specific sizing information.

**KPI:** Wrong Size return rate / Fashion return rate.

### 3. Damaged Product

- **184 returned units**.
- Represents an important financial-impact area because refunds associated with damaged products can be significant.

**Recommended action:** Investigate packaging and delivery-handling processes for products with high damage returns.

**KPI:** Damaged Product return rate and refund amount.

> **Important:** The dashboard identifies patterns and signals. It does not prove operational causality because fields such as packaging type, carrier, listing version, and customer complaint text are not directly available in the model.

---

## 🏗️ Data Model

The Power BI semantic model follows a **star-schema approach** with `Fact_Orders` as the central fact table and supporting dimensions including:

- `Dim_Date`
- `Dim_Product`
- `Dim_Return_Reason`
- `Dim_Channel`
- `Dim_Customer`
- `Dim_Payment_Method`

The model was reviewed for table roles, relationships, cardinality, and filter logic before the final dashboard was completed.

---

## 📈 Power BI Dashboard

The report focuses on business impact rather than simply displaying charts.

### Executive KPIs

- Total Orders
- Returned Orders
- Return Rate %
- Refund Amount
- Average Return Days
- Month-over-Month performance

### Diagnostic Analysis

- Returned Units by Return Reason
- Return Rate % by Category
- Return Rate % by Price Range
- Monthly Return Rate trend
- Subcategory × Return Reason heatmap
- Product-level return detail table
- Average Discount %
- Product-level return metrics

### Business Storytelling

The dashboard is designed to move from:

**What happened → Where is the problem → Why might it be happening → What should the business do?**

---

## 🤖 AI-Assisted Power BI + MCP Workflow

Claude Desktop was connected to the Power BI model through the **Model Context Protocol (MCP)**.

### MCP was used for

- Inspecting tables and columns
- Reviewing existing measures
- Checking relationships
- Creating and debugging DAX measures
- Creating calculated columns/tables where required
- Running DAX/data queries
- Validating the semantic model
- Supporting business-pattern investigation
- Helping translate analysis into recommendations

### Work completed manually in Power BI

- Data import and Power Query preparation
- Visual creation
- Chart selection
- Dashboard layout
- Formatting and styling
- Slicers and report interaction
- Final business storytelling

This created a practical workflow where **AI assisted with model/logic work while the final dashboard design and business interpretation remained human-led**.

---

## 🛠️ Tools & Skills

**Power BI** · **DAX** · **Excel** · **Power Query** · **Star Schema** · **Data Modeling** · **KPI Development** · **Data Visualization** · **Business Analysis** · **Claude AI** · **MCP**

---

## 🔬 Analysis Methodology

1. Prepared and cleaned the e-commerce order/return data.
2. Built a star-schema semantic model.
3. Created DAX measures for return KPIs.
4. Calculated return days and other required analytical fields.
5. Validated relationships and model logic.
6. Built Power BI visuals around business questions.
7. Analyzed return reasons, products, categories, subcategories, price ranges, and time trends.
8. Combined return volume, return rate, and financial impact to prioritize problems.
9. Separated **data-supported facts** from **root-cause hypotheses**.
10. Recommended actions with measurable success KPIs.

---

## 📁 Repository Structure

```text
AI-Assisted-E-commerce-Return-Analysis/
│
├── README.md
├── powerbi/
│   └── Return_Analysis.pbix
├── excel/
│   └── source_data.xlsx
├── screenshots/
│   ├── executive_dashboard.png
│   ├── return_reason_analysis.png
│   ├── product_analysis.png
│   └── data_model.png
├── dax/
│   └── measures.md
└── docs/
    └── AI_MCP_Workflow.md
```

---

## 💼 Business Impact Framework

The recommendations are prioritized using three signals where available:

1. **Return volume** — how many units are being returned.
2. **Return rate** — how frequently the problem occurs relative to orders.
3. **Financial impact** — refund amount and related value leakage.

The objective is not simply to find the most common return reason, but to identify the return problems where intervention can potentially create the largest business benefit.

---

## ⚠️ Data & Causality Note

This is a portfolio analysis using a sample e-commerce dataset. Findings should be treated as analytical signals rather than proof of operational causality.

For example, a high `Product Not As Expected` return rate can indicate a listing/content problem, but additional data would be required to prove that hypothesis.

---

## 🚀 Future Improvements

- Customer review and complaint-text analysis
- Carrier-level return analysis
- Packaging-level damage analysis
- Product listing/version analysis
- Automated return monitoring
- A/B testing of recommended interventions
- Pre/post measurement of return-rate reduction

---

## 👤 Author

**Jitender Yadav**

GitHub: https://github.com/jitendera-code
