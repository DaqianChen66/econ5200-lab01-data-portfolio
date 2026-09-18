# econ5200-lab01-data-portfolio
Daqian Chen
# Data Quality Profiling — Big Mac Index

## Objective

This project examines data quality and measurement issues in The Economist's Big Mac Index, with a focus on PPP calculations, missing-data bias, and panel-data structure.

## Methodology

- Diagnosed and corrected an error in the PPP valuation calculation.
- Compared complete-panel estimates with estimates using all available observations.
- Identified survivorship bias caused by dropping countries with incomplete time series.
- Measured the direction and magnitude of the resulting bias.
- Built a `profile_dataframe()` function to summarize:
  - Number of units and time periods
  - Data structure
  - Number of complete units
  - Whether the panel is balanced
  - Missing-value percentages by column

## Key Findings

- The original PPP calculation used the wrong numerator and denominator, which reversed the economic interpretation of currency valuation.
- Restricting the data to complete-panel countries biased the average Big Mac price upward.
- The complete-panel average was approximately **$0.081 (2.1%) higher** than the all-available average.
- The complete-panel estimate was higher in **33 of 45 periods**.
- The dataset contains **57 units and 45 periods** and is an **unbalanced panel**.
- Only **25 units** have observations in every period.
- **7 columns** have more than 10% missing values.

## Conclusion

This lab demonstrates that correct arithmetic alone is not enough for reliable economic analysis. Data selection, missing observations, and panel structure can materially affect results. Diagnosing these issues before modeling helps produce more transparent and defensible economic conclusions.
