# FOMC Market Reaction (Event Study)

## Goal
Measure how financial markets react around FOMC announcements using an event-study framework.

## Data
- S&P 500 prices (log returns)
- Treasury yields: DGS2, DGS10 (daily changes)
- VIX (daily changes)
- FOMC meeting/announcement dates

## Method
1. Construct event-time index k = -5…+5 around each FOMC date
2. Compute average paths (AAR/CAR0)
3. Run event-time dummy OLS:
   - y_t = α + Σ β_k * 1{k} + ε_t
   - Baseline: k = -1
   - Robust SE: HC1

## Key Findings (Interpretation)
- **S&P 500:** Only k=2 shows statistical significance (p<0.05). Most other days are not significant → weak average effect in this sample.
- **2Y / 10Y / VIX:** No strong consistent significant event-time pattern at 5% level in this run.
- **Pre-trends check (Wald test on k<0):** p-values are large → no evidence of systematic pre-event drift (good sign).

## Outputs
- Coefficient plots: `figures/`
- OLS event-time table: `output/project1_event_ols_table.csv`
- Notebook: `notebooks/01_build_master.ipynb`

## How to Run
Open the notebook and run cells top-to-bottom.
