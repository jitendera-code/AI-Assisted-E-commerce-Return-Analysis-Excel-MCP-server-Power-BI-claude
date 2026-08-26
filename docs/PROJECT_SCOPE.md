# Project Scope

## Business objective

Move from **“returns happened”** to **“why returns happened and what to fix first.”**

## Source

- Period: 1 Jan 2025–31 Dec 2025
- Grain: one product line inside an order
- Raw rows: 4,286
- Unique orders: 3,100
- Products: 104
- Customers: 850

## Core KPIs

- Total Orders
- Returned Orders
- Return Rate %
- Refund Amount
- Average Return Days
- Products Returned
- Top Return Category
- Top Return Reason

## Dashboard scope

### Page 1 — Executive Summary

- KPI cards
- Monthly return trend
- Return reason Pareto
- Returns by category
- Returned units by sales channel
- Date, category and channel slicers

### Page 2 — Product Diagnostics

- Average Return Days
- Products Returned
- Top Category
- Top Return Reason
- Subcategory × Return Reason heatmap
- Discount vs Return Risk scatter
- Product return detail table
- Date, category, channel and return-reason slicers

## Deliberate exclusions

The supplied presentation states that the final report design avoids a Net Sales KPI and a Top 10 Returned Products visual.

## Analytical rule

A returned order is counted as a distinct Order_ID with Return_Quantity > 0. This gives 745 returned orders and a 24.03% return rate from 3,100 total orders.

## Causality rule

Dashboard patterns are evidence for investigation, not proof of operational causality. Recommendations should be presented as actions to test unless the data directly supports a causal conclusion.
