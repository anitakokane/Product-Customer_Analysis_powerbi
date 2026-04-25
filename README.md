# Customer/Product Analysis Dashboard — Power BI

A multi-page Power BI report covering sales, product, and customer performance.

---

## Cover

(<img width="800" height="454" alt="cover_project" src="https://github.com/user-attachments/assets/5e7e56e6-5101-4979-99a8-b29f6c8cb97f" />
)

---

## Business Performance Dashboard

![Business Performance Dashboard](screenshot-main-dashboard.jpg)

**KPIs:** Total Sales: 844.02K · Units Sold: 5,502 · Total Returns: 50

- Sales by Product Category, Segment, and Day
- Top 10 Products · Region slicer · Sales parameter

---

## Product Performance Analysis

![Product Performance Analysis](screenshot-product-dashboard.jpg)

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
