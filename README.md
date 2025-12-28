# Cycle Stock Availability Optimization (US & Canada)

This project rebuilds a multi-year, Excel-based cycle stock dispatch and availability analysis in Python to create a transparent, reproducible, SLA-driven view of service performance across U.S. and Canadian distribution operations.

The analysis focuses on availability rather than speed alone and explicitly accounts for real operating constraints such as cutoff times and weekends.

---

## Objective

Assess and materially improve cycle stock availability across U.S. and Canadian distribution operations by replacing static Excel reporting with SLA-driven, reproducible analytics, while stabilizing planning and execution in the absence of a fully functional system solution.

---

## Scope

- Timeframe: **January 2023 through March 2025**
- Inventory scope: **Cycle stock only (Move Codes 1–3)**
- Exclusions: Non-stock, exception, and irregular items

This period captures pre-intervention instability, corrective actions, and sustained performance improvement.

---

## Operating Context

At the outset of the analysis:

- The **D365 demand planning function was not operationally usable**
- **Poor master data quality** prevented reliable system-driven forecasting
- Replenishment execution from the **European Global Distribution Center (GDC)** lacked consistent performance accountability
- Service performance relied heavily on static Excel summaries

To restore control:

- An **interim Excel-based demand planning and forecasting model** was implemented
- A structured **master data cleanup and governance process** was established
- **Delivery performance metrics were formalized and enforced** with the European GDC

These actions formed the foundation for the measured improvements.

---

## SLA Definitions

### Shared Operational Rules (US and Canada)

The following rules apply to both regions:

- Orders placed **after 2:00 p.m. on Thursday** may still be on time if shipped on **Monday**
- Orders placed on **Friday** may still be on time if shipped on **Monday**
- **Weekend** orders receive their SLA clock starting **Monday morning**

This prevents artificial penalties caused by non-working days.

### United States

- Baseline SLA: **Ship within 24 hours** of sales order creation (in-stock items)

### Canada

- Baseline SLA: **Ship within 2 calendar days** from sales order creation to warehouse dispatch

---

## Key Metric

**Supply Chain Availability**

Defined as:

Shipped-on-time order lines ÷ total demand lines

Calculated monthly and segmented by move code to preserve service-class integrity and avoid misleading blended averages.

---

## Results Summary

### United States

- By **March 2025**, cycle stock availability exceeded **86% across all move codes**
- **Priority items (Move Code 1)** consistently exceeded **90% availability**
- From 2023 to 2025, **deseasonalized average dispatch time improved by approximately 53% overall**
  - Move Code 2 improved approximately 58%
  - Move Code 3 improved approximately 67%
- Early 2024 performance deterioration highlighted the limits of the initial planning approach
- A second, more disciplined planning iteration combined with stronger master data governance drove sustained improvement in 2025

### Canada

- Strong availability achieved under a **stricter baseline SLA**
- Lower volatility and earlier stabilization than the U.S.
- From 2023 to 2025:
  - **Deseasonalized dispatch performance improved approximately 39%**
  - **January–February seasonal delays improved approximately 58%**
- Stability reflects lower volume, single-warehouse execution, and reduced exposure to upstream disruption

---

## Seasonal Findings

- January–February seasonality was the primary driver of inflated annual averages
- Canada showed a steady seasonal recovery from 2023 to 2025
- The U.S. experienced its weakest seasonal performance in early 2024 due to:
  - Poor GDC replenishment execution
  - Limited effectiveness of the initial planning solution
- Post-intervention enforcement materially reduced seasonal volatility in 2025

---

## Key Takeaways

- Improvements were driven by **planning maturity, data governance, and execution discipline**, not inventory inflation
- Interim planning solutions can outperform enterprise systems when governance is strong
- SLA-aware segmentation prevented misleading conclusions
- Structural network differences materially influence service outcomes

---

## Repository Contents

### Notebooks

- `notebooks/us_cycle_stock_analysis.ipynb`
- `notebooks/ca_cycle_stock_analysis.ipynb`

### Outputs

- `outputs/us/` – availability trend and month-over-month charts
- `outputs/ca/` – availability trend and month-over-month charts

### Executive Summary

- `executive_summary/Cycle_Stock_Availability_Executive_Summary.pdf`

---

## How to Run

1. Install dependencies:
   - pandas
   - matplotlib
2. Open either notebook and run all cells top to bottom

Raw data files are intentionally excluded. The framework can be reused with equivalent column structures and SLA logic.

---

## Why This Matters

This project demonstrates how disciplined, SLA-driven supply chain analytics can restore operational control and convert instability into sustained, defensible performance improvements, even when enterprise systems are not fully functional.
