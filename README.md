# Retail_SalesData_PowerBI_Dashboard
## Problem Statement:
A regional sales company has been growing steadily over the last few years. The business operates across different regions, sells multiple product categories, and works with several Regional Managers who are responsible for driving sales performance in their assigned areas.
Each Regional Manager is assigned multiple product categories as sales targets. This means a manager is not evaluated only on total regional sales, but also on how well they perform across the specific product categories assigned to them. For example, one Regional Manager may be responsible for achieving targets in Electronics, Furniture, and Office Supplies within a region, while another manager may handle a different mix of categories in another region.
The company has recently started feeling pressure from leadership. Revenue is growing in some areas, but not consistently across all regions or categories. Some Regional Managers appear to be performing well overall, but they may still be missing targets in certain product categories. In other cases, a region may generate high sales but fail to achieve category-wise targets. Management has also noticed that sales numbers alone are not enough to understand the real health of the business. A product category may look successful on paper, but high returns or delayed deliveries may be affecting customer satisfaction.
The Sales Manager is responsible for reviewing this business performance and presenting it to leadership. However, the current reporting process is manual, scattered across spreadsheets, and difficult to understand. Every review meeting leads to more questions than answers. The manager is unable to clearly explain whether the business is improving, whether targets are being achieved, which Regional Managers need attention, whether returns are under control, and whether delivery delays are damaging the customer experience.
The Sales Manager does not come from an analytics background. He is a practical business leader who understands customers, sales pressure, people performance, category targets, and operational issues. He does not want a technical report filled with complex terms. He wants a clear business view that helps him understand what is happening, why it is happening, and where he should take action.
The leadership team has asked for a proper analytical dashboard that can be used during monthly business reviews. The dashboard should help the Sales Manager explain business performance in a simple and confident way. It should allow him to compare the current year with the previous year, understand whether sales and profit are improving, identify whether Regional Managers are achieving their assigned category targets, and highlight where performance has improved or declined.
A major expectation from the client is Year-over-Year comparison. The Sales Manager wants to see how the business has changed compared to last year. He wants to know the percentage growth or decline in sales, profit, orders, target achievement, returns, and delivery delays. He should be able to quickly understand whether a number is better or worse than the previous year and what that means for the business.
The client is also concerned about category-wise targets. Sales targets are assigned to Regional Managers across multiple product categories, but the manager does not currently have a clear view of whether those targets are being achieved at the region, manager, or category level. He wants to understand not only the total sales value, but also whether each Regional Manager is meeting the targets for the categories assigned to them. If there is a shortfall, he wants to know which region, manager, and category are causing the gap.
Product returns have become another concern. Some returns are expected in the business, but high returns can indicate poor product quality, wrong customer expectations, incorrect selling, or service issues. The Sales Manager wants to know whether returns are increasing or decreasing compared to last year and whether any specific region, product category, or Regional Manager is contributing more to this problem.
Delivery delay is also becoming important. The company believes that a sale is not complete until the product reaches the customer on time. Delayed delivery can affect customer trust, increase complaints, and lead to returns. The Sales Manager wants to understand whether delivery delays are under control and whether delays are connected to specific regions, product categories, shipping methods, or Regional Managers.
The client wants the final dashboard to behave like a business story, not just a reporting file. When the Sales Manager opens the dashboard, he should be able to understand the overall health of the business first. Then he should be able to move deeper into the reasons behind the performance. The dashboard should help him answer questions such as whether the business is growing, whether the growth is profitable, whether Regional Managers are achieving their category targets, whether returns are damaging performance, and whether delivery delays are creating business risk.

# Data Description

This project uses four categories of datasets:

## 1. Orders Data
The orders data is divided into four separate files representing sales transactions from 2015 to 2018:

- `order_2015`
- `order_2016`
- `order_2017`
- `order_2018`

### Columns
| Column Name |
|------------|
| Order ID |
| Order Date |
| Ship Date |
| Ship Mode |
| Customer ID |
| Customer Name |
| Segment |
| City |
| State |
| Country |
| Region |
| Product ID |
| Category |
| Sub-Category |
| Product Name |
| Sales |
| Quantity |
| Discount |
| Profit |

---

## 2. People Data
Contains information about the person responsible for each region.

### Columns
| Column Name |
|------------|
| Region |
| People |

---

## 3. Returns Data
Contains information about returned orders.

### Columns
| Column Name |
|------------|
| Order ID |
| Returned |

---

## 4. Target Data
Contains annual sales targets for each product category.

### Columns
| Column Name |
|------------|
| Category |
| Year |
| Sales Target |

# Data Preparation

The following data preparation steps were performed before analysis and dashboard development:

1. **Merged Orders Data**
   - Appended `order_2015`, `order_2016`, `order_2017`, and `order_2018` into a single table named **Orders**.

2. **Data Cleaning**
   - Corrected data types for all columns across the datasets.
   - Removed duplicate records from the **Returns** table based on `Order ID`.

3. **Created a Composite Key**
   - Created a new column named **CategoryYear** in the **Orders** table.
   - This column was used to establish a relationship with the **Target** table.

4. **Built a Date Table**
   - Created a dedicated **DateTable** to support time intelligence calculations.
   - Included the following fields:
     - Year
     - Month
     - Month Number
     - Quarter

5. **Established Data Model Relationships**
   - Connected the Orders, Returns, People, Target, and Date tables through appropriate relationships to create a star-schema-like model.

6. **Created DAX Measures**
   - Developed DAX measures for key business KPIs and analytical insights, including:
     - Total Sales
     - Total Profit
     - Total Orders
     - Profit Margin
     - Sales vs Target
     - Year-over-Year Growth
     - Return Rate
     - Other supporting measures used in dashboard visualizations
# Analysis of Data

## Page 1 – Executive Overview

### KPIs Created

The following Key Performance Indicators (KPIs) were developed using DAX measures:

- Total Sales
- Sales YoY Growth %
- Total Orders
- Total Profit
- Profit YoY Growth %
- Return Rate
- Returns YoY %
- Total Target
- Target Gap
- Target Achievement %

### Visualizations

#### KPI Cards
Displayed key business metrics such as sales, profit, orders, returns, and target achievement.

#### Sales & Profit Trend Analysis
- Stacked Column Chart: Total Sales and Total Profit by Month
- Column Chart: Total Sales and Total Profit by Quarter

#### Sales Performance Matrix
Parameters:
- Category
- Total Sales
- Sales PY (Previous Year)
- Sales YoY Growth %

#### Profit Performance Matrix
Parameters:
- Category
- Total Profit
- Profit PY (Previous Year)
- Profit YoY Growth %

---

## Key Business Insights

### 1. Strong Business Growth
- Total Sales reached **$2.94M**, representing **55% YoY growth**.
- Total Profit reached **$372.83K**, representing **53% YoY growth**.
- # The business achieved both revenue and profit growth simultaneously, indicating sustainable expansion.

### 2. Target Achievement
- Global sales target of **$3M** was exceeded.
- Target Achievement reached **101.66%**.
- # Positive Target Gap of **$48.09K** indicates revenue exceeded expectations.

### 3. Operational Efficiency
- Total Orders increased by **50% YoY**.
- Return Rate remained stable compared to the previous year.
- # Increased demand was managed without a rise in product returns.

### 4. Technology Category – Primary Growth Driver
- Generated over **$1.1M** in sales.
- Achieved approximately **59% YoY sales growth**.
- South Region contributed significantly with **67% sales growth**.
- # Identified as the strongest contributor to overall revenue growth.

### 5. Office Supplies – Highest Profit Contributor
- Generated nearly **$160K** in profit.
- South Region recorded approximately **74% profit growth**.
- # Delivered the highest profitability among all product categories.

### 6. Furniture – Area of Concern
- Lowest sales contribution among categories.
- Slowest sales growth rate (~51%).
- Lowest profit contribution (~$68K).
- # Represents the biggest opportunity for business improvement.

### 7. North Region Furniture Performance
- Furniture sales increased by approximately **57%**.
- Profit increased by only **17%**.
- # Indicates declining profitability despite higher sales.
- # Potential causes:
  - Excessive discounting
  - Higher shipping costs
  - Operational inefficiencies
  - Unfavorable product mix

### Business Recommendation
Focus future investigations on the Furniture category, particularly in the North Region, to identify factors reducing profitability and improve margin performance.


## Page 2 – Regional & Operational Performance

### KPIs Created

The following KPIs were developed to analyze regional performance and operational efficiency:

- Return Rate
- Returns YoY %
- Total Returns
- Region Sales
- Target Gap
- Target Achievement %

### Visualizations

#### Category Performance Matrix
Parameters:
- Category
- Total Sales
- Total Profit
- Total Returns
- Return Rate
- Total Target
- Target Achievement %

#### Shipping Mode Analysis
- Stacked Bar Chart displaying Total Orders by Shipping Mode.

#### Returns Trend Analysis
- Clustered Column Chart displaying:
  - Total Returns
  - Returns PY (Previous Year)
  - Month-wise comparison

---

## Key Business Insights

### 1. Overall Success Masks Category-Level Issues
- Overall business performance exceeded targets.
- However, category-level analysis revealed uneven performance across product categories.
- Technology and Office Supplies significantly outperformed targets, while Furniture underperformed.

### 2. Technology and Office Supplies Drive Growth
- Technology achieved approximately **148.36%** of its assigned target.
- Office Supplies achieved approximately **139.51%** of its assigned target.
- These categories were the primary contributors to overall target achievement.

### 3. Furniture Failed to Meet Expectations
- Furniture was assigned the highest sales target (**850K**).
- Achieved only **91.66%** of its target.
- Identified as the weakest-performing category from a target achievement perspective.

### 4. High Return Rate Impacts Furniture Profitability
- Furniture recorded a **6.50% Return Rate**, the highest among categories.
- High product returns increase reverse logistics costs and negatively affect profitability.
- Indicates potential issues related to product quality, customer expectations, or delivery processes.

### 5. Shipping Operations Depend Heavily on Standard Class
- Standard Class handled the majority of customer orders.
- Same Day and First Class shipping modes represented a much smaller share of shipments.
- Suggests operational dependence on slower shipping channels.

### 6. Rising Returns Require Attention
- Total Returns increased by approximately **54.35% YoY**.
- Growing returns may create additional operational costs and reduce profit margins.
- Indicates the need to review fulfillment, product quality, and customer satisfaction processes.

## Business Recommendations

Based on the regional and operational analysis, the following actions are recommended to reduce profit leakage and improve business performance:

### 1. Investigate High Furniture Returns
- Analyze the root causes of Furniture returns, including product quality, packaging, shipping damage, and customer expectations.
- Focus on reducing reverse logistics costs that negatively impact profitability.

### 2. Audit the Standard Class Shipping Pipeline
- Conduct a detailed review of the Standard Class fulfillment process, particularly for bulky Furniture products.
- Evaluate packaging standards, handling procedures, and delivery performance.
- Identify operational issues contributing to the high return rate and margin erosion.

### 3. Optimize Warehouse Operations
- Office Supplies contributes the largest share of total returns despite maintaining a moderate return rate.
- Streamline order verification, packing, and quality-control processes to reduce fulfillment errors.
- Improve warehouse efficiency to lower labor and return-processing costs.

### 4. Review Furniture Pricing and Discount Strategies
- Re-evaluate pricing and discount models, particularly in the North Region.
- Ensure that increased sales volume translates into proportional profit growth.
- Identify products or promotions that may be reducing overall margins.

### 5. Improve Customer Experience
- Enhance product descriptions, delivery accuracy, and after-sales support.
- Reduce avoidable returns by ensuring customers receive products that meet expectations.

### 6. Leverage High-Performing Categories
- Continue investing in Technology and Office Supplies, which are the primary drivers of sales growth and profitability.
- Apply successful strategies from these categories to improve the performance of underperforming segments.

### Expected Business Impact
By addressing these operational bottlenecks and optimizing high-volume channels, the company can:

- Reduce return-related costs
- Improve profit margins
- Increase operational efficiency
- Strengthen customer trust and satisfaction
- Support sustainable long-term growth
