# DRC-Uganda SDG 1-4-8 Tracker 2030

> Tracking Poverty, Education & Decent Work for 2 countries that host me: DRC (home) & Uganda (study)

## The Problem
DRC and Uganda have 78% youth but:
- **SDG 1 - No Poverty:** 79% in DRC live under $2.15/day (World Bank 2023)
- **SDG 4 - Quality Education:** School completion 32% in DRC vs 53% in Uganda
- **SDG 8 - Decent Work:** Youth unemployment 19.2% DRC, 13.3% Uganda

Governments have data but no real-time dashboard for youth.

## What This Project Does
Fetches live data from World Bank API (2015-2024) and visualizes progress to 2030.

### 3 Dashboards
1. **SDG 1 Dashboard:** Poverty headcount, GDP per capita DRC vs Uganda
2. **SDG 4 Dashboard:** Primary completion, literacy rate
3. **SDG 8 Dashboard:** Youth unemployment, vulnerable employment

## Tools
- Python: `wbdata`, `pandas`, `plotly`
- Power BI for final dashboard
- Data Source: World Bank Open Data API
- GitHub Actions: Auto-update monthly

## Code to Fetch Data
```python
import wbdata
import pandas as pd

# Indicators
indicators = {
 'SI.POV.DDAY': 'poverty_under_2.15',
 'SE.PRM.CMPT.ZS': 'primary_completion',
 'SL.UEM.1524.ZS': 'youth_unemployment'
}
countries = ['CD', 'UG'] # DRC and Uganda

df = wbdata.get_dataframe(indicators, country=countries)
df.to_csv('data/sdg_1_4_8_2015_2024.csv')
print("Data saved for DRC-Uganda")
