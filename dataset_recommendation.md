# Recommended Dataset: `SupplyChain Dataset.csv`

We should work on **`SupplyChain Dataset.csv`** for the Python data visualization presentation outlined in `READme.md`.

---

## Quick Comparison

| Criterion | `SupplyChain Dataset.csv` (Winner) | `Ecommerce Data Set.xlsx` |
| :--- | :--- | :--- |
| **Size** | **1,500 rows, 24 columns** (2024–2025) | 119 rows, 11 columns (2025 only) |
| **Data Quality** | 0 missing values, 0 duplicates, valid dates | 0 missing values, 0 duplicates |
| **Multi-level Hierarchies** | Clean 2-level trees (`Customer Region` → 27 `Countries`; `Product Category` → 25 `Products`) | Only 1 tree (`Category` → 24 `Products`), very sparse (some products have 1–2 rows) |
| **Negative Values / Deltas** | Yes (`Cancelled` orders = `-$7,771` profit; MoM profit goes up and down) | No negative profit (`min = $1.51`); waterfall only goes down |
| **Cross-tab Density** | Dense (e.g., `Transportation Mode` × `Order Status`, ~370+ rows per mode) | Too sparse (`Category` × `Region` has cells with just 1 order) |
| **Python Workflow Fit** | Raw `.csv` ready for `pandas` + `matplotlib`/`seaborn`/`plotly` | Already has 5 pre-built Excel chart sheets (including `Line Chart`, which is not in `README.md`) |

---

## Why `SupplyChain Dataset.csv` Fits Every Chart in `README.md`

Since `README.md` focuses on **explaining *why* each chart type is chosen and how they differ**, `SupplyChain Dataset.csv` gives clear, distinct visual stories for all required charts:

### 1. Bar Charts
* **Vertical Bar:** `Total Profit` by `Product Category` (5 short labels with huge contrast: Furniture `$3.04M` vs. FMCG `$226.7K`).
* **Horizontal Bar:** `Total Cost` or `Orders` by `Customer Country` (27 countries) or `Product Name` (25 items) — clearly shows *why* horizontal bars solve long labels and many categories.
* **Grouped (Clustered) Bar:** Average `Delivery Time Days` or `Total Cost` across `Product Category` × `Transportation Mode` (`Air`, `Rail`, `Road`, `Sea`) for side-by-side comparison.
* **Stacked Bar:** `Total Profit` by `Customer Region` stacked by `Product Category` to show both regional totals and category makeup.
* **100% Stacked Bar:** `Order Status` share across `Transportation Mode` — immediately highlights reliability differences (`Air` is `89.7%` Delivered / `0.5%` Delayed vs. `Sea` at `76.8%` Delivered / `10.7%` Delayed).
* **Waterfall Chart:** Monthly `Profit` changes (shows both **positive gains and negative drops**, e.g., Aug→Sep 2025 `+$215.6K`, Apr→May 2025 `-$146.4K`) or `Profit` by `Order Status` (`Delivered` + `In Transit` + `Delayed` minus `Cancelled` loss of `$7.8K` = Total Net Profit).

### 2. Bar Chart vs. Histogram
* With **1,500 orders**, continuous variables like `Delivery Time Days` (1–25 days, skew `0.83`), `Total Cost` (skew `1.95`), and `Profit` (skew `2.17`) produce smooth, right-skewed histograms.
* This makes the 4 key differences (`Data type`, `No gaps`, `Numeric order`, `Distribution shape`) unmistakable compared to 119 sparse rows.

### 3. Pie Charts
* **Standard Pie:** `Order Status` (4 clean slices: Delivered `82.4%`, In Transit `8.2%`, Delayed `5.9%`, Cancelled `3.5%`).
* **Donut:** `Transportation Mode` or `Customer Region` share (4–5 slices) with total orders/profit in the center ring.
* **Sunburst:** `Customer Region` (5) → `Customer Country` (27) or `Product Category` (5) → `Product Name` (25) — every leaf has solid counts (36–117 orders per country), unlike Ecommerce where leaf products drop to 1 order.
* **Polar Area Pie:** Monthly `Profit` across 12 months (`$404.6K` in Nov to `$783.0K` in Apr) or `Product Category` `Profit` — strong magnitude differences make radius encoding clear.

---

## Why Not `Ecommerce Data Set.xlsx`?
1. **Too small (`119` rows):** Splitting by 2 categories (`Category` × `Region`) or 24 products leaves cells with `1–2` rows, making Grouped/100% Stacked Bars, Histograms, and Sunburst charts weak.
2. **Already pre-solved in Excel:** It already includes Excel-built `Bar`, `Pie`, `Line`, `Histogram`, and `Waterfall` sheets — and lacks the multi-level/proportional depth needed for `100% Stacked`, `Horizontal`, `Sunburst`, and `Polar Area` charts in Python.
