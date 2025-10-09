# World Bank Sustainable Development Bond (SDB) Analysis

Python script exploration of bond market conditions for World Bank Sustainable Development Bonds (SDBs) using AAA corporate spreads and Treasury yield curve slope as proxies for funding costs.



## Focus
- AA Corporate vs Treasury Spreads(2020–2025)
- Yield Curve Dynamics (10Y–5Y Treasury slope) 
- Percentile ranking, range and volatility of current market conditions
- Funding implications for SDB issuance


##  Methodology
- **Data Source**: FRED API (Federal Reserve Economic Data)
- **Time Period**: Jan 2020-Sep 2025 (69 months)
- **Series**: 
  - `DGS10` - 10-Year Treasury Yield
  - `DGS5` - 5-Year Treasury Yield  
  - `AAA` - Moody's AAA Corporate Bond Yield
- **Frequency**: Month-end aligned data
- **Analysis Steps**:
  1. Fetch data from FRED and align monthly.
  2. Compute AAA spread: AAA Corporate Yield – 10Y Treasury.
  3. Compute Yield Curve slope: 10Y Treasury – 5Y Treasury.
  4. Calculate percentiles of current values relative to 2020–2025.
  5. Compute volatility and summarize funding environment implications.



## Findings (as of October 2025)
- **AAA Spread**: 1.090% (109 bps) — 49th percentile 
- **Yield Curve**: 0.458% (45.8 bps) — 80th percentile 
- **Market Regime**: Moderate spreads, steep yield curve (based on 2020–2025 percentile)  
- **Implication**: Typical funding costs; favors longer-term issuance



## Limitations
1. **Temporal Scope**
   - Limited to post-Covid era: 2020–2025 (69 months)
   - Percentiles reflect only post-COVID monetary regime
   - Excludes pre-2020 historical extremes (e.g., 2008 crisis)
2. **Proxy Data**
   - AAA corporate yields approximate actual World Bank bond yields ((typically 10-20 bps lower due to supranational premium))
3. **Volatility Context**
   - Spread volatility captures COVID-era market stress
   - Pre-2020 volatility regimes are not represented
4. **Percentile Basis**
   - Rankings relative to recent period only, not long-term historical norms



## Visualizations
Include plots generated in the notebook:  
- AAA Spread over 10Y Treasury (2020–2025)  
- Yield Curve Slope: 10Y–5Y Treasury (2020–2025)  





#### Prerequisites:
- Python 3.12 
- Set FRED_API_KEY environment variable
- Required packages:
```bash
pip install pandas matplotlib fredapi

