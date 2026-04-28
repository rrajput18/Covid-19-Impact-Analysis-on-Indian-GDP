# 🦠📉 COVID-19 Impact on Indian GDP — Power BI Analysis

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
  <img src="https://img.shields.io/badge/Domain-Macroeconomics-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Scope-Pan--India-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Pages-4%20Dashboards-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge"/>
</p>

---

## 📌 Project Overview

This project presents a **multi-dimensional Power BI analysis** of how the COVID-19 pandemic reshaped India's macroeconomic landscape. Using a structured star-schema data model (`Fact_India_Economic_Impact`), the report synthesizes state-level and sector-level data to surface the GDP contraction patterns, unemployment shocks, and population-level economic suffering that defined India's pandemic years.

The dashboard goes beyond headline numbers — it dissects **which sectors bled the most**, **which states were hardest hit**, and **how the recovery trajectory looked** through a rich set of KPI cards, trend lines, scatter plots, and pivot matrices — all navigable through an interactive, multi-page report.

---

## 🗂️ Report Architecture — 4 Dashboard Pages

### 📊 Page 1 — Economic Loss Overview
> *The macro lens: aggregate economic damage at a glance*

The entry point of the report. This page anchors the entire analysis with three headline KPI cards:

| Metric | Description |
|---|---|
| **Avg. GDP Loss %** | Average percentage contraction in GDP across sectors and states |
| **Total GDP Loss** | Absolute economic loss aggregated across the analysis period |
| **Avg. Unemployment Change** | Mean shift in unemployment rate — capturing labour market stress |
| **Total Population Affected** | Cumulative count of population exposed to economic disruption |

**Visuals on this page:**
- **Dual-axis Line Chart** — Plots `Avg. GDP Loss %` vs `Avg. Unemployment Change` over time, revealing the lagged correlation between output contraction and job destruction.
- **Clustered Column Chart** — Breaks down `Total GDP Loss by Sector`, exposing which industries (e.g., hospitality, aviation, retail) absorbed disproportionate shocks.
- **Bar Chart** — Ranks `Avg. GDP Loss % by State`, providing a first look at the geographic distribution of economic pain.

---

### 🗺️ Page 2 — State-Wise Impact Analysis
> *The geographic dimension: how India's regions diverged under pressure*

A deep dive into inter-state heterogeneity in economic outcomes. The presence of a **Year slicer** makes this page fully temporal — allowing the analyst to toggle across pandemic years and observe how state vulnerabilities evolved.

**Visuals on this page:**
- **Pivot Table** — Cross-tabulates `State × Sector` against `Avg. GDP Loss %`, enabling granular identification of the worst state-sector intersections.
- **Clustered Bar Chart** — Visualizes `Total Population Affected by State`, quantifying the human scale of the economic crisis per region.
- **Multi-Row Card** — For each state, displays the full set of KPIs: `Avg. GDP Loss %`, `Total GDP Loss`, `Avg. Unemployment Change`, and `Total Population Affected` — serving as a quick comparative scorecard.
- **Year Slicer** — Enables dynamic filtering across the pandemic timeline for all visuals on the page.

---

### 🏭 Page 3 — Sectoral Impact Analysis
> *Industry under the microscope: which sectors fell, which held, and how unemployment tracked output*

This page treats India's economic sectors as the primary unit of analysis, exposing structural vulnerabilities across industries.

**Visuals on this page:**
- **Stacked Column Chart** — Plots `Avg. GDP Loss % by Sector and Year`, making year-over-year sectoral recovery (or further decline) immediately visible.
- **Clustered Column Chart** — Compares `Avg. Unemployment Change by Sector`, revealing sectors where job losses significantly outpaced GDP contraction — a signal of structural labour displacement.
- **Scatter Chart** — Maps `Avg. GDP Loss %` (X-axis) vs `Total GDP Loss` (Y-axis) with sectors as data points. This bivariate view distinguishes sectors that were *relatively* hard hit (high loss %) from those that were *absolutely* hard hit (high total loss) — critical for policy triage.

---

### 🔄 Page 4 — Social & Recovery Factors Analysis
> *Beyond the balance sheet: population stress and the recovery arc*

The final page shifts focus from pure economic metrics to the social and temporal recovery dimensions — asking: *who bore the burden, and when did things start turning around?*

**Visuals on this page:**
- **Scatter Chart** — Plots `State` against `Avg. GDP Loss %`, providing a clean state-level ranking free of sectoral noise.
- **Line + Stacked Column Combo Chart** — Tracks `Avg. GDP Loss % by Sector across Years` in a combo layout that allows simultaneous comparison of trend lines and absolute magnitudes — the most information-dense visual in the report.
- **Pie Chart** — Segments `Population Affected by State`, delivering an intuitive proportional view of which states contributed most to the aggregate human impact figure.
- **KPI Cards (×2)** — Dedicated summary cards for recovery-relevant metrics, anchoring the narrative conclusion of the dashboard.

---

## 🧮 Data Model

The report is powered by a **fact-table-centric** data model:

```
Fact_India_Economic_Impact_Clea
├── Dimensions: State, Sector, Year
└── Measures:
    ├── Avg.GDPLoss%              → Average GDP contraction rate
    ├── TotalGDPLoss              → Absolute GDP loss aggregation
    ├── AvgUnemploymentChange     → Mean unemployment rate delta
    └── TotalPopulationAffected   → Cumulative population impact count
```

The DAX measures are designed for **cross-filter compatibility**, ensuring that slicers (Year, State, Sector) dynamically propagate across all pages via Power BI's native filter context engine.

---

## 📐 Visual Inventory

| Visual Type | Count | Usage |
|---|---|---|
| Card / KPI Card | 6 | Headline metric callouts |
| Clustered Column Chart | 2 | Sector/State comparisons |
| Bar / Clustered Bar Chart | 2 | Ranked state comparisons |
| Line Chart | 1 | Temporal trend overlay |
| Scatter Chart | 2 | Bivariate economic mapping |
| Combo Chart (Line + Column) | 1 | Recovery trend analysis |
| Pivot Table | 1 | State × Sector matrix |
| Multi-Row Card | 1 | Per-state KPI scorecard |
| Pie Chart | 1 | Population share breakdown |
| Slicer | 1 | Year filter |
| Textbox | 4 | Page headers |
| Image | 5 | Branding/decorative assets |
| Action Button | 4 | Navigation between pages |

---

## 💡 Key Insights

1. **Uneven State Impact** — GDP contraction was not uniform across India. States with higher dependency on tourism, construction, and informal labour showed significantly steeper losses than manufacturing-heavy states.

2. **Sector-Level Divergence** — The scatter chart on Page 3 reveals a critical asymmetry: some sectors suffered high *percentage* loss with relatively low absolute totals (smaller base), while others recorded moderate % loss but massive absolute damage due to their scale in the economy.

3. **Unemployment Lagged Output** — The dual-axis line chart on Page 1 suggests that unemployment peaks *lagged* GDP loss peaks — consistent with the economic principle that firms exhaust other cost levers before shedding workers at scale.

4. **Population Burden Concentrated** — The pie chart on Page 4 indicates that a small subset of states account for a disproportionate share of total population economically affected, pointing to geographic inequality in crisis exposure.

5. **Sectoral Recovery Was Non-Linear** — The combo chart on Page 4 captures that recovery across sectors was neither uniform nor monotonic, with some sectors bouncing back sharply in Year 2 while others remained suppressed.

---

## 🛠️ Technical Stack

| Component | Detail |
|---|---|
| **Platform** | Microsoft Power BI Desktop |
| **File Format** | `.pbix` (Power BI Report + Data Model bundle) |
| **Data Model** | Star Schema — single fact table |
| **Query Language** | DAX (Data Analysis Expressions) |
| **Report Theme** | Custom dark theme (CY24SU10 base) |
| **Interactivity** | Cross-filtering, Year slicer, Page navigation buttons |

---

## 🚀 Getting Started

### Prerequisites
- **Power BI Desktop** (free) — [Download here](https://powerbi.microsoft.com/desktop/)
- Windows OS (Power BI Desktop is Windows-only; use Power BI Service on other platforms)

### Steps
```bash
1. Clone or download this repository
2. Open Power BI Desktop
3. File → Open → Select Covid-19_Impact_On_IndianGDP_Analysis.pbix
4. Explore each of the 4 dashboard pages using the navigation buttons
5. Use the Year slicer on Page 2 to filter temporal views
```

---

## 📁 Repository Structure

```
📦 Covid-19-India-GDP-Analysis
 ┣ 📊 Covid-19_Impact_On_IndianGDP_Analysis.pbix   ← Main Power BI report
 ┗ 📄 README.md                                     ← This file
```

---

## 🎯 Use Cases

- **Academic Research** — Macro-economic impact analysis of pandemic shocks on emerging economies
- **Policy Analysis** — Identifying sectors and states requiring targeted fiscal intervention
- **Data Journalism** — Visual storytelling of India's COVID-19 economic narrative
- **Portfolio Showcase** — Demonstrating Power BI data modelling, DAX, and dashboard design skills

---

## 👤 Author

> RAKSHIT RAJPUT.

---

<p align="center">
  <i>Data tells the story the headlines couldn't — one sector, one state at a time.</i>
</p>
