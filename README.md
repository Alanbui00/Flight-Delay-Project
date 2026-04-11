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

## Project Structure
 

- Flight_Delay_Project.ipynb   - Main analysis notebook
- flights.csv                    - [Link for dataset](https://www.kaggle.com/datasets/usdot/flight-delays) 
- airlines.csv                   - [Link for dataset](https://www.kaggle.com/datasets/usdot/flight-delays) 
- airports.csv                   - [Link for dataset](https://www.kaggle.com/datasets/usdot/flight-delays) 
- README.md


## Methodology
 
### 1. Data Merging
The three datasets are merged on airline IATA codes and airport IATA codes. Origin and destination airports are prefixed (`ORIGIN_`, `DEST_`) to avoid column name collisions.
 
### 2. Data Cleaning
- **Outliers** are removed using IQR — flights with extreme delay values (250–2000+ minutes) are excluded from delayed flights only; on-time flights are retained.
- **Airports with fewer than 1,000 flights** are filtered out to prevent small sample sizes from skewing delay rate metrics.

### 3. Feature Engineering
- 1. A boolean column for flights if it is classified as **delayed** if its arrival delay exceeds 15 minutes (the FAA standard).
- 2. A column for the total time delay, in case a flight has more than one type of delay
 
### 3. Exploratory Data Analysis
Five analyses are performed:
- Delay rate by airline (frequency)
- Average airline delay duration (severity)
- Top 10 departure airports by delay rate
- Top 10 destination airports by delay rate
- Delay causes breakdown (pie chart)
- Monthly delay trends overall and by cause
 
---

## Key Findings
 
- **Spirit (~25%) and Frontier (~22%)** had the highest delay rates among all airlines, with most in the top 5 being budget airlines; **Hawaiian and Alaska** had the lowest (~10%), not main airlines but not budget airlines . However, Hawaiian's delays tended to last longer when they did occur — highlighting that frequency and severity are different dimensions of performance.
- **Late aircraft propagation and airline operational issues** together account for ~75% of all delay minutes, indicating that delays are often carried over from earlier flights or caused by internal airline operations. In contrast, weather and security contribute only ~5%, despite being more visible to passengers. 
- **Delays peak in June, July, and February** driven by summer travel demand and winter weather disruptions. The lowest delays occur in September and October, making them the most reliable months for travel.
- **Departure delays** are more concentrated at major hubs (e.g., ORD, LGA), where congestion is high with them being transit hubs. while **arrival delays** skew toward smaller regional airports with limited operational flexibility, likely due to limited infrastructure and reduced flexibility in handling disruptions.
 
---

## How to Run
 
1. Clone or download this repository.
2. Get dataset [Link](https://www.kaggle.com/datasets/usdot/flight-delays) 
3. Place `flights.csv`, `airlines.csv`, and `airports.csv` in the same directory as the notebook.
4. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
5. Open and run `Flight_Delay_Project.ipynb` top to bottom in Jupyter Notebook or JupyterLab.
 
---
 
## Recommendations
 
**For Airlines:** Focus on improving schedule buffers and aircraft turnaround efficiency, particularly during peak summer and winter months. Since late aircraft is the leading cause of delays, reducing delays throughout the day would have the greatest system-wide impact.
 
**For Travelers:** Flying in September or October minimizes delay risk. When choosing an airline, consider both delay frequency and typical delay duration — a carrier with fewer but longer delays may be more disruptive than one with more frequent but shorter delays. Avoid tight connections on low-cost carriers, which have higher delay rates.
