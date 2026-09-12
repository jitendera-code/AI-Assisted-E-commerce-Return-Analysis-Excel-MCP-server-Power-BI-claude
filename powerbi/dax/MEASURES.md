# DAX / Power BI Measure Specification

This document records the analytical definitions used to keep the Power BI model and portfolio story consistent.

## Core measures

```DAX
Total Orders = DISTINCTCOUNT(Fact_Orders[Order_ID])
```

```DAX
Returned Orders =
CALCULATE(
    DISTINCTCOUNT(Fact_Orders[Order_ID]),
    Fact_Orders[Return_Quantity] > 0
)
```

```DAX
Return Rate % =
DIVIDE([Returned Orders], [Total Orders])
```

```DAX
Returned Units =
SUM(Fact_Orders[Return_Quantity])
```

## Refund Amount

Refund amount should reflect returned quantity multiplied by paid price after discount and reduced by refund deductions.

```text
Refund Amount = Return Quantity
              × Unit Price
              × (1 - Discount %)
              × (1 - Refund Deduction %)
```

## Return Days

```text
Return Days = Return Date - Delivery Date
```

## Diagnostic measures

- Average Return Days
- Products Returned
- Top Return Category
- Top Return Reason
- Category Refund Contribution %
- Previous Month Return Rate
- Return Rate Variance
- Return Reason Rank
- Cumulative Returned Units
- Cumulative Return %

## Modeling note

Use `DISTINCTCOUNT(Order_ID)` for order-level KPIs because the source grain is order-line level and one order can contain multiple product lines.

## Data-cleaning note

Standardize inconsistent values in Return Flag, Return Reason, Sales Channel and Payment Method before building dimensions and measures.
