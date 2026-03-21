# GB Power Market Simulation

## Overview
The project looks at the GB power market, utilising hourly data for GB day-ahead prices, wind and solar generation. Granger causality and spectral analysis is used to find the relationships between renewables and price fluctuations. A battery simulation has also been constructed to see how the spread of charge and discharge prices can vary net revenue of the battery.

## Dataset
Open Power System Data. 2020. Data Package Time series. Version 2020-10-06. https://doi.org/10.25832/time_series/2020-10-06. (Primary data from various sources, for a complete list see URL).

The dataset chosen for this project uses hourly data specifically for the GB market, specifically variables for day-ahead prices, wind and solar generation. While all variable data has been cleaned for this project, only price and generation variables have been used thus far. Other variables may be integrated into further analysis conducted on this dataset.

## Key Findings

- A causal effect is found between renewable generation and day-ahead power prices, with the effect being immediate for total and wind generation, and lagged by an hour for solar generation

- Spectral analysis finds dominant trends for day-ahead prices and solar at the 12 and 24 hour intervals, whereas wind has a slight trend at 24 hours but is otherwise noisy

- The battery simulation base case shows very volatile net revenues across the years, with the sensitivity analysis showing the most profitable spread being the tightest around the mean day-ahead power price

## Requirements

Python 3.x, Pandas, Matplotlib, Numpy, Seaborn

For full methodology and results, see the [project notebook](GB Power Market Notebook.ipynb)
