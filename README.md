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

## Methodology and Assumptions

**Causal Analysis**

The initial hypothesis was that renewable generation would have a causal effect on day-ahead prices, given the weather-dependent and volatile nature of wind and solar output. Granger causality testing was used to formally test this relationship, examining whether past values of renewable generation improve the prediction of day-ahead prices beyond prices alone. This was found to hold across all lags tested from 1 to 24 hours, with wind generation showing an immediate causal effect and solar lagging by approximately one hour.

**Spectral Analysis**

Spectral analysis was applied to identify dominant cyclical patterns in both renewable generation and day-ahead prices. Dominant 12 and 24-hour cycles were identified in solar generation and day-ahead prices, consistent with diurnal demand and generation patterns. Wind generation was found to be largely stochastic, with only a weak 24-hour cycle present.

**Battery Simulation**

The battery simulation was designed to exploit price spreads between low and high price periods. Initial charge and discharge thresholds were set based on descriptive statistics of the day-ahead price series, establishing a baseline scenario generating £2.1 million total revenue over the period.

A sensitivity analysis was then conducted across a range of charge and discharge threshold combinations. The tightest spread around the price mean proved most profitable, generating approximately £4.7 million over the period. This highlights the importance of parameter selection in battery dispatch optimisation.

**Limitations and Future Work**

The current simulation does not account for transmission costs, grid fees, or degradation costs, which would compress margins in practice. Planned extensions include modelling multiple batteries simultaneously summing to the same total capacity, with parameters optimised individually by season to reflect differing summer and winter price dynamics, and the incorporation of more realistic transaction cost assumptions.

## Requirements

Python 3.x, Pandas, Matplotlib, Numpy, Seaborn

For full methodology and results, see the [project notebook](GB_Power_Market_Notebook.ipynb)
