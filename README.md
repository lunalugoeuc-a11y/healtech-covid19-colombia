# COVID-19 Dynamics in Colombia

An academic HealthTech data-science project that combines epidemiological modeling, time-series analysis, machine learning, and interactive visualization to study the evolution of COVID-19 in Colombia.

**Authors:** Camilo Arias and Luna Lugo  
**Institution:** Universidad Externado de Colombia  
**Course:** HealthTech 2

## Project overview

The project uses country-level data from the COVID-19 Data Hub to answer two complementary questions:

1. How can Colombia's transmission dynamics be interpreted with a mechanistic epidemiological model?
2. How accurately can recent incidence be estimated from its own temporal structure?

The workflow combines a classical SIR model with a lag-based linear regression model for the 7-day moving average of new cases. A self-contained interactive dashboard communicates the main epidemiological patterns and validation results.

## Main results

- The SIR model estimated an average reproduction number of **R₀ = 0.966** and an infectious period of approximately **12.3 days** for the fitted period.
- The estimated epidemic peak occurred on **June 14, 2021**, with approximately **215,523 active infections** under the model.
- The temporal regression achieved **R² = 0.987**, **MAE = 51.41**, **RMSE = 62.98**, and **MAPE = 2.73%** on the chronological test split.
- Recent case lags provided the strongest predictive signal, confirming the short-term autoregressive behavior of the series.

These figures describe performance within the analyzed period. They should not be interpreted as guaranteed performance under new variants, reporting changes, or future structural breaks.

## Methods

- Data cleaning and consistency checks
- Exploratory data analysis and temporal visualization
- SIR compartment construction and parameter estimation
- Lag feature engineering for cases and diagnostic tests
- Linear regression with chronological 80/20 validation
- Interactive dashboard development with Plotly and Seaborn

## Repository structure

```text
.
├── data/
│   └── covid19datahub_level1.csv
├── dashboard/
│   └── covid19_colombia_dashboard.html
├── notebooks/
│   └── COVID19_Colombia_Analysis.ipynb
├── presentation/
│   └── COVID19_Colombia_Presentation_ES.pptx
├── requirements.txt
└── README.md
```

The notebook and repository documentation are in English. The original Spanish presentation is included as a supporting academic deliverable and is explicitly labeled with the `_ES` suffix.

## Run the analysis

1. Clone or download the repository.
2. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Open `notebooks/COVID19_Colombia_Analysis.ipynb` in Jupyter.
4. Run the cells from top to bottom. The notebook automatically checks common relative paths for the dataset.

To explore the results without running Python, open `dashboard/covid19_colombia_dashboard.html` in a modern browser.

## Technology stack

Python, pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn, Plotly, Jupyter Notebook, HTML, and epidemiological time-series modeling.

## Limitations

- Official surveillance data may contain reporting delays, undercounting, and changes in diagnostic criteria.
- Correlations among cumulative indicators may reflect common temporal trends rather than causal relationships.
- The classical SIR model assumes homogeneous mixing, constant parameters, and a single epidemic wave.
- The predictive model excludes mobility, vaccination, variants, and public-policy variables.
- The model is intended for short-horizon analysis within the observed period.

## Data source

The included file is a level-1 extract from the **COVID-19 Data Hub**, used for educational analysis. Please consult the upstream project for its data documentation, attribution requirements, and current licensing terms.

## Responsible use

This repository is an academic project and is not intended for clinical diagnosis, public-health decision-making, or real-time forecasting.

