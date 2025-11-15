# 🌍 Sales Performance & Market Expansion For A Global Superstore | Power BI

**Author:** Lê Gia Bảo

**Date:** August 2025

**Tools Used:** Power BI

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

**📖 What is this project about?**

This project is about building a powerful **Power BI dashboard** using the **Global Superstore Sales** data. This data includes records of customer transactions (**Orders**), who the sales reps are (**People**), and items that were sent back (**Returns**).

The main goal is to give senior managers **clear, data-backed insights** so they can:

* **Understand current business performance** (See how well the company is doing right now).
* **Optimize market expansion strategies** (Figure out the best ways and places to grow the business).
* **Identify strategic products for growth** (Find the products that should be prioritized for maximum success).
* **Support better decision-making to drive revenue** (Use facts to make choices that boost sales).

**👤 Who is this project for?**

✔️ Data analysts & business analysts seeking actionable insights.

✔️ Marketing and sales teams focusing on product performance and market growth.

✔️ Route to market team aiming to improve distribution strategies and market reach.


**❓Business Questions:**

✔️ What is the current performance of Superstore?

✔️ Which markets should Superstore expand into to increase revenue?

✔️ Which products should be prioritized for strategic growth?

---

# 📂 Dataset Description & Data Structure

### **📌 Data Source** 

- **Source**: Kaggle  
- **Size**: The **Orders** table contains **51,290** records.  
- **Format**: CSV  

### 📊 **Data Structure & Relationships**  

#### 1️⃣ **Tables Used:**  
The dataset consists of **three tables**:  

- 🛒 **Orders** – Contains detailed transaction and customer information (**51,290 records**).

<details>
<summary> <strong>Table 1: Orders</strong></summary>

| Column Name       | Data Type   | Description                              |
|------------------|------------|------------------------------------------|
| `Order ID`      | `VARCHAR`   | Unique identifier for each order.       |
| `Order Date`    | `DATE`      | Date when the order was placed.         |
| `Ship Date`     | `DATE`      | Date when the order was shipped.        |
| `Ship Mode`     | `VARCHAR`   | Shipping method used for delivery.      |
| `Customer ID`   | `VARCHAR`   | Unique identifier for each customer.    |
| `Customer Name` | `VARCHAR`   | Full name of the customer.              |
| `Segment`       | `VARCHAR`   | Customer segment (e.g., Consumer, Corporate). |
| `City`         | `VARCHAR`   | City where the order was placed.        |
| `State`        | `VARCHAR`   | State where the order was placed.       |
| `Country`      | `VARCHAR`   | Country where the order was placed.     |
| `Postal Code`  | `VARCHAR`   | Postal code of the shipping address.    |
| `Market`       | `VARCHAR`   | Market region (e.g., APAC, EMEA).       |
| `Region`       | `VARCHAR`   | Geographical region of the order.       |
| `Product ID`   | `VARCHAR`   | Unique identifier for each product.     |
| `Category`     | `VARCHAR`   | Product category (e.g., Furniture, Office Supplies). |
| `Sub-Category` | `VARCHAR`   | Sub-category of the product.            |
| `Product Name` | `VARCHAR`   | Name of the product ordered.            |
| `Sales`        | `DECIMAL`   | Revenue generated from the order.       |
| `Quantity`     | `INT`       | Number of items ordered.                |
| `Profit`       | `DECIMAL`   | Profit earned from the order.           |

</details>

- 🔄 **Returns** – Stores data on returned orders.

<details>
<summary> <strong>Table 2: Returns</strong></summary>

| Column Name  | Data Type | Description |
|--------------|-----------|-------------|
| `Returned`   | `VARCHAR` | Indicates whether the order was returned (e.g., 'Yes' or 'No'). |
| `Order ID`   | `VARCHAR` | Unique identifier for each order. |

</details>
  
- 👥 **People** – Holds information about sales representatives.

<details>
<summary> <strong>Table 3: People</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `Person`    | `VARCHAR` | Name of the salesperson. |
| `Region`    | `VARCHAR` | Geographic region where the salesperson operates. |

</details>

#### 2️⃣ Data Relationships:

<img width="1009" height="786" alt="image" src="https://github.com/user-attachments/assets/6027fe42-a8dc-45a2-b55f-3bef25bed9a9" />


| **From Table** | **To Table** | **Join Key**   | **Relationship Type**                                  |
|------------|----------|------------|----------------------------------------------------|
| `Orders`   | `People` | `Region`   | Many-to-One (multiple orders belong to one Region) |
| `Orders`   | `Returns`| `Order ID` | Many-to-One (multiple orders belong to one Order ID) |
---

# 🧠 Design Thinking Process

### STAGE 1: EMPATHIZE

## EMPATHIZE - 5W1H

| Who will view this Dashboard? | What problem does this dashboard solve? | When and where will stakeholders view this dashboard? | Why do stakeholders need this dashboard? | How have stakeholders tried to achieve this goal? |
| :--- | :--- | :--- | :--- | :--- |
| • Global Senior Manager<br>• Business Unit Head<br>• Regional Sale Manager | • Provides insights into company performance (Revenue, Profit & Growth)<br>• Supports strategic decisions (market/product focus)<br>• Saves time and improves decision-making efficiency<br>• Enables quick response to market changes with real-time data | **When:**<br>• Before yearly/quarterly strategic meetings<br>• When making expansion or product decisions<br>• When there are unusual sales fluctuations<br>• To compare market performance<br><br>**Where:**<br>• At office<br>• While on business trips | • Quickly grasp business performance without manual data work<br>• Make better decisions on market expansion & product focus<br>• React faster to market changes<br>• Save meeting time and enhance internal communication | • Monthly/quarterly analysis<br>• Review charts to understand key metrics<br>• Use meetings to discuss and connect data points<br>• Identify potential markets and products for growth |
| **If only one key stakeholder is chosen, who would it be?**<br><br>Global Senior Manager | **Summarize the problem in one sentence**<br><br>This dashboard helps stakeholders understand past business performance and decide whether to expand into new markets, and if so, which markets and products to focus on. | | | |

---
## EMPATHIZE MAP

| Category | What the stakeholder THINKS and FEELS | What the stakeholder SEES | What the stakeholder SAYS and DOES |
| :------- | :------------------------------------ | :------------------------ | :--------------------------------- |
| **THINKS** | - Constantly worried about overall business performance and the pressure to grow. <br> - Fears missing out on market or product opportunities. | - Scattered reports in various Excel files from different teams, each with its own unique format. | - "I need a single, clear overview of global revenue." |
| **FEELS** | - Unsure about which products or markets are best for expansion. <br> - Lacks trust in data because it's not real-time or synchronized. <br> - Gets frustrated waiting for others to explain data; wishes for independent access. | - Charts are often unclear or difficult to compare across different markets. <br> - Data frequently shows inconsistencies, missing entries, or misalignment. | - "Show me the top 10 products to invest in this year and why." <br> - Asks staff to prepare quicker, clearer, and more understandable reports. <br> - Often questions: "Why did we choose this market? Do we have data to support this?" <br> - Proactively looks for BI tools to verify data instead of waiting for reports. |

---

## 🛑 What are the BIGGEST PROBLEMS and CHALLENGES?

- **No unified, clear picture** of the global business status.
- **Too much time spent** gathering, consolidating, and understanding data from various sources.
- **Reliance on others** for data access and interpretation, hindering independent analysis.

## ✅ What are the OPPORTUNITIES and BENEFITS?

- Gain a **quick and clear understanding** of global business through a single, cohesive view.
- Make **faster and more accurate strategic decisions** powered by visual, real-time data.
- **Easily identify** promising markets and high-potential products for future growth.

---

### STAGE 2: Define point of view

## STAKEHOLDERS JOURNEY

| Step | Title | Detailed Description (Paraphrased) |
| :---: | :--- | :--- |
| **1** | **Assess Current Business Performance** | Starting from the company's actual business situation, the **Board of Directors (BOD)** and relevant managers aim to **understand performance and trends** over the years. If results are positive, they plan to **expand into new markets** and select suitable products to maximize revenue. |
| **2** | **Request Data Visualization & Insights** | To obtain the necessary insights, stakeholders reach out to **Data Analysts** to **build dashboards** that clearly visualize business performance. This process enables them to **identify growth opportunities** and **potential products** to focus on. |
| **3** | **Strategy Finalization and Brainstorming** | After receiving the dashboard, stakeholders conduct meetings to **brainstorm ideas** and **finalize the business strategies** for moving forward and execution. |
| **4** | **Deployment and Performance Tracking** | **(This step is completed based on the project's logic)** <br> **New products are launched** in the new markets. Sell-in and sell-out data is **regularly updated** into the system to continuously monitor performance and allow for strategic adjustments. |

---

## DEFINE NORTHSTAR METRICS

| | **NORTHSTAR 1** | **NORTHSTAR 2 (Optional)** |
| :--- | :--- | :--- |
| **What VALUE you want to measure?** | Company profit | Company revenue |
| **WHEN the value DELIVERY SUCCESS?** | If the profit meets or exceeds the annual/quarterly plan + successful delivery. If it's lower, there must be insight to explain and adjust. | Meets or exceeds the set revenue target. |
| **Northstar Metric Name** | Profit | Revenue |
| **WHY do you choose this metric?** | - It's a realistic metric: high revenue doesn't mean much if costs are also high. Profit shows whether the company is running efficiently. <br> - Helps senior managers identify which markets or product lines bring in more profit, guiding investment priorities. | - Directly aligns with the goal of market expansion. <br> - Revenue represents cash inflow—good revenue means the market is accepting the company's products/services. |

---

## Dimension Data Grouping

| Dimension Data Group | **Group 1** | **Group 2** | **Group 3** | **Group 4** |
| :---: | :---: | :---: | :---: | :---: |
| **Primary Dimension Name** | Location | Product | Time | Customer Type |
| **Detailed Attributes** | Market/Region/Country/State | Segment, Category, SubCat, Product name | Year, quarter, month, day | Demographic |

---

## Dashboard Views and Focus Areas

| View | Description | Purpose (Key Focus) |
| :---: | :--- | :--- |
| **Overall Performance (View 1)** | Assesses the **Revenue and Profit** across the entire operation. | To understand the global success level and identify financial trends. |
| **Market (View 2)** | Evaluation of sales and profit distribution across geographies. | To **Evaluate Markets** and select high-potential ones for expansion. |
| **Product (View 3)** | Analysis focused solely on product performance metrics. | To **Determine Strategic Products** and evaluate strong vs. weak performers for optimization. |
| **Customer (View 4)** | Analysis of customer segments and demographics. | (Implied purpose from the navigation tabs) To understand buyer behavior and optimize sales efforts toward key customer segments. |

---

## VIEW BREAKDOWN & NORTHSTAR FORMULAS

| View | Description | Why | NORTHSTAR Formula | Profit | Revenue |
| :---: | :--- | :--- | :---: | :--- | :--- |
| **View 1** | Overall Performance | Assess overall business performance to understand the global success level of the company. | View 1 breakdown | Total profit performance by location = SUM(Profit) across all countries/regions | Total revenue performance by location = SUM(Revenue) across all countries/regions |
| **View 2** | Revenue & Profit | Identify potential markets. | View 2 breakdown | Total profit performance by category = SUM of all category | Total revenue pfm by category = SUM(Revenue) across all product categories |
| **View 3** | Product | Determine strategic products and evaluate strong vs. weak performers. | View 3 breakdown | Total profit performance by category = SUM(Profit) across all product categories | Revenue by market = SUM(Revenue) grouped by region/country |

---

### STAGE 3: METRICS FOR OVERVIEW LAYER 

**Start With:** Based on the NorthStar Metric, brainstorm breakdown dimensions and relevant insights from different perspectives of the NorthStar Metric.

| Overview layer | Metric 1 | Metric 2 | Metric 3 | Metric 4 |
| :--- | :--- | :--- | :--- | :--- |
| | **Profit** | **Revenue** | **Profit Margin** | **Total Quantity** |
| | Metric 5 | Metric 6 | Metric 7 | Metric 8 |
| | **% Growth** | **YoY** | **Return Rate** | **Total order** |


# 📊 Key Insights & Visualizations

### 🔍 Dashboard Preview

### I. Overview

<img width="1335" height="756" alt="image" src="https://github.com/user-attachments/assets/c0b6631f-676d-4ec7-ba72-40a40623dbc9" />

### 📌 Key Findings:

## I. Overall Performance & Trends (All-Time)

### Overview
* **Revenue:** **$12.64 Million**
* **Profit:** **$1.467 Million**
* **Profit Margin:** **11.61%** (considered healthy)

### Positive Year-over-Year (YoY) Growth
The current performance shows significant growth across core metrics:
* **Revenue YoY:** **+51.5%** (+$4.3M)
* **Profit YoY:** **+52.3%** (+$0.5M)
* **Total Orders YoY:** **+51.7%** (+8.5K)

### Annual Sales Trend
* Total sales show a **clear upward trend** from 2011 to 2014.
* Sales **peaked** in **2014** with **$4.3 Million** in total sales.

---

## II. Geographic and Segment Focus

### 🌎 Market and Country Analysis
* **Dominant Market:** **APAC** is the largest contributor to Total Sales with **$3.6 Million**, significantly outpacing **EU** ( $\$2.9\text{M}$ ).
* **Leading Country:** The **United States** has the highest total sales: **$2.297 Million**.

### 👤 Customer Segment Analysis
* **Most Valuable Segment:** The **Consumer** segment accounts for the majority of Total Sales by Segment, at **51.48%** ( $\$6.51\text{M}$ ).

---

## III. Product Category and Order Details

### 🛍️ Product Category
* **Leading Category:** **Technology** leads in sales in the current period (Quarter chart), accounting for **37.53%** ( $\$4.7\text{M}$ ) of total sales.

### 📦 Order and Return Details
* **Total Orders Processed:** 25,035
* **Total Quantity Sold:** 178,312
* **Return Rate:** **4.68%** (This rate is down $\text{0.1\%}$ compared to the previous year).

<img width="1316" height="739" alt="image" src="https://github.com/user-attachments/assets/09ba7316-94ee-49d5-837c-94f1ac1c9f45" />

### 📌 Key Findings:

1. **Strong YoY Growth in Revenue & Profit**
   - Revenue YoY: **+51.5% (+4.3M)**
   - Profit YoY: **+52.3% (+0.5M)**
   - → Indicates a solid and sustainable growth performance.

2. **Significant Increase in Total Orders & Quantity**
   - Total Orders YoY: **+51.7% (+8.5K)**
   - Total Quantity YoY: **+51.5% (+60,622)**
   - → Both order volume and total items sold increased substantially.

3. **Return Rate Remains Stable**
   - Return Rate: **4.68%**
   - Rate YoY: **-0.1%**
   - → Slight improvement despite strong sales growth.

4. **APAC & EU Are the Top-Contributing Markets**
   - APAC: **$3.58M**
   - EU: **$2.94M**
   - → These regions drive the highest revenue.

5. **Central & South Lead in Revenue by Region**
   - Central: **~2.8M**
   - South: **~1.6M**
   - → Central is the highest-performing region.

6. **Return Volume Concentrated in North America & Europe**
   - Highest return density in: **US** and **Europe**
   - → Possibly linked to logistics or regional return policies.
   - 
<img width="1321" height="738" alt="image" src="https://github.com/user-attachments/assets/8b477355-e5c2-4751-a465-7b853bfd1983" />

1. **Order Volume**
   - Total Orders: **25,035**
   - YoY Order Growth: **+51.7%**
   - → Indicates strong and consistent market demand.

2. **Return Rate**
   - Return Rate: **4.68%**
   - YoY Change: **-0.1%**
   - → Slight improvement, showing stable product quality and delivery performance.

3. **Product Category Performance**
   - Technology products (Phones, Machines, Copiers) generate the highest sales.
   - Furniture items such as Bookcases and Chairs also show solid performance.
   - → Technology is the top revenue-driving category.

4. **Market/Region Trends**
   - EU and APAC are the strongest revenue-contributing regions.
   - → These are priority markets for strategic focus.
  
### 📌 Key Findings:

1. **Strong Financial Performance**
   - Total Revenue: **12.643M**
   - Total Profit: **1.467M**
   - YoY Growth:
     - Revenue: **+51.5%**
     - Profit: **+52.3%**
   → The business experienced a major improvement compared to last year.

2. **Customer Base and Activity**
   - Total Customers: **1,590**
   - Total Orders: **25,035**
   - Products: **3,788 SKU**
   → High product diversity supports strong order volume.

3. **Average Profit per Customer Shows Clear Growth**
   - 2011: **$190**
   - 2012: **$224**
   - 2013: **$279**
   - 2014: **$334**
   → Profit per customer increases steadily year over year, showing improved customer value.

4. **Revenue by Segment**
   - Consumer segment leads revenue every year.
   - Corporate and Home Office also grow steadily.
   → Consumer remains the core market, but Corporate shows the strongest upward trend.

5. **Top 10 Customers Drive Significant Profit**
   - Highest customer profit: **$8.8K**
   - All top-10 customers contribute **$6.5K–$8.8K**.
   → Customer concentration is moderate but high-value customers are impactful.

6. **Shipping Mode Insights**
   - Standard Class has the highest average orders (~5 orders).
   - Same-Day delivery nearly 0 orders.
   → Customers prioritize cost-saving shipping options over speed.

7. **Returned Products**
   - Total Returned: **1,172**
   → Return rate is manageable but requires continuous monitoring.   

# 🔎 Final Conclusion & Recommendation

| **Strategy** | **Key Findings** | **Actionable Recommendations** |
| :--- | :--- | :--- |
| **🚀 Market Expansion** | - **Canada:** Very high profit margin (28%) despite low sales. <br> - **Africa & EMEA:** Extremely rapid revenue growth. <br> - **Oceania & Africa:** Attracting the most new customers. | - **Canada:** Expand smartly to capture maximum profit. <br> - **Africa & EMEA:** Increase investment to leverage growth. <br> - **Oceania & Africa:** Focus promotions to drive new customer acquisition. |
| **🛒 Product Optimization** | - **Technology:** Leads in both revenue and profit. <br> - **Accessories, Art, Labels:** High profit but low sales volume. <br> - **Tables:** Good sales but negative profit. <br> - **Suppliers & Furnishings:** Poor overall performance. <br> - **Storage:** High orders but low profit margin. | - **Technology:** Scale up, focus on high-profit items (Canon Copiers, Motorola/Cisco Phones). <br> - **Accessories, Art, Labels:** Market aggressively to boost sales. <br> - **Tables, Suppliers, Furnishings:** Consider delisting or redesigning. <br> - **Storage:** Review pricing and costs to improve profitability. |
| **⚙️ Operational Efficiency** | - **Standard Class Shipping:** Dominates shipping revenue. | - **Focus on Standard Class shipping** and audit other modes for potential cost savings. |




