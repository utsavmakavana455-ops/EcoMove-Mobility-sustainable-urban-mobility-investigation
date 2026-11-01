# EcoMove Mobility – Data Visualisation

Python analysis and an interactive dashboard for the **COM7021 Data Visualisation** module (Arden University).

The project studies 5,000 daily records (2024–2025) from EcoMove Mobility, a sustainable urban transport operator.
It looks at five areas: demand, reliability, finance, accessibility and sustainability.



## Questions the project answers

- Which cities and transport modes carry the most passengers?
- How do weather and event days change delays and on-time performance?
- Does delay affect customer ratings?
- Which modes cover their costs, and what does each tonne of CO2 saved cost?
- Where are accessibility complaints highest?

## Main findings

- **Metro carries 63.0% of passengers**, saves 70.3% of CO2 and earns the largest surplus (€4.3 million).
- **Bus is the least reliable mode:** 6.58 minutes average delay and 74.9% on time. Snow raises average delay to 8.14 minutes.
- **Delay lowers ratings:** about 0.14 points per extra minute, in every mode.
- **Bike Share and E-Scooter cover only 5.2% and 7.4% of their costs.** Their combined loss (€8.88 million) is larger than the surplus of the other modes (€8.41 million).
- **Accessibility complaints are local:** about 1.5 per 1,000 passengers almost everywhere, but 4.93 (Bike Share) and 5.40 (E-Scooter) on Suburban Feeder routes.

## Repository contents

| File / folder | Description |
|---|---|
| `ecomove_analysis.py` | Imports the data, checks and cleans it, runs the statistics, saves the charts |
| `ecomove_dashboard.py` | Interactive dashboard built with Plotly Dash |
| `EcoMoveMobility.xlsx` | Dataset supplied for the module |
| `figures/` | The 12 charts and two dashboard screenshots |
| `screenshots/` | Screenshots of each step of the code running |
| `notebooks/` | The analysis as a notebook with outputs saved |
| `requirements.txt` | Python libraries needed |

## How the analysis works

1. **Import and inspect** – load the Excel file, check structure, types, missing values and duplicates.
2. **Clean and prepare** – convert Excel dates, check valid ranges, investigate zero values and outliers (IQR rule), add helper columns.
3. **Statistics** – descriptive statistics and skewness, group summaries by mode and city, hypothesis tests and correlation.
4. **Visualise** – 12 charts saved to `figures/` at 200 dpi.
5. **Save outputs** – cleaned data and summary tables as CSV files.

## Dashboard features

- Filters: city, transport mode, route type, weather, event day, date range (empty filter = all).
- 8 KPI cards: records selected, passengers, cost recovery, average delay, on-time %, rating, CO2 saved, complaints per 1,000 passengers.
- 7 charts arranged from overview to detail.
- A warning appears when fewer than 100 records match the filters.

```

Run the commands from the repository folder; the scripts look for `EcoMoveMobility.xlsx` in the current folder.

## Libraries

pandas, numpy, scipy, matplotlib, seaborn, openpyxl, plotly, dash.

## Notes

- All figures come from the supplied dataset. Nothing is simulated.
- Made for university coursework. If you reuse any of it, please reference it properly.
