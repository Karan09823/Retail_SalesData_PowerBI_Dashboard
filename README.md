# 📊 Retail Sales Performance Dashboard | Power BI

## 📌 Project Overview

This Power BI dashboard was developed to help a regional sales company monitor business performance, evaluate category-wise target achievement, identify operational risks, and support data-driven decision-making.

The dashboard transforms raw sales, returns, targets, and regional management data into actionable business insights through interactive visualizations and KPI tracking.

### Business Objectives

* Analyze Year-over-Year (YoY) Sales and Profit Growth
* Monitor Category and Regional Performance
* Track Target Achievement across product categories
* Identify Return-related Profit Leakage
* Evaluate Operational Efficiency
* Support Monthly Leadership Reviews with actionable insights

---

# 🎯 Problem Statement

A regional sales company operates across multiple regions and product categories. Each Regional Manager is assigned category-specific sales targets and is evaluated based on both revenue generation and target achievement.

Despite overall business growth, leadership faces several challenges:

* Difficulty tracking category-wise target achievement
* Limited visibility into regional performance
* Increasing product returns affecting profitability
* Concerns regarding delivery efficiency
* Manual reporting processes that are time-consuming and difficult to interpret

The objective of this project is to build an analytical dashboard that tells a complete business story—from overall company performance to the root causes behind operational challenges.

---

# 📂 Data Sources

The project utilizes four datasets.

## 1️⃣ Orders Data

Historical sales transactions from:

* `order_2015`
* `order_2016`
* `order_2017`
* `order_2018`

### Columns

| Column        |
| ------------- |
| Order ID      |
| Order Date    |
| Ship Date     |
| Ship Mode     |
| Customer ID   |
| Customer Name |
| Segment       |
| City          |
| State         |
| Country       |
| Region        |
| Product ID    |
| Category      |
| Sub-Category  |
| Product Name  |
| Sales         |
| Quantity      |
| Discount      |
| Profit        |

---

## 2️⃣ People Data

Regional manager information.

| Column |
| ------ |
| Region |
| People |

---

## 3️⃣ Returns Data

Order return information.

| Column   |
| -------- |
| Order ID |
| Returned |

---

## 4️⃣ Target Data

Annual sales targets by category.

| Column       |
| ------------ |
| Category     |
| Year         |
| Sales Target |

---

# 🛠 Data Preparation

The following ETL and modeling steps were performed:

### 1. Data Consolidation

* Appended all yearly order files into a single **Orders** table.

### 2. Data Cleaning

* Corrected column data types.
* Removed duplicate Order IDs from Returns data.

### 3. Composite Key Creation

* Created **CategoryYear** column.
* Used to establish relationship with Target table.

### 4. Date Table Creation

Created a dedicated Date Table containing:

* Year
* Month
* Month Number
* Quarter

### 5. Data Modeling

Established relationships between:

* Orders
* Returns
* People
* Target
* Date Table

### 6. DAX Development

Created measures for:

* Total Sales
* Total Profit
* Total Orders
* Sales YoY Growth %
* Profit YoY Growth %
* Returns YoY %
* Return Rate
* Target Achievement %
* Target Gap
* Sales vs Target

---

# 📈 Dashboard Analysis

---

# 🏆 Page 1: Executive Overview

## KPIs

* Total Sales
* Sales YoY Growth %
* Total Orders
* Total Profit
* Profit YoY Growth %
* Return Rate
* Returns YoY %
* Total Target
* Target Gap
* Target Achievement %

## Visualizations

### KPI Cards

Executive-level performance summary.

### Sales & Profit Trend Analysis

* Sales & Profit by Month
* Sales & Profit by Quarter

### Sales Performance Matrix

* Category
* Total Sales
* Sales PY
* Sales YoY Growth %

### Profit Performance Matrix

* Category
* Total Profit
* Profit PY
* Profit YoY Growth %

---

## Key Insights

### 🚀 Strong Business Growth

* Total Sales reached **$2.94M**
* Sales increased by **55% YoY**
* Total Profit reached **$372.83K**
* Profit increased by **53% YoY**

The company achieved strong and sustainable growth while maintaining profitability.

---

### 🎯 Target Achievement

* Target Achievement reached **101.66%**
* Revenue exceeded target by **$48.09K**

The organization successfully surpassed its overall sales target.

---

### ⚙ Operational Efficiency

* Orders increased by **50% YoY**
* Return Rate remained stable

Growth was achieved without a significant deterioration in product returns.

---

### 💻 Technology: Growth Driver

* Generated over **$1.1M Sales**
* Achieved **59% YoY Growth**
* South Region contributed **67% Growth**

Technology emerged as the primary revenue engine.

---

### 📦 Office Supplies: Profit Leader

* Generated approximately **$160K Profit**
* South Region delivered **74% Profit Growth**

Office Supplies was the strongest contributor to profitability.

---

### ⚠ Furniture: Category of Concern

* Lowest sales contribution
* Lowest profit contribution
* Slowest growth among categories

Furniture presents the largest improvement opportunity.

---

### 🚨 North Region Furniture Risk

* Sales increased by **57%**
* Profit increased by only **17%**

Potential reasons:

* Excessive discounting
* High logistics costs
* Product mix issues
* Operational inefficiencies

---

# 🌎 Page 2: Regional & Operational Performance

## KPIs

* Return Rate
* Returns YoY %
* Total Returns
* Region Sales
* Target Gap
* Target Achievement %

## Visualizations

### Category Performance Matrix

* Total Sales
* Total Profit
* Total Returns
* Return Rate
* Total Target
* Target Achievement %

### Shipping Mode Analysis

Stacked Bar Chart:

* Total Orders by Shipping Mode

### Returns Trend Analysis

Clustered Column Chart:

* Total Returns
* Returns PY
* Monthly Comparison

---

## Key Insights

### 📊 Uneven Category Performance

Overall company performance exceeded expectations; however, category-level analysis revealed performance gaps.

---

### 🏆 Technology & Office Supplies Exceeded Targets

| Category        | Target Achievement |
| --------------- | ------------------ |
| Technology      | 148.36%            |
| Office Supplies | 139.51%            |

These categories were responsible for driving overall target achievement.

---

### ❌ Furniture Missed Target

* Assigned Target: **850K**
* Achievement: **91.66%**

Furniture failed to meet expectations despite receiving the highest target allocation.

---

### 🔄 Furniture Return Risk

* Return Rate: **6.50%**

The highest return rate among all categories, resulting in increased reverse logistics costs and reduced profitability.

---

### 🚚 Shipping Dependency

* Standard Class handled the majority of shipments.
* Same Day and First Class represented a small share of total orders.

Operational efficiency is heavily dependent on Standard Class fulfillment.

---

### 📈 Rising Returns

* Returns increased by **54.35% YoY**

This trend requires immediate attention to prevent future margin erosion.

---

# 💡 Strategic Recommendations

## 1. Audit the Standard Class Shipping Pipeline

* Review packaging quality for bulky furniture items.
* Identify fulfillment issues causing high return rates.
* Reduce reverse logistics costs.

---

## 2. Optimize Warehouse Operations

Office Supplies accounts for the largest volume of returns.

Focus on:

* Order verification
* Packing accuracy
* Quality control procedures

---

## 3. Review Furniture Pricing Strategy

* Reassess discount structures.
* Evaluate pricing models in the North Region.
* Ensure revenue growth translates into profit growth.

---

## 4. Improve Customer Experience

* Enhance product descriptions.
* Improve delivery accuracy.
* Strengthen after-sales support.

---

## 5. Leverage High-Performing Categories

Continue investing in:

* Technology
* Office Supplies

Apply successful practices to underperforming categories.

---

# 📊 Expected Business Impact

Implementing these recommendations can help:

✅ Reduce return-related costs

✅ Improve profit margins

✅ Increase operational efficiency

✅ Improve customer satisfaction

✅ Strengthen customer trust

✅ Support sustainable long-term growth

---

# 🏅 Key Results

| Metric             | Value    |
| ------------------ | -------- |
| Total Sales        | $2.94M   |
| Sales Growth       | 55%      |
| Total Profit       | $372.83K |
| Profit Growth      | 53%      |
| Orders Growth      | 50%      |
| Target Achievement | 101.66%  |
| Target Gap         | +$48.09K |
| Returns Growth     | 54.35%   |

---

## 📸 Dashboard Screenshots

### Executive Overview

<img width="1318" height="742" alt="image" src="https://github.com/user-attachments/assets/67ba53ab-3cb8-4795-a32a-2325e080f60a" />


### Regional & Operational Performance

<img width="1316" height="743" alt="image" src="https://github.com/user-attachments/assets/13d47782-9fd5-424c-aedf-1cd85282a5e5" />


---

## 🚀 Tools Used

* Power BI
* Power Query
* DAX
* Data Modeling
* Business Analytics

---

### Author

**Karan Kumar**

Power BI | SQL | Data Analytics
