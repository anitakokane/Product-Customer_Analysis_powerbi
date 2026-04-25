# Customer/Product Analysis Dashboard — Power BI

A multi-page Power BI report covering sales, product, and customer performance.

---

## Cover

!("C:\Users\Admin\Pictures\Screenshots\Screenshot 2026-04-25 112241.png")

---

## Business Performance Dashboard

![Business Performance Dashboard]("C:\Users\Admin\Pictures\Screenshots\Screenshot 2026-04-25 112241.png")

**KPIs:** Total Sales: 844.02K · Units Sold: 5,502 · Total Returns: 50

- Sales by Product Category, Segment, and Day
- Top 10 Products · Region slicer · Sales parameter

---

## Product Performance Analysis

![Product Performance Analysis]("C:\Users\Admin\Pictures\Screenshots\Screenshot 2026-04-25 112319.png")

**Regional Sales:** East 194.45K · South 234.70K · West 195.34K · North 219.54K

- Most sold products by quantity · Bottom 10 products
- Monthly sales matrix by category · Region-wise units sold

---

## Key DAX Measures

| Measure | Formula |
|---|---|
| Total Sales | `SUM(Sales_Fact[TotalAmount])` |
| South region sales | `CALCULATE([Total Sales], Sales_Fact[Region]="South")` |
| ALL regions | `CALCULATE([Total Sales], ALL(Customer_Dim[Region]))` |
| Average Units Sold | `AVERAGEX('Sales_Fact', 'Sales_Fact'[UnitsSold])` |
| TotalAmount>1000 | `CALCULATE([Total Sales], FILTER(Sales_Fact, Sales_Fact[TotalAmount]>1000))` |
| YoY % / MoM % / YTD | Quick Measures via Power BI |

---

## Row-Level Security

| Role | Filter |
|---|---|
| North_Manager | RegionName = "North" |
| West_Manager | RegionName = "West" |

---

## How to Open

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
2. Open `Power_bi_final.pbix` — all data is embedded, no external connection needed
