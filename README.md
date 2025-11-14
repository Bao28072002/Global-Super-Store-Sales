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

### STAGE 1: EMPATHIZE - 5W1H

| Who will view this Dashboard? | What problem does this dashboard solve? | When and where will stakeholders view this dashboard? | Why do stakeholders need this dashboard? | How have stakeholders tried to achieve this goal? |
| :--- | :--- | :--- | :--- | :--- |
| • Global Senior Manager<br>• Business Unit Head<br>• Regional Sale Manager | • Provides insights into company performance (Revenue, Profit & Growth)<br>• Supports strategic decisions (market/product focus)<br>• Saves time and improves decision-making efficiency<br>• Enables quick response to market changes with real-time data | **When:**<br>• Before yearly/quarterly strategic meetings<br>• When making expansion or product decisions<br>• When there are unusual sales fluctuations<br>• To compare market performance<br><br>**Where:**<br>• At office<br>• While on business trips | • Quickly grasp business performance without manual data work<br>• Make better decisions on market expansion & product focus<br>• React faster to market changes<br>• Save meeting time and enhance internal communication | • Monthly/quarterly analysis<br>• Review charts to understand key metrics<br>• Use meetings to discuss and connect data points<br>• Identify potential markets and products for growth |
| **If only one key stakeholder is chosen, who would it be?**<br><br>Global Senior Manager | **Summarize the problem in one sentence**<br><br>This dashboard helps stakeholders understand past business performance and decide whether to expand into new markets, and if so, which markets and products to focus on. | | | |

---

# 📊 Key Insights & Visualizations

(Content for Section 4: Present the most significant analysis results, key findings, and related charts or data visualizations.)

---

# 🔎 Final Conclusion & Recommendation

(Content for Section 5: State the final conclusion based on the insights and provide strategic recommendations or future steps.)

---

---

**Revenue**
<img width="1326" height="785" alt="image" src="https://github.com/user-attachments/assets/9a02c175-5ac5-47f2-b936-1fda8e8066fc" />

**Product**
<img width="1320" height="742" alt="image" src="https://github.com/user-attachments/assets/d02e58e5-a7fe-4bad-b0c3-6d93d6670036" />

**Market**
<img width="1316" height="736" alt="image" src="https://github.com/user-attachments/assets/2fbcb14c-823f-4ae4-b17e-7e42cc806f8a" />

**Customer**
<img width="1316" height="736" alt="image" src="https://github.com/user-attachments/assets/ba49b97d-1114-4906-ba67-8cee975661bf" />



