# Cycle Stock Availability Optimization (US & Canada)

This project rebuilds a multi-year, Excel-based cycle stock dispatch and availability analysis in Python to create a transparent, reproducible, SLA-driven view of service performance across U.S. and Canadian distribution operations.

The original performance analysis and improvement calculations were developed in Excel. The Python rebuild preserves the operating logic and creates a cleaner, repeatable framework for reviewing availability, dispatch performance, and seasonal delay reduction.

The analysis focuses on availability rather than speed alone and explicitly accounts for real operating constraints such as cutoff times, weekends, replenishment handoffs, and regional service rules.

## Objective

Assess and materially improve cycle stock availability across U.S. and Canadian distribution operations by replacing static Excel reporting with SLA-driven, reproducible analytics, while stabilizing planning and execution in the absence of a fully functional system solution.

## Scope

- **Timeframe:** January 2023 through March 2025
- **Inventory scope:** Cycle stock only (Move Codes 1-3)
- **Exclusions:** Non-stock, exception, and irregular items

This period captures pre-intervention instability, corrective actions, and sustained performance improvement.

## Operating Context

At the outset of the analysis:

- The D365 demand planning function was not operationally usable
- Poor master data quality prevented reliable system-driven forecasting
- Replenishment execution from the European Global Distribution Center (GDC) lacked consistent performance accountability
- Service performance relied heavily on static Excel summaries

To restore control:

- An **interim Excel-based demand planning and forecasting model** was implemented
- A structured **master data cleanup and governance process** was established
- **Delivery performance metrics were formalized and enforced** with the European GDC
- Dedicated **dispatch and collection time slots were agreed with the European 3PL and freight carrier** to stabilize replenishment flow, reduce handoff variability, and restore delivery reliability

These actions formed the foundation for the measured improvements.

## SLA Definitions

### Shared Operational Rules

The following rules apply to both regions:

- Orders placed after 2:00 p.m. on Thursday may still be on time if shipped on Monday
- Orders placed on Friday may still be on time if shipped on Monday
- Weekend orders receive their SLA clock starting Monday morning

This prevents artificial penalties caused by non-working days.

### United States

**Baseline SLA:** Ship within 24 hours of sales order creation for in-stock items.

### Canada

**Baseline SLA:** Ship within two SLA-adjusted days from sales order creation to warehouse dispatch.

## Key Metric

**Supply Chain Availability**

Defined as:

```text
Eligible cycle stock demand lines shipped within SLA / total eligible cycle stock demand lines
```

The metric is calculated monthly and segmented by move code to preserve service-class integrity and avoid misleading blended averages.

## Measurement Notes

- The **32% reduction** represents the blended total North American cycle stock dispatch-time improvement from January 2023 to March 2025
- The **38% U.S. reduction** is a deseasonalized U.S. cycle stock dispatch-time improvement from the 2023 baseline to 2025
- The **25-30% Canada reduction** reflects Canadian cycle stock delay improvement under a stricter SLA
- The **52% seasonal reduction** reflects January-February seasonal dispatch delay improvement across North America from 2023 to 2025
- Seasonal analysis should be viewed specifically against January-February performance, not full-year averages

## Results Summary

### United States

- By March 2025, cycle stock availability exceeded 86% across all move codes
- Priority items (Move Code 1) consistently exceeded 90% availability
- U.S. cycle stock dispatch time reduced by approximately 38%, deseasonalized, versus the 2023 baseline
- Early 2024 performance deterioration highlighted the limits of the initial planning approach
- A second, more disciplined planning iteration, combined with stronger master data governance, drove sustained improvement in 2025

### Canada

- Strong availability was achieved under a stricter baseline SLA
- Performance showed lower volatility and earlier stabilization than the U.S.
- Canadian cycle stock delays reduced by approximately 25-30% versus the 2023 baseline
- Stability reflected lower volume, single-warehouse execution, and reduced exposure to upstream disruption

### North America

- Blended total cycle stock dispatch-time performance improved by approximately 32% from January 2023 to March 2025
- January-February seasonal dispatch delays reduced by approximately 52% across North America from 2023 to 2025
- Inventory health and working capital efficiency improved without relying on inventory inflation

## Seasonal Findings

- January-February seasonality was the primary driver of inflated annual averages
- Seasonal reductions should be assessed by comparing January-February performance from 2023 to January-February performance in 2025
- Canada showed a steady seasonal recovery from 2023 to 2025
- The U.S. experienced its weakest seasonal performance in early 2024 due to poor GDC replenishment execution and the limited effectiveness of the initial planning solution
- Post-intervention enforcement materially reduced seasonal volatility in 2025, contributing to the approximately 52% January-February dispatch delay reduction across North America

## Key Takeaways

- Improvements were driven by planning maturity, data governance, replenishment handoff discipline, and execution accountability, not inventory inflation
- Interim planning solutions can outperform enterprise systems when governance is strong
- SLA-aware segmentation prevented misleading conclusions
- Structural network differences materially influence service outcomes

## Repository Contents

### Notebooks

- `notebooks/us_cycle_stock_analysis.ipynb`
- `notebooks/ca_cycle_stock_analysis.ipynb`

### Outputs

- `outputs/us/` - availability trend and month-over-month charts
- `outputs/ca/` - availability trend and month-over-month charts

### Executive Summary

- `executive_summary/Cycle_Stock_Availability_Executive_Summary.pdf`

## How to Run

Install dependencies:

- `pandas`
- `matplotlib`

Open either notebook and run all cells from top to bottom.

Raw data files are intentionally excluded. The framework can be reused with equivalent column structures and SLA logic.

## Why This Matters

This project demonstrates how disciplined, SLA-driven supply chain analytics can restore operational control and convert instability into sustained, defensible performance improvements, even when enterprise systems are not fully functional.

It also shows how interim planning, master data governance, replenishment handoff discipline, and supplier accountability can stabilize delivery performance without relying on inventory inflation.
