# Data Dictionary

## Fact / transaction fields

| Field | Role |
|---|---|
| Order_Line_ID | Unique order-line identifier |
| Order_ID | Customer order identifier; use DISTINCTCOUNT for Total Orders |
| Order_Date | Order placement date |
| Customer_ID | Customer identifier |
| Customer_Segment | Customer segment |
| Customer_City | Customer city |
| Customer_State | Customer state |
| Product_ID | Product identifier |
| Product_Name | Product name |
| Category | Product category |
| Subcategory | Product subcategory |
| Brand | Product brand |
| Sales_Channel | Sales channel |
| Payment_Method | Payment method |
| Quantity | Ordered quantity |
| Unit_Price | Listed unit price |
| Unit_Cost | Unit cost |
| Discount_Pct | Discount applied |
| Shipping_Fee | Shipping fee |
| Delivery_Date | Delivery date |
| Return_Flag | Raw return indicator; contains inconsistent labels |
| Return_Date | Return date |
| Return_Reason | Raw return reason; requires standardization |
| Return_Quantity | Units returned |
| Refund_Deduction_Pct | Refund deduction percentage |
| Product_Rating | Product rating |

## Derived analytical fields

The source workbook intentionally does not contain calculated Sales Amount, Discount Amount, COGS, Refund Amount, Net Revenue, Return Days or Return Rate. These are derived in Power BI rather than added to the raw source.
