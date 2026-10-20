# SaaS-sales-analysis-forecasting

An educational data analysis project using Python and Power BI to explore software sales trends and project sales beyond the dataset period.

## Project files

- `inspect_sales.py` — checks and prepares the data, creates exploratory charts, compares forecasting methods, and exports files for Power BI.
- `Task2_Sales_Analysis.pbix` — Power BI report with sales overview and forecast visuals.

## Dataset

This project uses the public [AWS SaaS Sales dataset on Kaggle](https://www.kaggle.com/datasets/nnthanh101/aws-saas-sales). The sample data is not confidential data from an employer.

Download and extract the dataset. Place `SaaS-Sales.csv` in the same folder as `inspect_sales.py`.

## Run the Python analysis

Install the required packages:

```bash
python -m pip install pandas matplotlib statsmodels
```

Open a terminal in the project folder and run:

```bash
python inspect_sales.py
```

The script creates cleaned and monthly sales CSV files, exploratory charts, a six-month forecast, and `powerbi_sales_forecast.csv`.

## Forecast method

The script reserves the final 12 months of the dataset for evaluation. It compares a seasonal baseline with Holt-Winters using MAE and MAPE, then uses the lower-MAE method for a six-month projection.

The projection continues from the last month in the dataset. It is a historical sample projection, not a forecast from the current date.

## Power BI

The report uses the analysis output files. To refresh or recreate its visuals, import `saas_sales_cleaned.csv` and `powerbi_sales_forecast.csv`. For the forecast line chart, use `Date` on the X axis, `Sales` on the Y axis, and `Series` as the legend.
