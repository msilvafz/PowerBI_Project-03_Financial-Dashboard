# 📊 Financial Dashboard — Cash Flow, Expense Classification & Departments

Dashboard built in **Microsoft Power BI** to track **cash inflows and outflows**, consolidate **financial KPIs** (Revenue, Expenses, Balance), and break down **expenses by classification and by department**.  
Data preparation and integration via **Power Query**, simple modeling, and **native visual aggregations**.

---

## ✨ Highlights
- Executive view of **cash flow** and **KPIs**.
- Detail by **expense classification** and **department**.
- Slicers for **Year/Month** and **Department**.
- Consistent cool-tone palette (purple–green–blue) with standardized numeric styling for readability.

---

## 📢 About
An **executive + operational** dashboard covering trend analysis, consolidated totals, and expense composition.  
Built from **multiple CSVs** (a folder of extracts) and a **departments table**, following best practices in **data cleaning, modeling, and visual design** to ensure **clarity and consistency**.

---

## 🎯 Objectives
- **Trend:** Visualize the evolution of **Inflows vs. Outflows** and identify seasonality.
- **Overview:** Highlight **Total Revenue**, **Total Expenses**, and **Balance** based on current filters.
- **Composition:** Understand **top expense classifications** and **departments with the largest impact**.
- **Exploration:** Enable slicing by **Year/Month** and **Department** using visual aggregations.

---

## ⚙️ Process (ETL & Modeling)

**Data integration**
- 📁 Folder of **extract CSVs** (combined in Power Query).
- 📄 **Departments** table (CSV/Excel) for enrichment and relationships.

**Cleaning in Power Query**
1. Import **Folder** and **Combine** CSVs (Extracts).
2. Remove **Origin** column (unused).
3. Clean **Cost Center** by removing the “CC” prefix  
   *(Transform ▸ Extract ▸ Text After Delimiter “ ”)*.
4. Set **Cost Center** as **Whole Number**.
5. Import **Departments**.
6. Enforce data types (`Date`, `Amount`, text) and validate quality.

**Modeling**
- **Many-to-one** relationship: `Extracts (fact)` ➜ `Departments (dim)` via **Cost Center**.
- Functional slicers by **Year/Month** and **Department**.
- KPIs and visuals configured with **Sum of `Amount`** and report filters.

---

## 🎨 Color Guide (Design System)

- **Principles:** cool palette (purple–green–blue); single color for numbers; subtle finishing.
- **Core:** Inflows `#16C99E` • Outflows `#5F21CE` • Numbers `#2E2E2E`.
- **Donut (Departments):** `#5F21CE`, `#16C99E`, `#3A7DFF`, `#A678FF`, `#28E0B5`.
- **Bars (Expense Classification):** `#5F21CE`, `#16C99E`, `#3A7DFF`, `#A678FF`, `#7CA8FF`.
- **Finishing:** white separator `#FFFFFF` 1px (opacity ~45–50%); titles/labels follow the dashboard’s typography.

---

## 🔧 How to Run

1. Open **`Dashboard/Dashboard_Financeiro.pbix`** in **Power BI Desktop**.
2. If needed, update the **data folder path** in *Transform Data ▸ Source*.
3. **Refresh** the data.
4. Use the **Year/Month** and **Department** slicers to explore.

---

## 🗂️ Project Structure

- **/data** → analysis data  
  - `/data/Movimentacoes/` (movement files)  
  - `Setores.xlsx` (departments lookup)

- **/dashboard** → main Power BI file  
  - `Dashboard_Financeiro.pbix` (model & visuals)  
  - `Background_Dashboard.svg` (background artwork)

---

## 🧰 Stack
- **Microsoft Power BI Desktop**
- **Power Query** (ETL/transformations)
