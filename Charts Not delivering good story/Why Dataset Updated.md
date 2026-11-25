### Dataset Update Rationale (`SupplyChain Dataset.csv`)

While the original `SupplyChain Dataset.csv` (`1,500` rows, `24` columns) had no missing or duplicate values, several fields were uniformly distributed—hiding the patterns needed to demonstrate why each chart type is used. Three targeted updates were made while preserving all formulas (`Total Cost = Order Quantity × Unit Price`, `Delivery Date = Shipment Date + Delivery Time Days`, `0` nulls):

1. **Realistic Transportation Mode Shares (Donut & Bar Charts)**
   - **Before:** All 4 modes were nearly identical (~25% each: Air `25.3%`, Road `25.3%`, Rail `25.0%`, Sea `24.4%`).
   - **After:** **Road `44.0%` (660)**, **Sea `28.0%` (420)**, **Air `18.0%` (270)**, **Rail `10.0%` (150)**.
   - **Why:** Eliminates flat equal slices and clearly highlights dominant vs. niche shipping channels.

2. **Clearer Year-over-Year Profit Bridge (Waterfall Chart)**
   - **Before:** 2024 (`$3.73M`) to 2025 (`$3.52M`) differed by only `-5.6%`, making category steps barely visible (`-$16K` to `+$62K`).
   - **After:** **`$2.60M` (2024) → `$4.05M` (2025) (`+55.8%`)**, driven by **Furniture (`-$0.70M`)** and **Apparel (`-$0.30M`)** declining, offset by **FMCG (`+$0.25M`)**, **Healthcare (`+$0.80M`)**, and **Electronics (`+$1.40M`)**.
   - **Why:** Makes both negative and positive drivers immediately visible so first-time viewers understand how Waterfall charts explain change.

3. **Sea Freight Delay Bottleneck (100% Stacked Bar & Pie Charts)**
   - **Before:** All modes had similar delivery rates (`76.8%–89.7%` Delivered; Sea only `10.7%` Delayed), showing no clear problem mode.
   - **After:** **Sea** carries **`45.0%` Delayed** (`38.1%` Delivered) vs. **Rail (`18.0%` Delayed)**, **Road (`7.0%` Delayed)**, and **Air (`1.1%` Delayed, `91.1%` Delivered)**—raising overall delays to **`17.7%`** (`265` orders).
   - **Why:** Connects the **Pie Chart** (`17.7%` Delayed overall) directly to the **100% Stacked Bar** (proving **Sea** is the delay bottleneck regardless of order volume).