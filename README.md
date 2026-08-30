# MAST30034-Project_1
First project
# Weather and Taxi Demand in New York City

## Project Overview

This project investigates the relationship between weather conditions and taxi
demand in New York City.

The analysis uses Yellow and Green Taxi trip records from the New York City Taxi
and Limousine Commission (TLC) together with hourly historical weather data from
Meteostat.

The study period covers six consecutive months from 1 December 2025 to
31 May 2026.

Taxi demand is measured as the number of valid taxi pickups recorded within each
hour. The main comparison considers Sunny and Rainy weather conditions and examines
how taxi demand changes across time and taxi zones.

The analysis is intended to provide useful information for NYC taxi drivers when
considering when and where passenger demand may be higher.

---

## Research Question

**How is weather associated with taxi demand in New York City?**

The project investigates this question through:

- Taxi data preprocessing and outlier removal
- Hourly weather and taxi-data integration
- Spatial analysis of taxi demand by TLC taxi zone
- Comparison of hourly demand under Sunny and Rainy weather
- Linear Regression modelling
- XGBoost modelling with a Poisson objective
- XGBoost feature-importance analysis

---

## Data

### NYC TLC Taxi Trip Records

Yellow and Green Taxi trip records were obtained from:

https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

The analysis uses data from:

- December 2025
- January 2026
- February 2026
- March 2026
- April 2026
- May 2026

Both Yellow and Green Taxi records are included to provide broader coverage of
taxi activity across New York City.

### Historical Weather Data

Hourly historical weather observations were obtained from Meteostat:

https://dev.meteostat.net/

The weather data are matched to taxi trips according to the hourly pickup
timestamp.

For the main comparison:

- `coco = 1` is classified as **Sunny**
- `coco = 7, 8, 9, 10, 11, 17, 18` are classified as **Rainy**

Other weather conditions are excluded from the Sunny versus Rainy comparison.

### NYC Taxi Zones

NYC TLC taxi-zone geographic data and the taxi-zone lookup table are used to
validate pickup locations and create the geospatial visualisations.

---

## Repository Structure

The main files and folders used by the project are organised approximately as:

```text
MAST30034-Project_1/
│
├── README.md
├── requirements.txt
├── project_1_f.ipynb
├── report.pdf
├── main.tex
├── reference.bib
│
├── p1_green/
│   ├── green_tripdata_2025-12.parquet
│   ├── green_tripdata_2026-01.parquet
│   ├── green_tripdata_2026-02.parquet
│   ├── green_tripdata_2026-03.parquet
│   ├── green_tripdata_2026-04.parquet
│   └── green_tripdata_2026-05.parquet
│
├── p1_yellow/
│   ├── yellow_tripdata_2025-12.parquet
│   ├── yellow_tripdata_2026-01.parquet
│   ├── yellow_tripdata_2026-02.parquet
│   ├── yellow_tripdata_2026-03.parquet
│   ├── yellow_tripdata_2026-04.parquet
│   └── yellow_tripdata_2026-05.parquet
│
└── weather and TLC taxi-zone files used by the notebook
