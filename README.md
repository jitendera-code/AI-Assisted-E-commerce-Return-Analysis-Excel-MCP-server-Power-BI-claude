# E-commerce Return & Refund Analysis
### Power BI · DAX · Excel · Business Analytics

> **Business question:** Why are customers returning products, where is refund exposure concentrated, and what should the business fix first?

## Executive Summary

This project analyzes **2025 e-commerce order-line data** to move from *"returns happened"* to *"why returns happened and what to fix first."* The analysis combines return volume, return rate, refund exposure, product/category patterns, sales channels, return timing, and diagnostic relationships.

The project follows a business-first portfolio framework: **Business Problem → KPI framing → Data Model → Executive Findings → Product Diagnostics → Business Recommendations.**

### Headline Findings

- **745 returned orders** from **3,100 total orders** → **24.03% return rate**.
- **1,113 units** were returned across **104 products**.
- **₹38.17L** of refund amount is derived from returned quantity, paid price after discount, and refund deductions.
- **Product Not As Expected (228 units), Wrong Size (217), and Damaged Product (184)** together account for **629 returned units (56.5%)**.
- **Fashion** contributes the highest returned-unit volume at **392 units**.
- **Mobile App** has the highest returned-unit concentration at **385 units**.
- Average return time is approximately **14.9 days** from delivery to return.

### What the business should do first

1. Improve product images, descriptions, specifications, and expectation-setting for high-return products.
2. Strengthen size charts and fit guidance for Fashion and footwear.
3. Audit packaging and marketplace handling for products with high damage returns.
4. Build vendor/product-quality scorecards using returned units and refund amount.
5. Avoid deep discounts on products already showing elevated return risk.

> **Important:** Root-cause statements are treated as hypotheses unless the dataset directly proves them. Operational data such as customer complaint text, packaging type, carrier, product-page versions, and controlled experiments would be required to establish causality.

---

## 1. Business Problem

The business sees returns, but cannot explain them fast enough.

The analysis addresses four practical problems:

- **Refund leakage:** Money is leaving through refunds, but the business needs to isolate the category, reason, product, and channel behind it.
- **Messy return reasons:** Return reasons contain inconsistent casing/labels and need standardization before analysis.
- **Hidden root causes:** Category-level summaries can hide important subcategory × return-reason combinations.
- **Discount risk:** The analysis tests whether higher discounts are associated with higher return risk rather than assuming a causal relationship.

**Dashboard objective:** move from **“returns happened”** to **“why returns happened and what to fix first.”**

---

## 2. KPI Framework

Every KPI is tied to a decision question.

| KPI | Business question | Decision lens |
|---|---|---|
| Total Orders | How large is the order base? | Business volume |
| Returned Orders | How many orders came back? | Return exposure |
| Return Rate % | What share of orders were returned? | Operational risk |
| Refund Amount | How much money was refunded? | Financial leakage |
| Average Return Days | How quickly are items returned after delivery? | Customer behavior |
| Products Returned | How many products were affected? | Product spread |
| Top Return Category | Which category creates the most returned units? | Priority area |
| Top Return Reason | Which return reason is biggest? | Action trigger |

The dashboard deliberately focuses on decision-useful return KPIs rather than displaying numbers without an action lens.

---

## 3. Dataset & Data Model

### Source dataset

The supplied Excel workbook covers **1 Jan 2025–31 Dec 2025** and contains **4,286 order-line rows**, **3,100 unique orders**, **104 products**, and **850 customers**.

**Raw grain:** one row represents one product line inside an order.

### Star schema

`Fact_Orders` is the central fact table with dimensions for:

- `Dim_Date`
- `Dim_Product`
- `Dim_Customer`
- `Dim_Channel`
- `Dim_Payment_Method`
- `Dim_Return_Reason`

The source workbook intentionally leaves calculated business metrics to Power BI. Derived fields/measures include Refund Amount, Return Days, Return Rate, MoM indicators, Pareto values, Products Returned, Top Return Category, Top Return Reason, and Category Refund Contribution %.

### Return-order definition

For reproducibility, a **returned order** is a distinct `Order_ID` with **`Return_Quantity > 0`**. This produces the presentation's **745 returned orders / 24.03% return rate** from 3,100 total orders.

The raw workbook contains inconsistent `Return_Flag` labels (`Y`, `Yes`, `Returned`, `N`, `No`, `Not Returned`). Therefore, the analytical return condition should be based on the actual returned quantity after cleaning rather than relying only on the raw flag text.

--- <img width="1917" height="1007" alt="image" src="https://github.com/user-attachments/assets/3dec4a3e-dfc2-4686-b14e-c5864b240946" />



## 4. Executive Dashboard — Page 1

The first dashboard page answers: **What is happening with returns at a business level?**

### Included analysis

- Total Orders
- Returned Orders
- Return Rate %
- Refund Amount
- Monthly Return Trend
- Return Reason Pareto
- Returns by Category
- Returned Units by Sales Channel

### Slicers

- Date Range
- Category
- Sales Channel
- Reset Filters

The monthly trend is used to detect spikes and seasonality, while Pareto analysis identifies the small number of return reasons contributing most returned units.

--- <img width="1282" height="745" alt="image" src="https://github.com/user-attachments/assets/4c0b7f68-265b-475b-b3fd-f70e9214c94a" />



## 5. Product Diagnostics — Page 2

The second dashboard page answers: **Where are the return problems concentrated and what patterns should be investigated?**

### Diagnostic KPIs

- **Average Return Days:** 14.9 days
- **Products Returned:** 104 unique products
- **Top Category:** Fashion
- **Top Return Reason:** Product Not As Expected

### Diagnostic visuals

- Subcategory × Return Reason heatmap
- Discount vs Return Risk scatter plot
- Product Return Details table

The product table includes product, subcategory, orders, returned units, return rate, refund amount, average return days, and average discount.

### Slicers

- Date Range
- Category
- Sales Channel
- Return Reason
- Reset Filters

The project intentionally does **not** use a Top 10 Returned Products visual; product-level risk is investigated through the detailed table and diagnostic relationships instead.

---<img width="1327" height="752" alt="image" src="https://github.com/user-attachments/assets/a42c4c79-dd8e-4d0a-8373-7911710b2867" />


## 6. Key Findings

### 6.1 Product Not As Expected — largest return driver

**228 returned units** make this the largest standardized return-reason group.

**Business interpretation:** Product expectations, listing content, imagery, specifications, or product experience should be investigated.

**Action:** Audit high-return product pages and improve product information and expectation-setting.

**Success KPI:** Product Not As Expected return rate.

### 6.2 Wrong Size — major Fashion/footwear issue

**217 returned units** are attributed to Wrong Size.

**Business interpretation:** Sizing and fit guidance are important areas for investigation, particularly for Fashion and footwear.

**Action:** Improve size charts, fit guidance, and product-specific sizing information.

**Success KPI:** Wrong Size return rate / Fashion return rate.

### 6.3 Damaged Product — high financial exposure

**184 returned units** are attributed to Damaged Product. The reason contributes approximately **₹8.03L** in derived refunds, the largest refund amount among individual return reasons.

**Business interpretation:** Packaging and handling are reasonable operational hypotheses, but the dataset does not contain enough evidence to prove causality.

**Action:** Audit packaging and marketplace/delivery-handling quality for high-damage products.

**Success KPI:** Damaged Product return rate + refund amount.

### 6.4 Category concentration

Returned units are concentrated in:

| Category | Returned Units | Share of Returned Units |
|---|---:|---:|
| Fashion | 392 | 35.2% |
| Electronics | 277 | 24.9% |
| Home & Kitchen | 177 | 15.9% |
| Sports | 102 | 9.2% |
| Beauty | 95 | 8.5% |
| Books | 70 | 6.3% |

Fashion has the highest returned-unit volume, while Electronics has the highest derived refund exposure at approximately **₹15.62L**.

### 6.5 Sales-channel concentration

Returned units by channel:

| Channel | Returned Units | Share |
|---|---:|---:|
| Mobile App | 385 | 34.6% |
| Marketplace | 323 | 29.0% |
| Website | 315 | 28.3% |
| Offline Store | 90 | 8.1% |

This identifies where return volume is concentrated; it does not by itself prove that a channel causes more returns.

---

## 7. Business Impact & Prioritization

The top three return reasons account for **629 / 1,113 returned units = 56.5%**.

Their derived refunds total approximately **₹19.84L**, or **52.0% of total refund amount**.

This supports a practical prioritization rule:

> **Fix causes that combine high returned units and high refund amount first.**

The project therefore evaluates problems using three signals:

1. **Return volume** — how many units are affected.
2. **Return rate** — how frequently the problem occurs relative to orders.
3. **Financial impact** — refund exposure.

---

## 8. Analytical Techniques

### MoM indicators

Previous-month calculations and arrow indicators are used below KPI cards to communicate movement quickly.

### Pareto analysis

Return reasons are ranked and cumulative returned-unit percentages are calculated to identify the vital few causes.

### Heatmap logic

A Subcategory × Return Reason matrix uses color intensity to reveal concentrated problem combinations.

### Risk colouring

Product return rates can be compared with a benchmark and represented as risk levels in the scatter analysis.

### Dynamic text KPIs

TOPN-style measures dynamically identify the Top Return Category and Top Return Reason.

### Volume filters

Low-volume products should be excluded from risk visuals where appropriate so that a tiny number of returns does not create misleading “high-risk” signals.

---

## 9. Business Recommendations

| Priority | Finding | Recommended action | Success KPI |
|---|---|---|---|
| 1 | Product Not As Expected | Improve product images, descriptions, specifications and expectation-setting | Product Not As Expected return rate |
| 2 | Wrong Size | Add size guidance and a return-feedback loop for Fashion/footwear | Wrong Size / Fashion return rate |
| 3 | Damaged Product | Audit packaging and marketplace handling quality | Damaged return rate + refund amount |
| 4 | Quality Issue | Create vendor/product-quality scorecards using returned units and refund amount | Quality Issue rate + refund amount |
| 5 | Discount Risk | Avoid deep discounts on products already showing elevated return risk | Return rate by discount band |

These recommendations are **actions to test**, not claims of proven causality.

---

## 10. Limitations

This is a portfolio analysis using a sample e-commerce dataset.

The available data can identify patterns, but cannot prove operational root causes. Additional evidence would be required for causal conclusions, including:

- Customer complaint/review text
- Product-page versions
- Packaging type
- Carrier and delivery-handling information
- Seller/vendor information
- Controlled A/B tests

The final dashboard scope also intentionally avoids a Net Sales KPI and a Top 10 Returned Products visual, following the supplied project presentation.

---

## 11. AI-Assisted Power BI Workflow

The repository can document the AI-assisted workflow separately from the business analysis.

Claude Desktop + Power BI MCP can support:

- Semantic-model inspection
- Table and relationship review
- DAX development/debugging
- Model validation
- Business-pattern investigation
- Hypothesis development

The analyst remains responsible for:

- Data preparation
- Business-question definition
- Visual selection and dashboard design
- Interpretation
- Recommendations
- Final validation

The portfolio story should therefore lead with **business value**, not with AI tooling.

---

## 12. Repository Structure

```text
AI-Assisted-E-commerce-Return-Analysis-Excel-MCP-server-Power-BI-claude/
│
├── README.md
├── Book1.csv
│
├── powerbi/
│   └── README.md
│
├── excel/
│   └── README.md
│
├── dax/
│   └── MEASURES.md
│
├── docs/
│   ├── BUSINESS_RECOMMENDATIONS.md
│   ├── DATA_DICTIONARY.md
│   ├── ANALYSIS_NOTES.md
│   ├── PROJECT_SCOPE.md
│   └── RESUME_BULLETS.md
│
└── screenshots/
    └── README.md
```

Dashboard images and the `.pbix` file can be added later without changing the analytical structure of the repository.

---

## 13. Project Files

- **Raw data:** `Book1.csv` currently stored in the repository.
- **Source workbook:** E-Commerce Returns & Refunds — Raw Dataset (2025).
- **Power BI:** final dashboard/report can be placed under `powerbi/`.
- **DAX:** reusable KPI and diagnostic definitions are documented under `dax/`.
- **Business documentation:** methodology, findings, limitations and recommendations are under `docs/`.
- **Screenshots:** executive and diagnostic dashboard images can be added under `screenshots/`.

---

## Author

**Jitender Yadav**  
Data Analyst | SQL | Power BI | Excel | Business Intelligence

[GitHub](https://github.com/jitendera-code)
