# 🌍 Sales Performance & Market Expansion For A Global Superstore | Power BI

**Author:** Lê Gia Bảo

**Date:** August 2025

**Tools Used:** Power BI

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendation)

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

<img width="1272" height="710" alt="image" src="https://github.com/user-attachments/assets/b4b7687c-6a7f-45d7-bf37-bb53696f52ef" />

---
## EMPATHIZE MAP

<img width="1285" height="722" alt="image" src="https://github.com/user-attachments/assets/b3425430-ebd1-45a4-81f6-59bc26cdc492" />

---

### STAGE 2: Define point of view

## STAKEHOLDERS JOURNEY

<img width="1277" height="704" alt="image" src="https://github.com/user-attachments/assets/fa792641-dab3-4461-a612-8fa1ccabf05d" />

---

## DEFINE NORTHSTAR METRICS

<img width="1274" height="725" alt="image" src="https://github.com/user-attachments/assets/4c05a115-31ba-4a89-a5e5-4c34955bbaf5" />

---

## Dimension Data Grouping

<img width="1279" height="725" alt="image" src="https://github.com/user-attachments/assets/0c5cd5ed-2317-48ef-948c-f6383592a751" />

---

## VIEW BREAKDOWN & NORTHSTAR FORMULAS

<img width="1278" height="715" alt="image" src="https://github.com/user-attachments/assets/41966025-2932-44fd-aadb-cf533893eecb" />

---

### STAGE 3: METRICS FOR OVERVIEW LAYER 

<img width="1280" height="511" alt="image" src="https://github.com/user-attachments/assets/9d2a99d9-3ac0-4c52-871d-3772d1790981" />


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

5. **Shipping Mode Insights**
   - Standard Class has the highest average orders (~5 orders).
   - Same-Day delivery nearly 0 orders.
   → Customers prioritize cost-saving shipping options over speed.

6. **Returned Products**
   - Total Returned: **1,172**
   → Return rate is manageable but requires continuous monitoring.   

# 🔎 Final Conclusion & Recommendation

| **Strategy** | **Key Findings** | **Actionable Recommendations** |
| :--- | :--- | :--- |
| **🚀 Market Expansion** | - **Canada:** Very high profit margin (28%) despite low sales. <br> - **Africa & EMEA:** Extremely rapid revenue growth. <br> - **Oceania & Africa:** Attracting the most new customers. | - **Canada:** Expand smartly to capture maximum profit. <br> - **Africa & EMEA:** Increase investment to leverage growth. <br> - **Oceania & Africa:** Focus promotions to drive new customer acquisition. |
| **🛒 Product Optimization** | - **Technology:** Leads in both revenue and profit. <br> - **Accessories, Art, Labels:** High profit but low sales volume. <br> - **Tables:** Good sales but negative profit. <br> - **Suppliers & Furnishings:** Poor overall performance. <br> - **Storage:** High orders but low profit margin. | - **Technology:** Scale up, focus on high-profit items (Canon Copiers, Motorola/Cisco Phones). <br> - **Accessories, Art, Labels:** Market aggressively to boost sales. <br> - **Tables, Suppliers, Furnishings:** Consider delisting or redesigning. <br> - **Storage:** Review pricing and costs to improve profitability. |
| **⚙️ Operational Efficiency** | - **Standard Class Shipping:** Dominates shipping revenue. | - **Focus on Standard Class shipping** and audit other modes for potential cost savings. |




