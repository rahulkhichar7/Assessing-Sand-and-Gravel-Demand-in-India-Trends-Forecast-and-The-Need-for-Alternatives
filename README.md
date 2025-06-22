# Assessing Sand and Gravel Demand in India: Trends, Forecast, and The Need for Alternatives

[![GitHub Repo](https://img.shields.io/badge/GitHub-Project-blue?.com/rahulkhichar7/Assessing-Sand-and-Gravel-Demand-in-India-Trends-Forecast-and-The-Need-for-Alternatives

This repository contains code and data for the research project **"Assessing Sand and Gravel Demand in India: Trends, Forecast, and The Need for Alternatives"**. The project analyzes historical sand and gravel extraction trends in India, explores their relationship with socio-economic factors, and forecasts future demand using advanced time-series models. The findings highlight the urgent need for sustainable alternatives and policy interventions to mitigate environmental impacts.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
- [How to Run](#how-to-run)
- [Key Results](#key-results)
- [Project Structure](#project-structure)
- [References](#references)
- [License](#license)

---

## Introduction

Sand and gravel are critical raw materials for construction and infrastructure in India. Rapid urbanization and economic growth have sharply increased their demand, resulting in extensive mining and significant environmental challenges. This project:

- Analyzes historical sand and gravel mining data (1994–2019)
- Correlates demand with GDP and population growth
- Uses SARIMAX (with exogenous variables) and other time-series models for forecasting
- Provides insights for policymakers and industry stakeholders on sustainable alternatives and regulatory needs

For a detailed abstract, background, and results, see the [project paper](https://github.com/rahulkhichar7/Assessing-Sand-and-Gravel-Demand-in-India-Trends-Forecast-and-The-Need-for-Alternatives.git) and [paste.txt][1].

---

## Features

- **Historical Data Analysis:** Visualizes and interprets sand and gravel mining trends in India.
- **Socio-Economic Correlation:** Quantifies the relationship between demand, GDP, and population.
- **Time-Series Forecasting:** Implements SARIMAX with exogenous variables (GDP, population) for robust demand prediction.
- **Hyperparameter Tuning:** Employs a validation-based approach to avoid data leakage.
- **Scenario Forecasting:** Projects demand up to 2050, highlighting sustainability challenges.
- **Policy Relevance:** Supports recommendations for sustainable mining and adoption of alternatives like M-Sand.

---

## Data Sources

- **Sand and Gravel Mining Data:** U.S. Geological Survey (USGS) Mineral Commodity Summaries
- **GDP and Population:** CEIC Data, fabricated for future projections based on historical trends

See [paste.txt][1] for details on data collection and assumptions.

---

## Methodology

1. **Data Preparation:**  
   - Historical data from 1994–2019  
   - Exogenous variables: GDP (Trillion USD), Population (Billion)

2. **Train-Validation-Test Split:**  
   - `train = df.iloc[:23]` (1994–2016)  
   - `validation = df.iloc[23:24]` (2017)  
   - `test = df.iloc[24:26]` (2018–2019)  
   - `forecast_period = df.iloc[26:]` (2020 and beyond)

3. **Modeling:**  
   - SARIMAX with grid search over hyperparameters  
   - Hyperparameter tuning uses only the last point of the training set (validation) to prevent data leakage  
   - Retrain best model on train + validation, then evaluate on test set

4. **Evaluation:**  
   - Performance measured using Mean Absolute Error (MAE)

5. **Forecasting:**  
   - Long-term projections up to 2050

---

## How to Run

### Prerequisites

- Python 3.8+
- Install dependencies:
  ```bash
  pip install numpy pandas matplotlib scikit-learn statsmodels
  ```

### Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/rahulkhichar7/Assessing-Sand-and-Gravel-Demand-in-India-Trends-Forecast-and-The-Need-for-Alternatives.git
   cd Assessing-Sand-and-Gravel-Demand-in-India-Trends-Forecast-and-The-Need-for-Alternatives
   ```

2. Run the main notebook or script:
   ```bash
   python sand_gravel_forecast.ipynb
   ```
   *(Replace with the actual filename if different.)*

3. View the generated plots and results.

---

## Key Results

- **SARIMAX (with GDP and population as exogenous variables) outperformed ARIMA and SARIMA models.**
- **Best SARIMAX MAE:** 0.75 (see [paste.txt][1] for details)
- **Forecast:** Demand for sand and gravel is projected to rise steadily, potentially exceeding 90 million metric tons annually by 2050.
- **Policy Insight:** The results underscore the need for sustainable alternatives (e.g., M-Sand) and stronger regulatory frameworks to mitigate environmental impacts.

---

## Project Structure

```
.
├── sand_gravel_forecast.py   # Main code for data analysis and forecasting
├── data/                     # Data files (if any)
├── figures/                  # Generated plots
├── paste.txt                 # Project report and documentation
└── README.md                 # Project overview and instructions
```

---

## References

- [Project Report and Analysis (paste.txt)][1]
- Sustainable Sand Mining Management Guidelines, Ministry of Environment, Forest and Climate Change, Government of India[2]
- USGS Mineral Commodity Summaries
- CEIC Data, Population Projection: Single Year — India
- [Sand Mining in India and its Evaluation using SWOT Analysis][3]
- [Mapping and modeling riverine sand and gravel mining at the sub-continental scale: A case study for India][4]

---

## License

This project is for academic and research purposes only.  
See [LICENSE](LICENSE) for details.

---

[1]: paste.txt

