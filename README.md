# econ5200-lab01-data-portfolio
# Data Quality Profiling — Big Mac Index

## Objective

Assess data quality and panel structure in The Economist’s Big Mac Index by diagnosing calculation errors, evaluating missing-data bias, and systematically profiling dataset completeness.

## Methodology

* Diagnosed and corrected a PPP valuation calculation in which the numerator and denominator had been reversed.
* Examined missing observations across countries and time to identify the consequences of restricting the dataset to complete panels.
* Compared average Big Mac prices from the 25 complete-panel countries with averages using all countries available in each period.
* Quantified the resulting survivorship bias across all 45 periods.
* Distinguished between cross-sectional, time-series, and panel data structures and evaluated whether the full panel was balanced.
* Developed `profile_dataframe()` to report dataset shape, number of units and periods, data structure, complete units, balance status, and per-column missing percentages.

## Key Findings

The Big Mac dataset contains **57 units across 45 periods**, but only **25 units have complete observations across every period**, making the full dataset an **unbalanced panel**.

Dropping all incomplete panels removed **32 of 57 units** and introduced measurable survivorship bias. Across the full sample, the complete-panel approach overstated the average Big Mac price by **$0.081, or 2.1%**, on average. The complete-panel average was higher than the all-available-country average in **33 of 45 periods**.

The missing observations were also not explained by a single pattern. Some countries entered the index later, some stopped being reported, and others contained gaps within otherwise continuing series. This showed that filtering solely for complete panels changes the composition of the sample rather than simply removing random missing observations.

The final data-quality profile identified **7 columns with more than 10% missing values**, reinforcing the importance of evaluating both missing rows in a panel structure and null values within observed rows before conducting economic analysis.
