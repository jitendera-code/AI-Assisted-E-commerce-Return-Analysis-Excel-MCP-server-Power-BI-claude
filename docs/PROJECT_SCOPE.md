# Project Scope

## Business objective

Move from **“returns happened”** to **“why returns happened and what to fix first.”**

## Decision

Which return problems should the business prioritize to reduce customer returns and refund exposure?

## Source

- Period: 1 Jan 2025–31 Dec 2025
- Grain: one product line inside an order
- Raw rows: 4,286
- Unique orders: 3,100
- Products: 104
- Customers: 850

## North Star KPIs

- Return Rate %
- Returned Units
- Refund Amount
- Average Return Days

Supporting KPIs include Total Orders, Returned Orders, Products Returned, Top Return Category and Top Return Reason.

## Dashboard scope

### Page 1 — Executive Decision View

- KPI cards
- Monthly return trend
- Return reason Pareto
- Returns by category
- Returned units by sales channel
- Date, category and channel slicers

### Page 2 — Diagnostic / Action View

- Average Return Days
- Products Returned
- Top Category
- Top Return Reason
- Subcategory × Return Reason heatmap
- Discount vs Return Risk scatter
- Product return detail table
- Date, category, channel and return-reason slicers

## Analytical rule

A returned order is counted as a distinct Order_ID with Return_Quantity > 0. This gives 745 returned orders and a 24.03% return rate from 3,100 total orders.

## Prioritization rule

Prioritize using **return volume + return rate + financial exposure**, then recommend an action with an owner and success KPI.

## Causality rule

Dashboard patterns are evidence for investigation, not proof of operational causality. Recommendations should be presented as actions to test unless the data directly supports a causal conclusion.
