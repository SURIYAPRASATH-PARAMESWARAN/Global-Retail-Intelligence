# Global Retail Intelligence

A three-page interactive Power BI dashboard investigating the sales performance, profit leakage, and customer behaviour of a global retail operation across 147 countries from 2011 to 2014. Built as a portfolio project targeting data analyst roles in retail, e-commerce, and financial services.

> **Business Question:** Revenue is $12.64M. So why is profit margin only 11.61%? Where is the money leaking — and how do we fix it?

---

## Dashboard Overview

This project goes beyond standard sales reporting. Instead of answering "how much did we sell?", it answers "why are we losing margin and where do we act?" Every page is built around a specific business question that a retail analyst or commercial manager would face on day one.

**Pages:**

- **Page 1 — Global Sales Overview** — Executive summary with live world map showing sales bubbles by market, ribbon chart tracking category sales rank over time, segment and market donuts, ship mode funnel analysis, and year slicer for dynamic filtering.
- **Page 2 — Profit Leak Analysis** — Deep investigation into where profit is being destroyed. Waterfall chart showing profit by sub-category, scatter plot proving discount abuse kills margin, order priority breakdown, and year-on-year profit vs sales trend.
- **Page 3 — Customer & Product Intelligence** — Top 10 profit-generating products, bottom 10 loss-making products, top 10 customers by sales, and an interactive Decomposition Tree drilling from total profit down to Category → Sub-Category → individual Customer.

---

## Screenshots

### Page 1 — Global Sales Overview
![Page 1](screenshots/page1.png)

### Page 2 — Profit Leak Analysis
![Page 2](screenshots/page2.png)

### Page 3 — Customer & Product Intelligence
![Page 3](screenshots/page3.png)

---

## Key Features

- **World map visual** — Sales bubbles sized by revenue, coloured by market region (APAC, EU, US, LATAM, EMEA, Africa) across 147 countries
- **Decomposition Tree** — Interactive drill-down from Total Profit → Category → Sub-Category → Customer Name, revealing exactly who and what drives profitability
- **Discount vs Profit scatter** — Visually proves that high discount rates correlate directly with negative profit — a finding any commercial team would act on immediately
- **Waterfall chart** — Sub-category profit breakdown showing which product lines are winners and which are silently destroying margin
- **Ribbon Chart** — Category sales rank over time showing how Furniture, Office Supplies and Technology shifted in dominance year on year
- **Top N filtering** — Dynamic Top 10 and Bottom 10 product filters using Power BI filter pane
- **Cross-page slicers** — Category, Segment, Country and Order Date slicers filtering all visuals simultaneously

---

## Tech Stack

| Tool | Usage |
|------|-------|
| Power BI Desktop | Dashboard development, visualisation, interactivity |
| DAX | Custom measures, profit margin calculations, discount analysis |
| Power Query (M) | Data type casting, column profiling, transformation |
| Excel / CSV | Source data preparation and inspection |

---

## DAX Measures Used

```dax
Total Sales = SUM('Global_Superstore2'[Sales])

Total Profit = SUM('Global_Superstore2'[Profit])

Profit Margin % = DIVIDE([Total Profit], [Total Sales]) * 100

Total Orders = DISTINCTCOUNT('Global_Superstore2'[Order ID])

Avg Discount % = AVERAGE('Global_Superstore2'[Discount]) * 100
```

---

## Key Business Insights

- **Tables sub-category is loss-making** — negative profit despite reasonable sales volume, suggesting pricing or discount strategy needs review
- **Discount abuse is killing margin** — the scatter plot on Page 2 shows a clear negative correlation between average discount rate and profit, particularly in Office Supplies
- **Standard Class dominates shipping** — 7.58M in sales vs 0.67M for Same Day, suggesting an opportunity to upsell premium shipping
- **Technology drives the most profit** — $663K total profit vs $285K for Furniture, despite similar sales volumes
- **Top 10 customers account for a disproportionate share of revenue** — Tom Ashbrook and Tamara Chand lead, suggesting key account risk if either churns

---

## Dataset

**Source:** [Global Superstore Dataset](https://www.kaggle.com/datasets/apoorvaappz/global-super-store-dataset) — Kaggle

**Coverage:** 999+ orders across 147 countries, 3 product categories, 17 sub-categories, 4 market regions

**Key columns used:** Order ID, Order Date, Ship Date, Ship Mode, Customer Name, Segment, Country, Market, Region, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit, Shipping Cost, Order Priority

---

## Project Structure

```
Global-Retail-Intelligence/
│
├── Global Retail Intelligence.pbix
├── README.md
│
├── screenshots/
│   ├── page1.png
│   ├── page2.png
│   └── page3.png
│
└── dataset/
    └── Global_Superstore2.csv
```

---

## Business Questions Answered

- Which markets and countries generate the highest sales and profit?
- Which product sub-categories are generating losses despite high sales volume?
- Does discounting actually increase profit — or does it destroy it?
- Who are the top 10 customers by revenue, and how concentrated is that risk?
- Which products should be prioritised, repriced, or discontinued based on profit performance?
- How has category performance shifted year on year from 2011 to 2014?
- Which shipping modes are being used most, and is there a cost-efficiency opportunity?

---

## How to Use

1. Download the `.pbix` file
2. Open in Power BI Desktop (free download from Microsoft)
3. Use the **Order Date** dropdown slicer to filter by year
4. Use the **Category** and **Segment** slicers to isolate specific product lines or customer segments
5. On Page 2, hover over the scatter plot dots to see which sub-categories have the worst discount-to-profit ratio
6. On Page 3, click the **+** button on the Decomposition Tree to drill from Total Profit into Category, then Sub-Category, then individual Customer Names

---

## Author

**Suriya Prasath Parameswaran**
Data Analyst | Power BI | Python | SQL | DAX | Machine Learning

[GitHub](https://github.com/) · [LinkedIn](https://linkedin.com/)

---

*Built as part of a data analyst portfolio. Dataset sourced from Kaggle under public licence.*
