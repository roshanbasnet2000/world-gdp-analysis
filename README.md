
# World GDP Indicator Analysis: Regression, Classification, and Time Series Forecasting

This repository contains a comprehensive analysis of the World Bank GDP indicators for 268 countries spanning from 2006 to 2023. The project includes three main tasks: regression modeling to predict GDP per capita, classification to assign countries to income tiers, and time series forecasting to predict future GDP growth. The analysis utilizes machine learning and statistical techniques to provide insights into global economic trends and predictions.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Code](#code)
4. [Report](#report)
5. [Installation and Usage](#installation-and-usage)
6. [Modeling Details](#modeling-details)
7. [Results](#results)
8. [Contributions](#contributions)
9. [Future Improvements](#future-improvements)
10. [Ethical Considerations](#ethical-considerations)

## Project Overview

The main goal of this project is to analyze GDP-related data using three distinct tasks:
- **Regression**: Predicting GDP per capita for countries using macroeconomic indicators.
- **Classification**: Categorizing countries into income tiers (Low, Lower-Middle, Upper-Middle, High).
- **Time Series Forecasting**: Forecasting future GDP growth using ARIMA models for selected countries.

The dataset is sourced from the [World Bank Open Data Portal](https://data.worldbank.org), and the analysis is performed using Python, specifically with libraries such as `pandas`, `scikit-learn`, `statsmodels`, and `matplotlib`.

## Dataset

The dataset used in this project is the **World Development Indicators (WDI)** from the World Bank, covering data from 2006 to 2023. It includes macroeconomic indicators for 268 countries, with 10 key indicators used in the analysis.

### Key Indicators:
- **GDP per capita** (current USD)
- **Gross Domestic Savings (% GDP)**
- **FDI Net Inflows (% GDP)**
- **Trade (% GDP)**
- **Inflation, GDP Deflator (%)**
- **Education Expenditure (% GDP)**
- **Tax Revenue (% GDP)**
- **Gross Capital Formation (% GDP)**
- **Current Account Balance (% GDP)**
- **GDP Growth (Annual %)**

You can find both the **raw dataset** and the **cleaned dataset** in the repository.

## Code

The code for this project is contained in the Jupyter Notebook `python_code.ipynb`. The notebook includes:
- Data preprocessing and cleaning steps.
- Feature engineering for classification.
- Regression model training (Linear Regression, Ridge Regression, Random Forest Regressor).
- Classification model training (Decision Tree, Random Forest, Gradient Boosting).
- Time series analysis and ARIMA model forecasting.
- Performance evaluation for each model.

### Libraries Used:
- `pandas` for data manipulation
- `numpy` for numerical operations
- `scikit-learn` for machine learning models
- `statsmodels` for ARIMA and time series analysis
- `matplotlib` and `seaborn` for visualizations

## Report

The project report (`Report.pdf`) details the entire process, including the methodology, results, and suggestions for future improvements. It includes an overview of the dataset, a description of the modeling process, and the findings from each task. Key findings are:
- A Random Forest Regressor achieved an **R² of 0.92** in predicting GDP per capita.
- A **Random Forest Classifier** achieved **91% accuracy** in classifying countries into income tiers.
- Time series models (ARIMA) were used to predict future GDP growth for Canada, India, and Brazil.

## Installation and Usage

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/your-username/World-GDP-Indicator-Analysis.git
   cd World-GDP-Indicator-Analysis
   ```

2. Install the required libraries (preferably in a virtual environment):

   ```bash
   pip install -r requirements.txt
   ```

3. Open the `python_code.ipynb` file using Jupyter Notebook or JupyterLab.

4. Run each cell in the notebook to reproduce the data preprocessing, modeling, and forecasting steps.

## Modeling Details

### Regression:
The regression task aims to predict **GDP per capita** using macroeconomic indicators. Three models were evaluated:
- **Linear Regression** (baseline)
- **Ridge Regression** (with L2 regularization)
- **Random Forest Regressor** (non-linear ensemble method)

The Random Forest Regressor outperformed the linear models, achieving an **R² score of 0.92** on the log-transformed GDP per capita target.

### Classification:
The classification task aims to assign countries into income tiers (Low, Lower-Middle, Upper-Middle, High). The models used were:
- **Decision Tree** (with hyperparameter tuning)
- **Random Forest Classifier**
- **Gradient Boosting**

The **Random Forest Classifier** achieved **91% accuracy**, with the most important features being **domestic savings**, **inflation**, and **trade**.

### Time Series Forecasting:
ARIMA models were used to forecast GDP growth for **Canada**, **India**, and **Brazil**. ARIMA(1,1,1) was found to be a good fit for all three countries. Five-year forecasts were generated, and model performance was evaluated using **RMSE** and **MAE**.

## Results

- **Regression**: Random Forest achieved **92% R²** on the test set.
- **Classification**: Random Forest Classifier achieved **91% accuracy**.
- **Time Series**: The ARIMA model's performance varied, with Canada performing best, followed by Brazil and India.

## Contributions

- **Roshan Basnet**: Led the **time series forecasting** task, using ARIMA models to forecast GDP growth for selected countries (Canada, India, Brazil). Responsible for **data preprocessing**, implementing the forecasting models, and evaluating the overall performance of the project. Contributed to the **evaluation** and **modeling insights** sections of the report.

## Future Improvements

1. **Advanced Models**: Replace Random Forest with **XGBoost** or **LightGBM** to improve performance and training efficiency.
2. **Multivariate Time Series**: Use **VAR** or **SARIMAX** to include additional macroeconomic indicators in the time series forecasting.
3. **Deep Learning**: Experiment with **LSTM** (Long Short-Term Memory) models for better handling of long-range temporal dependencies.
4. **External Income Labels**: Use official World Bank income classification labels to eliminate concerns about label derivation.
5. **Regional Models**: Fit separate models for different regions (e.g., Sub-Saharan Africa, East Asia) to improve accuracy.

## Ethical Considerations

- **Data Bias**: Models may exhibit bias due to missing data or the imputation method used. It's essential to regularly audit models for fairness and bias, especially when used for policy decisions.
- **Income Tier Classification**: Classifying countries into income tiers based on economic indicators can have significant consequences, such as determining eligibility for aid programs. These models should supplement expert judgment rather than replace it.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
