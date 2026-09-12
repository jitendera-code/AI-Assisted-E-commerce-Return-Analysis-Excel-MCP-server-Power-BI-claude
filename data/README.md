# Data

The project uses 2025 e-commerce order-line data.

- Raw rows: 4,286
- Unique orders: 3,100
- Products: 104
- Customers: 850
- Grain: one product line inside an order

A returned order is counted using `Return_Quantity > 0` with distinct `Order_ID` for order-level KPIs.

> The repository currently keeps the source CSV at the project root for compatibility with the existing Power BI workflow. The next local Git move can place it here as `data/ecommerce_returns_raw.csv` after confirming the PBIX source path.
