# Seattle and New York City rainfall comparison
This project compares precipitation in Seattle and New York City from 2018 through 2022 to explore which city receives more rain.

## Project overview
This project uses daily precipitation data to compare rainfall in Seattle and New York City. The analysis will examine both total precipitation and the number of rainy days before drawing a conclusion.
- **Objective:** Compare rainfall in Seattle and New York City
- **Domain:** Weather and climate
- **Key techniques:** Data cleaning, descriptive statistics and data visualization.

## Project structure
- `data/` — Raw and processed data
- `code/` — Jupyter notebooks and Python scripts
- `reports/` — Generated reports and visualizations
- `requirements.txt` — Dependencies
- `README.md` — Project documentation

## Data
- **Source:** <br>
Seattle datasets: [DATA 5100 weather repository](https://github.com/brian-fischer/DATA-5100/tree/main/weather) <br>
New York City precipitation data: [NOAA Climate Data Online](https://www.ncei.noaa.gov/cdo-web/search?datasetid=GHCND)
- **Description:** <br>
The datasets are CSV files containing weather observations. `seattle_rain.csv` has 1,658 daily records from one Seattle station, and `nyc_rain.csv` has 1,826 daily records from the New York City Central Park station. Both cover January 1, 2018, through December 31, 2022. Key columns include station ID (`STATION`), station name (`NAME`), date (`DATE`), and precipitation (`PRCP`). The course also provides `stl_rain.csv` (54,574 records from 44 stations), but this project compares Seattle and New York City.

## Data preparation
The data preparation is performed in `code/Weather_Data.ipynb`. The steps were:

1. Loaded the Seattle and NYC data sets and checked their columns, data types, sizes, and number of weather stations (one station per city, so no station filtering was needed).
2. Converted the `DATE` column from strings to datetime.
3. Checked for omitted dates: 2018-2022 should have 1,826 days. NYC was complete, while Seattle was missing 168 dates and had 22 `PRCP` values recorded as NaN.
4. Kept only the `DATE` and `PRCP` columns and combined the two data sets with an outer join on `DATE`, so dates missing from the Seattle file appear as NaN.
5. Reshaped the data into tidy (long) format with one row per city per day, and renamed the columns and values (`date`, `city` = `NYC` / `SEA`, `precipitation`).
6. Imputed the 190 missing Seattle precipitation values by replacing each with the mean precipitation for that day of the year, averaged across years.
7. Verified that no missing values remained and exported the result.
**Clean data file:** `data/clean_seattle_nyc_weather.csv` (3,652 rows; columns: `date`, `city`, `precipitation`, `day_of_year`).

## Analysis
The analysis will be completed in `code/Weather_Data.ipynb`.

## Results
To be completed after the analysis.

## Author
Quynh Giang Tran
