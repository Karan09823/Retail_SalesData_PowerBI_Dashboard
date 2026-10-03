# 📊 Retail Sales Performance Dashboard | Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Data%20Modeling-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

## 📌 Project Overview

This Power BI dashboard was developed to help a regional sales company monitor business performance across a 4-year historical period (2015–2018), evaluate category-wise target achievement, identify operational risks, and support data-driven decision-making.

The dashboard transforms raw sales, returns, targets, and regional management data into actionable business insights through interactive visualizations and KPI tracking.

### Business Objectives
- Analyze Year-over-Year (YoY) Sales and Profit Growth
- Monitor Category, Customer Segment, and Regional Performance
- Track Target Achievement across product categories
- Identify Return-related Profit Leakage
- Evaluate Operational Efficiency
- Support Monthly Leadership Reviews with actionable insights

---

## 🎯 Problem Statement

A regional sales company operates across multiple regions and product categories. Each Regional Manager is assigned category-specific sales targets and is evaluated based on both revenue generation and target achievement.

Despite overall business growth, leadership faces several challenges:
- Difficulty tracking category-wise target achievement
- Limited visibility into regional performance and customer segment contributions
- Increasing product returns and aggressive discounting affecting profitability
- Concerns regarding delivery efficiency
- Manual reporting processes that are time-consuming and difficult to interpret

The objective of this project is to build an analytical dashboard that tells a complete business story — from overall company performance to the root causes behind operational challenges.

---

## 📂 Data Sources

The project utilizes four datasets.

**1. Orders Data** — historical sales transactions (`order_2015`, `order_2016`, `order_2017`, `order_2018`)

| Column | Column | Column |
|---|---|---|
| Order ID | Customer Name | Product ID |
| Order Date | Segment | Category |
| Ship Date | City | Sub-Category |
| Ship Mode | State | Product Name |
| Customer ID | Country / Region | Sales, Quantity, Discount, Profit |

**2. People Data** — Region, People (regional manager mapping)

**3. Returns Data** — Order ID, Returned

**4. Target Data** — Category, Year, Sales Target

---

## 🛠 Data Preparation

1. **Data Consolidation** — Appended all yearly order files into a single Orders table
2. **Data Cleaning** — Corrected column data types; removed duplicate Order IDs from Returns data
3. **Composite Key Creation** — Built a `CategoryYear` column to relate Orders to the Target table
4. **Date Table Creation** — Dedicated Date Table with Year, Month, Month Number, Quarter
5. **Data Modeling** — Star-schema relationships between Orders, Returns, People, Target, and the Date Table
6. **DAX Development** — Total Sales, Total Profit, Total Orders, Sales YoY Growth %, Profit YoY Growth %, Returns YoY %, Return Rate, Target Achievement %, Target Gap, Average Discount %

---

## 📈 Dashboard Analysis

### 🏆 Page 1: Executive Overview

**KPIs:** Total Sales, Sales YoY Growth %, Total Orders, Total Profit, Profit YoY Growth %, Return Rate, Returns YoY %, Total Target, Target Gap, Target Achievement %

**Visualizations:** KPI cards · Sales & Profit trend (monthly/quarterly) · Sales Contribution by Segment (Donut Chart) · Sales Performance Matrix · Profit Performance Matrix

**Key Insights:**

| Finding | Detail |
|---|---|
| 🚀 Strong business growth | Total Sales reached **$2.94M (2015-2018)** (+55% YoY); Total Profit reached **$372.83K** (+53% YoY) |
| 👥 Customer Segments | The **Consumer** segment drives the highest share of the $2.94M revenue, followed by Corporate and Home Office clients. |
| 🎯 Target achievement | **101.66%** — revenue exceeded target by **$48.09K** |
| 💻 Technology as growth driver | **$1.1M+** in sales, **59% YoY growth**; South Region contributed 67% of that growth |
| 📦 Office Supplies as profit leader | ~**$160K profit**; South Region delivered 74% profit growth |
| 🚨 North Region furniture risk | Sales +57% but profit only +17% — signaling margin erosion at the regional level |

### 🌎 Page 2: Regional & Operational Performance

**KPIs:** Return Rate, Returns YoY %, Total Returns, Region Sales, Target Gap, Target Achievement %, Average Discount %

**Visualizations:** Category Performance Matrix · Shipping Mode Analysis (stacked bar) · Returns Trend Analysis (clustered column, YoY monthly comparison)

**Key Insights:**

| Finding | Detail |
|---|---|
| ❌ The Target Allocation Flaw | Furniture received the **highest target allocation ($850K)** despite being the lowest-margin category. It only achieved 91.66%. |
| 📉 Margin Erosion Verified | North Region Furniture profit lagged behind sales growth due to high markdowns. Analysis of **Average Discount %** confirms aggressive discounting is eroding baseline profitability. |
| 🔄 Furniture return risk | **6.50%** return rate — highest of all categories, driving up reverse-logistics cost |
| 🚚 Shipping dependency | Standard Class handles the majority of shipments; Same Day/First Class are a small share — a single-point operational dependency |
| 📈 Rising returns | Returns increased **54.35% YoY**, a trend that needs monitoring before it erodes margins further |

---

## 💡 Strategic Recommendations

1. **Realign Sales Targets** — Leadership should shift target weight away from low-margin Furniture and allocate higher targets to high-growth, high-profit categories like Technology and Office Supplies.
2. **Review North Region Pricing** — The data proves that aggressive discounting is eroding North Region Furniture profits. Implement stricter markdown thresholds to ensure revenue growth actually converts to profit.
3. **Audit the Standard Class shipping pipeline** — Review packaging quality for bulky furniture and identify fulfillment issues driving the 6.5% return rate.
4. **Optimize warehouse operations** — Office Supplies drives the largest return *volume*; tighten order verification and QC processes.
5. **Improve customer experience** — Enhance product descriptions, delivery accuracy, and after-sales support to combat the 54.35% YoY rise in returns.

---

### Executive Overview
<img width="1312" height="737" alt="image" src="https://github.com/user-attachments/assets/2ed3e88f-c8d8-4500-94b1-6bfc000bf3a2" />


### Regional & Operational Performance
<img width="1317" height="742" alt="image" src="https://github.com/user-attachments/assets/a1b7dbf5-2e9d-4704-94b9-71a5e1f9aacf" />

---

## 🧠 Skills Demonstrated

`Data Modeling` · `DAX` · `Power Query (ETL)` · `Star-Schema Design` · `KPI & Target Tracking` · `Root-Cause Analysis` · `Business Storytelling` · `Executive Reporting`

---

## 📁 Repository Structure

```
Retail_SalesData_PowerBI_Dashboard/
│
├── Karan_Kumar_Sahu_PowerBI_Submission.pbix   # Power BI report file
├── README.md                                  # Project documentation (this file)
├── order_2015.csv / order_2016.csv / order_2017.csv / order_2018.csv
├── Returns.csv
├── Target.csv
├── People.csv
├── Power BI Walkthrough & Performance Analysis Companion.pptx
└── images/
    ├── executive_overview.png
    └── regional_operational_performance.png
```

---

## 🚀 How to Use

1. Clone this repository
2. Open the `.pbix` file in Power BI Desktop
3. Use the slicers/filters on each page to explore performance by category, region, and time period
4. Refer to the accompanying `Power BI Walkthrough & Performance Analysis Companion.pptx` for a guided walkthrough of the analysis

---

## 🔮 Future Improvements

- Add a drill-through page for Sub-Category level analysis within Furniture to pinpoint the exact SKUs driving the 6.5% return rate
- Incorporate discount % as an explicit variable to test the hypothesis that North Region's profit lag is discount-driven
- Add a forecasting visual (e.g., linear trend or exponential smoothing) for next-quarter sales by category

---

## 👤 Author

**Karan Kumar Sahu**
Data Analyst | SQL · Python · Power BI
