# Wind Energy Data Analytics Project

## Programming for Data Analytics

## Author: Finian Doonan

## Overview
This repository contains a data analytics project examining historical wind speed data in Ireland and its implications for wind energy generation. The analysis focuses on wind speed variability, seasonal patterns, and long-term trends using publicly available meteorological data.
**Stations included:**
| Station              | Location       |
| -------------------- | -------------- |
| Malin Head           | Northern coast |
| Mace Head            | Western coast  |
| Valentia Observatory | Southwest      |
| Dublin Airport       | Eastern inland |

----

## Data Sources

* Daily meteorological data from [Met Éireann](https://www.met.ie/climate/available-data/daily-data)

* Variables used:

  * Mean wind speed (wdsp)

  * Highest 10-min mean (hm)

  * Maximum gust (hg)

  * Dominant wind direction (ddhm)

**CSV links:**

| Station              | CSV URL                                                                   |
| -------------------- | ------------------------------------------------------------------------- |
| Malin Head           | [dly1575.csv](https://cli.fusio.net/cli/climate_data/webdata/dly1575.csv) |
| Mace Head            | [dly275.csv](https://cli.fusio.net/cli/climate_data/webdata/dly275.csv)   |
| Valentia Observatory | [dly2275.csv](https://cli.fusio.net/cli/climate_data/webdata/dly2275.csv) |
| Dublin Airport       | [dly532.csv](https://cli.fusio.net/cli/climate_data/webdata/dly532.csv)   |

## Data Loading and Preparation

* Libraries used: pandas, numpy, matplotlib, seaborn, scipy.stats.

* Data from all stations are combined into a single DataFrame.

* Dates are parsed and features like year, month, and week are extracted.

* Wind speeds converted from knots to m/s.

* Missing values are filled per station using forward/backward fill.

````python

# Example: Convert mean wind speed to m/s
combined_df['wind_speed_ms'] = pd.to_numeric(combined_df['wdsp'], errors='coerce') * 0.514444

````

## Technologies Used
- Python 3
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciKit-Learn

## Repository Contents
- `wind_analysis.ipynb` – Main analysis notebook
- `data/raw/` – Original unmodified datasets
- `data/processed/` – Cleaned and processed datasets
- `figures/` – Generated plots

## How to Run
Open `wind_analysis.ipynb` in Jupyter Notebook or JupyterLab and run all cells from top to bottom. All required libraries are listed in `requirements.txt`.

## Notes
The notebook is saved with all outputs already generated for ease of review.
