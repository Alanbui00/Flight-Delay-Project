# Flight-Delay-Analysis

An exploratory data analysis of over 5 million U.S. domestic flights, examining delay patterns across airlines, airports, causes, and seasons.
 
---
 
## Project Overview
 
Flight delays create a ripple effect through airline operations, generating significant financial losses and customer dissatisfaction. This project analyzes flight delay data to answer four core questions:
 
1. Which airlines have the highest delay rates?
2. Which airports experience the most delays?
3. What are the most common delay causes?
4. Are there seasonal patterns in delays?

---

## Dataset
 
Three CSV files are required to run this project:
 
| File | Description |
|---|---|
| `flights.csv` | Flight-level records including departure/arrival times, delays, and cancellations |
| `airlines.csv` | Airline IATA codes and full names |
| `airports.csv` | Airport IATA codes, names, cities, and coordinates |
 
The flights dataset covers 2015 U.S. domestic flights and contains ~5.8 million rows after merging.
 
---
 
## Tools & Libraries
 
- **Python 3**
- **Pandas** — data loading, merging, and transformation
- **NumPy** — IQR-based outlier removal
- **Matplotlib** — charting and visualizations
- **Seaborn** — styled bar plots
- **Tableau** — supplemental dashboard (external)
 
---
