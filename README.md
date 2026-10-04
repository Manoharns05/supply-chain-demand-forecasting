# Supply Chain Demand Analysis and Forecasting

## Project Overview

This project analyzes historical store-item demand data and uses forecasting techniques to estimate future demand for supply-chain planning.

The project uses the Kaggle Store Item Demand Forecasting Challenge dataset. The analysis focuses on Store 1 and Item 1, using historical daily sales data from January 2013 to December 2017.

The daily sales data was converted into monthly demand and analyzed using Excel.

## Objectives

- Analyze historical demand patterns
- Convert daily sales into monthly demand
- Identify demand trends and recurring monthly variation
- Apply forecasting techniques
- Compare forecasting model accuracy
- Generate future demand forecasts
- Interpret the results for inventory and supply-chain planning

## Dataset

**Source:** Kaggle – Store Item Demand Forecasting Challenge

The original training dataset contains 913,000 records with the following fields:

- `date` – Date of the observation
- `store` – Store identifier
- `item` – Item identifier
- `sales` – Number of items sold

For this project, the analysis focuses on:

- **Store:** 1
- **Item:** 1
- **Historical period:** January 2013 – December 2017
- **Monthly observations:** 60

## Tools Used

- Microsoft Excel
- Excel formulas
- PivotTables
- Charts and data visualization
- Moving Average
- Exponential Smoothing

## Data Analysis

Daily sales data for Store 1 and Item 1 was aggregated into monthly demand.

Historical analysis showed:

| Measure | Result |
|---|---:|
| Minimum monthly demand | 322 units |
| Maximum monthly demand | 903 units |
| Average monthly demand | 607.8 units |
| Highest average month | July – 805 units |
| Lowest average month | February – 412.6 units |

The analysis showed recurring variation in demand throughout the year.

## Forecasting Methods

### 1. Three-Month Moving Average

The forecast is calculated using the average demand of the previous three months.

**Formula:**

`Forecast = (Previous 3 Months Demand) / 3`

Example:

`(328 + 322 + 477) / 3 = 375.67 units`

### 2. Exponential Smoothing

Exponential smoothing uses the latest actual demand and the previous forecast.

**Smoothing factor: α = 0.3**

**Formula:**

`New Forecast = α × Latest Actual Demand + (1 − α) × Previous Forecast`

This gives 30% weight to the latest actual demand and 70% weight to the previous forecast.

## Model Validation

The last six months of 2017, July to December, were used as the validation period.

The models were evaluated using:

- MAE – Mean Absolute Error
- MAPE – Mean Absolute Percentage Error
- RMSE – Root Mean Squared Error

### Results

| Model | MAE | MAPE | RMSE |
|---|---:|---:|---:|
| 3-Month Moving Average | 100.89 | 15.11% | 108.87 |
| Exponential Smoothing | 95.12 | 14.22% | 111.33 |

Exponential smoothing produced lower MAE and MAPE, while the three-month moving average produced a lower RMSE.

## 2018 Forecast

Both models were used to generate baseline monthly demand forecasts for 2018.

| Model | 2018 Monthly Average |
|---|---:|
| 3-Month Moving Average | 600.96 units |
| Exponential Smoothing | 711.06 units |

The difference between the two forecast averages is approximately 110.10 units per month.

These forecasts can be used as baseline estimates for demand planning. They should not be treated as exact inventory requirements because actual inventory planning also requires factors such as lead time, safety stock, service level, holding costs, and stockout risk.

## Project Structure

```text
supply-chain-demand-forecasting/
│
├── README.md
└── train 1.xlsx
