# How Does What We Eat Affect Our Planet?
### An Interactive Scrollytelling Visualization of Food System Emissions

**Natálie Hluší | CS 360 Data Visualization | University of San Francisco | 2026**

**Live site:** https://natyhl.github.io/final-project/

---

## About this project

A scrollytelling web application built with D3.js. As you scroll down the page, four interactive charts appear one at a time in a sticky viewport, each tied to a narrative step card. The project explores how food systems contribute to greenhouse gas emissions and connects that to broader environmental and health data.

---

## How to Run

**GitHub Pages (no setup)**
Just open https://natyhl.github.io/final-project/

---

## Required Files

All files must be in the **same directory**.

| File | Purpose |
|---|---|
| `index.html` | Main scrollytelling page — start here |
| `f1_barchart.html` | Figure 1 — GHG emissions bar chart |
| `f2_small_mul.html` | Figure 2 — Supply-chain small multiples |
| `f3_choropleth.html` | Figure 3 — World CO₂ choropleth map |
| `f4_parallel.html` | Figure 4 — Parallel coordinates |
| `Food_Production_edit.csv` | Data for Figure 1 (`food`, `ghg`, `category`) |
| `Food_Production.csv` | Data for Figure 2 (7 supply-chain stage columns) |
| `CO2emission_by_countries_2000.csv` | Data for Figure 3 (`country`, `code`, `co2`) |
| `water_pollution_disease.csv` | Data for Figure 4 |
| `countries-50m.json` | World map geometry for Figure 3 (TopoJSON) |

---

## Libraries

All loaded — no `npm install` needed.

| Library | Version | Used in |
|---|---|---|
| [D3.js](https://d3js.org) | 7.8.5 | all files |
| [Scrollama.js](https://github.com/russellsamora/scrollama) | 3.2.0 | `index.html` |
| [d3-legend](https://d3-legend.susielu.com) | 2.25.6 | `f1`, `f2`, `f4` |
| [TopoJSON](https://github.com/topojson/topojson) | 3 | `f3_choropleth.html` |
| [Google Fonts](https://fonts.google.com) | — | `index.html` |

---

## Interactions

| Chart | Action | Effect |
|---|---|---|
| **All** | Scroll down/up | Advances or returns through Figures 1 → 4 |
| **Figure 1** | Hover over a bar | Tooltip: food name, GHG value, category |
| **Figure 3** | Hover over a country | Tooltip: country name and CO₂ in billions of tons |
| **Figure 4** | Click and drag on an axis | Brush filter — only matching lines stay colored |
| **Figure 4** | Drag on multiple axes | Filters by all ranges simultaneously |
| **Figure 4** | Click axis without dragging | Clears that brush |

---

## Data Sources and Preprocessing

| Dataset | Source | Changes made |
|---|---|---|
| Food Production Emissions | [Kaggle — S. Vivek](https://www.kaggle.com/datasets/selfvivek/environment-impact-of-food-production) | Added `category` column by hand; saved as `Food_Production_edit.csv` |
| CO₂ Emissions by Country | [Kaggle — M. A. Bhatti](https://www.kaggle.com/datasets/moazzimalibhatti/co2-emission-by-countries-year-wise-17502022) | Filtered to year 2000 with Python/pandas; saved as `CO2emission_by_countries_2000.csv` |
| Water Pollution and Disease | [Kaggle — K. Yadhav](https://www.kaggle.com/datasets/khushikyad001/water-pollution-and-disease) | None — loaded as-is |
| World map geometry | [Natural Earth / world-atlas](https://github.com/topojson/world-atlas) | None — loaded as-is |

---

## Project Structure

```
project/
├── index.html                        ← main page (start here)
├── f1_barchart.html                  ← Figure 1
├── f2_small_mul.html                 ← Figure 2
├── f3_choropleth.html                ← Figure 3
├── f4_parallel.html                  ← Figure 4
├── Food_Production.csv               ← used by f2
├── Food_Production_edit.csv          ← used by f1
├── CO2emission_by_countries_2000.csv ← used by f3
├── water_pollution_disease.csv       ← used by f4
└── countries-50m.json                ← used by f3
```