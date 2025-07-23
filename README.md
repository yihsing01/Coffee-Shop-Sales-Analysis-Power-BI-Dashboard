# ☕ Coffee Shop Sales Analysis — Power BI Dashboard

An interactive Power BI dashboard analysing sales data from a fictional coffee chain using DAX calculations and visual storytelling.

This project explores transaction-level data from **Maven Roasters**, a fictional coffee shop operating out of three NYC locations. It provides rich insights into revenue trends, product performance, and operational efficiency through time-based segmentation and custom DAX measures.

---

## 📊 Overview

This dashboard provides analysis of:

- 📈 Monthly revenue trends and growth
- 🏪 Performance by store location
- 🛍️ Revenue and quantity by product category, type, and item
- 📅 Sales by day of the week
- ⏰ Purchasing patterns by time of day
- 📌 Top and bottom performing products
- 📆 Weekly and hourly operational trends

📅 **Date Range:** January 1, 2023 – June 30, 2023  
📍 **Locations:** Hell's Kitchen, Astoria, Lower Manhattan

### 🔍 Key Findings

- 📊 Revenue increased steadily from February onward
- 🌅 Morning rush accounted for ~36% of total daily revenue (RM253K)
- 📉 Transaction volume declined throughout the day
- 🏬 Each location contributed almost equally (~RM230K)
- ☕ Coffee led with RM270K in total revenue
- 📈 Revenue grew by **6.23%** in June compared to May

---

## 🗂️ Dataset

The dataset used is publicly available on Kaggle:

👉 [Coffee Shop Sales — Kaggle Dataset by ahmedabbas757](https://www.kaggle.com/datasets/ahmedabbas757/coffee-sales/data)

---

## 📈 Dashboard Overview

This dashboard contains **four interactive pages**:

1. **Executive Overview** — KPIs, revenue trends, and breakdowns  
2. **Product Performance** — Revenue & quantity by product  
3. **Top and Bottom 5** — Best and worst sellers  
4. **Operational Insights** — Store-level comparison and hourly trends

---

## 🛠️ Techniques and Tools

- **Power BI Desktop**
- Data transformation using **Power Query**
- Calculated columns for:
  - `time_category` (morning rush, etc.)
  - `day_name_short`, `day_name_sort`, etc.
  - `revenue = quantity * unit_price`
- DAX Measures for:
  - Revenue growth
  - Avg. transaction value
  - Total transactions
- Visuals: KPI Cards, Line/Bar/Donut Charts, Matrix Tables, Stacked Bars

### 🎯 Other Features

- Dynamic slicers for date range and store location  
- Revenue growth vs previous month  
- Day and hour-based behavior analysis  
- Category-level drilldown

---

## 💡 Sample DAX Measures

- Revenue Growth<pre>Revenue Growth = 
DIVIDE([Total Revenue] - [Total Revenue Previous], [Total Revenue Previous])</pre>
- Average Transaction Value<pre>Avg Transaction Value = 
DIVIDE(
    CALCULATE(SUM('Coffee Shop Sales'[Revenue]), <date_filter>),
    CALCULATE(COUNT('Coffee Shop Sales'[Transactions]), <date_filter>)
)</pre>
