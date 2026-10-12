<img width="1920" height="1080" alt="filter_panel png" src="https://github.com/user-attachments/assets/bfbb17c2-ae94-43fa-983c-cacec33ecacc" /><div align="center">

# -- ! Superstore Sales Dashboard ! --
### *Power BI Practical Report 1 (PR 1) — Sales, Profit & Regional Performance*

[![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Power Query](https://img.shields.io/badge/Power%20Query-Data%20Cleaning-CC0000?style=for-the-badge&logo=powerbi&logoColor=white)](https://powerbi.microsoft.com/)
[![Dataset](https://img.shields.io/badge/Dataset-Superstore%20Sales-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
[![Visuals](https://img.shields.io/badge/Visuals-KPI%20%7C%20Bar%20%7C%20Slicers-4A4A4A?style=for-the-badge&logo=powerbi&logoColor=white)](https://powerbi.microsoft.com/)

<br/>

> *"Numbers become decisions when they are shown clearly."*

</div>

---

## 📋 Table of Contents

- [📌 Overview](#-overview)
- [🖼️ Dashboard Preview](#️-dashboard-preview)
- [🎯 Project Objectives](#-project-objectives)
- [🏗️ Project Structure](#️-project-structure)
- [🗂️ Dataset](#️-dataset)
- [🔧 Power Query Transformations](#-power-query-transformations)
- [📊 Report Pages & Visuals](#-report-pages--visuals)
- [🎛️ Slicers, Filters & Interactions](#️-slicers-filters--interactions)
- [🎨 Theme & Formatting](#-theme--formatting)
- [✅ Tasks Completed](#-tasks-completed)
- [📈 Key Insights](#-key-insights)
- [🚀 How to Open This Project](#-how-to-open-this-project)
- [🛠️ Tools Used](#️-tools-used)
- [🎥 Video Explanation](#-video-explanation)
- [📄 License](#-license)
- [👤 Author](#-author)
- [🙏 Acknowledgements](#-acknowledgements)

---

## 📌 Overview

**Superstore Sales Dashboard** is a Power BI project built on the **Sample Superstore Sales dataset**. The raw data is cleaned in **Power Query Editor**, loaded into the data model, and presented as an interactive two-page report with **KPI cards, bar charts, slicers, filters, and visual interactions**.

The dashboard answers questions such as:
- How much total sales and profit does the store make?
- Which product **categories** and **sub-categories** sell the most?
- Which **regions** are the most and least profitable?

---

## 🖼️ Dashboard Preview

<img width="1257" height="712" alt="Screenshot 2026-10-12 134159" src="https://github.com/user-attachments/assets/c4237bbd-820c-493b-b321-79c19fed0001" />


*Page 1 — Sales Dashboard (unfiltered view, Innovate theme).*

---

## 🎯 Project Objectives

- Connect Power BI Desktop to a CSV data source
- Clean and shape the data using Power Query (8+ transformation steps)
- Build KPI cards and formatted bar charts
- Add slicers, page-level and visual-level filters
- Configure cross-filtering between visuals
- Apply a built-in theme and a consistent 16:9 layout

---

## 🏗️ Project Structure

```
📦 PR1-Superstore-Sales-Dashboard/
│
├── 📁 dataset/
│   └── 📄 superstore_sales_dataset.csv      ← Source data
│
├── 📁 screenshots/                          ← Power Query and dashboard screenshots
│
├── 📁 theme/
│   └── 📄 theme.json                        ← Exported report theme (Innovate)
│
├── 📊 Superstore_Sales_Dashboard.pbix       ← Power BI project file
│
└── 📄 README.md                             ← Project documentation
```

---

## 🗂️ Dataset

| Detail | Value |
|--------|-------|
| **Name** | Sample Superstore Sales Dataset |
| **Source** | [Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) |
| **Format** | CSV |
| **Original size** | ~9,994 rows × 21 columns |
| **After cleaning** | **8,211 rows × 19 columns** |

**Key columns:** Order Date, Ship Date, Ship Mode, Segment, City, State, Region, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit.

---

## 🔧 Power Query Transformations

| Step | Transformation | Details |
|------|----------------|---------|
| 1️⃣ | **Promote headers** | First row used as column headers |
| 2️⃣ | **Rename columns** | `Sub-Category` → `Sub Category`, `Product Name` → `Product`, `Customer Name` → `Customer` |
| 3️⃣ | **Change data types** | Order Date and Ship Date → Date (US locale), Sales, Discount and Profit → Decimal Number, Quantity → Whole Number |
| 4️⃣ | **Remove nulls** | Blank rows removed; Sales and Profit checked for nulls |
| 5️⃣ | **Filter rows** | Kept only **Consumer** and **Corporate** segments (Home Office removed) |
| 6️⃣ | **Duplicate column** | Copy of `Order ID` created |
| 7️⃣ | **Split column** | Copy split by `-` to extract the order region code, renamed `Order Region Code`; extra split columns removed |
| 8️⃣ | **Remove columns** | Removed `Row ID`, `Country` and `Postal Code` |
| 9️⃣ | **Close & Apply** | Cleaned data loaded into the model |

> Result: **21 columns → 19 columns** and **8,211 rows** after cleaning.

<img width="1851" height="802" alt="power query editor" src="https://github.com/user-attachments/assets/9d9dfd54-fe39-4d79-aaf7-2021e00afce3" />


<img width="1920" height="1080" alt="applied steps png" src="https://github.com/user-attachments/assets/f4758c10-63c7-46a4-b2d8-bd794f358542" />


---

## 📊 Report Pages & Visuals

### 📄 Page 1 — Sales Dashboard

| Visual | Fields | Purpose |
|--------|--------|---------|
| 💰 **KPI Card** | Sum of Sales | Total sales |
| 📈 **KPI Card** | Sum of Profit | Total profit |
| 📦 **KPI Card** | Sum of Quantity | Total units sold |
| 🏷️ **KPI Card** | Average of Discount | Average discount |
| 📊 **Clustered Bar** | Category × Sales | Total Revenue by Product Category |
| 📊 **Clustered Bar** | Region × Profit | Profit by Region |
| 📊 **Clustered Bar** | Sub Category × Sales | Top 5 Sub Categories by Sales |

### 📄 Page 2 — Order Details

A detailed **table visual** (`Detailed Order Data`) showing Order ID, Order Date, Customer, Segment, Region, Category, Sub Category, Product, Sales, Quantity, Discount and Profit.

> ℹ️ The page-level `Ship Mode` filter is applied only to Page 1. Because of this, the totals in the Order Details table cover all ship modes and are larger than the KPI cards on Page 1.

<img width="1920" height="1080" alt="order_details_page" src="https://github.com/user-attachments/assets/f50185b8-1535-44fe-ae40-34b1fb2e195f" />


<img width="1917" height="942" alt="fields_pane" src="https://github.com/user-attachments/assets/e6658af5-945b-4aa8-84d9-de5c974eb4c5" />

---

## 🎛️ Slicers, Filters & Interactions

### 🎚️ Slicers

| Slicer | Field | Style |
|--------|-------|-------|
| 🌍 Region | `Region` | Tile |
| 🗂️ Category | `Category` | Dropdown |

<img width="1920" height="1080" alt="region_slicer_test png" src="https://github.com/user-attachments/assets/8199386f-a338-4210-899d-f0043535eb43" />

### 🔍 Filters

| Scope | Filter |
|-------|--------|
| **Page-level** | `Ship Mode` = Standard Class, Second Class |
| **Visual-level** | Top 5 `Sub Category` by Sales |

<img width="1920" height="1080" alt="filter_panel png" src="https://github.com/user-attachments/assets/48ed2a81-de87-4705-baca-e784449fb6a5" />


### 🔗 Visual Interactions

| Source Visual | Target | Interaction |
|---------------|--------|-------------|
| Total Revenue by Product Category | Profit by Region | Filter |
| Total Revenue by Product Category | Top 5 Sub Categories by Sales | Filter |
| Total Revenue by Product Category | KPI Cards | None |
| Profit by Region | Total Revenue by Product Category | Highlight |
| Profit by Region | Top 5 Sub Categories by Sales | Highlight |
| Top 5 Sub Categories by Sales | Profit by Region | Filter |
| Top 5 Sub Categories by Sales | Total Revenue by Product Category | None |

<img width="1920" height="1080" alt="cross_filter_test" src="https://github.com/user-attachments/assets/b499d809-9ed1-4678-93cf-204701336322" />


---

## 🎨 Theme & Formatting

- 🖌️ **Theme:** Innovate (built-in Power BI theme), exported as `theme/theme.json`
- 📐 **Page size:** 16:9 (1280 × 720)
- 🎨 **Canvas background:** `#F5F5F5`
- 🔴 **Primary chart color:** `#CC0000`  |  ⚫ **Secondary chart color:** `#4A4A4A`
- 🏷️ **Data labels:** 10 pt, display units in K/M
- 🔤 **KPI values:** 28 pt, bold
- 🧭 **Layout:** Snap to Grid and Gridlines enabled, visuals aligned
- 🚫 **Gridlines:** Vertical gridlines removed from bar charts

<img width="1920" height="1080" alt="theme_applied png" src="https://github.com/user-attachments/assets/3e380c7f-7df8-470a-8912-3e00a12a6c56" />


---

## ✅ Tasks Completed

| # | Task | Status |
|---|------|--------|
| 1 | Connect to data source | ✅ |
| 2 | Explore Power Query interface | ✅ |
| 3 | Table transformations (8+ steps) | ✅ |
| 4 | Explore Fields pane | ✅ |
| 5 | Explore Visualizations pane | ✅ |
| 6 | Create 4 KPI cards | ✅ |
| 7 | Create bar charts | ✅ |
| 8 | Format visuals (titles, colors, labels) | ✅ |
| 9 | Add slicers | ✅ |
| 10 | Configure filter panel | ✅ |
| 11 | Report page formatting + second page | ✅ |
| 12 | Apply theme | ✅ |
| 13 | Configure visual interactions | ✅ |

---

## 📈 Key Insights

> Values below are from the unfiltered **Sales Dashboard** page (Consumer and Corporate segments, Standard Class and Second Class shipping).

| KPI | Value |
|-----|-------|
| 💰 **Total Sales** | 1.50M |
| 📈 **Total Profit** | 178.57K |
| 📦 **Total Quantity** | 25K |
| 🏷️ **Average Discount** | 0.16 (about 16%) |

- 📊 **Categories are almost equal in sales:** Technology (502.96K), Furniture (502.25K) and Office Supplies (491.6K).
- 🌍 **West is the most profitable region** (65.7K), about **2.6 times** Central, which is the least profitable (25.17K).
- 🪑 **Top sub-categories:** Chairs (216K) and Phones (209K) lead, followed by Storage, Tables and Binders. The top 5 together make up about **57%** of total sales.
- 💹 **Overall profit margin** is about **11.9%** (Profit ÷ Sales).

---

## 🚀 How to Open This Project

1. Install **Power BI Desktop** (Windows).
2. Clone or download this repository.
3. Open `Superstore_Sales_Dashboard.pbix`.
4. If the data does not load, update the source path: **Home → Transform data → Data source settings → Change Source**, then select `dataset/superstore_sales_dataset.csv` from your computer.
5. Click **Refresh**.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| 📊 **Power BI Desktop** `[version]` | Data modeling, visuals, and report design |
| 🔧 **Power Query Editor** | Data cleaning and transformation |
| 🔀 **Git / GitHub** | Version control and submission |

---

## 🎥 Video Explanation

| Item | Detail |
|------|--------|
| 🔗 **Video URL** | `[Paste your unlisted YouTube / Google Drive link here]` |

---

## 📄 License

This project is licensed under the **MIT License** — free to use, modify, and distribute with attribution.

---

## 👤 Author

<div align="center">

### Sneha Gupta

**🎓 Role:** BBA Student | Data Analysis Learner\
**📍 Location:** India\
**🛠️ Skills:** Excel · SQL · Python · Power BI

</div>

---

## 🙏 Acknowledgements

- 🏫 **Red & White Skill Education** — For the practical report and guidance
- 📚 [Kaggle — Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) — Source data
- 📊 [Microsoft Power BI Docs](https://learn.microsoft.com/power-bi/) — Official documentation

---

<div align="center">

*Made with ❤️ and ☕ — Last updated: 12 October, 2026*

</div>
