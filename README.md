# London-Bike-Sharing-Analysis
End-to-end data pipeline and Tableau visualization of London bike-share trends.
# London Bike Sharing: Data Pipeline & Analytics

### [View Interactive Tableau Dashboard Here](https://public.tableau.com/app/profile/luis.cuevas4516/viz/Book1_17703395580450/LondonBikeRides?publish=yes)

# Project Overview
This project explores the environmental and temporal factors affecting bike-sharing demand in London. Using a dataset from Kaggle, I built a Python-based ETL pipeline to clean the data and an interactive Tableau dashboard to visualize business insights.

# Data Pipeline (Python)
The data processing was handled in a Jupyter Notebook (`Bikes.ipynb`) using the following steps:
* **Direct Ingestion:** Used the Kaggle API to download the dataset into the environment.
* **Feature Engineering:** Renamed columns for clarity (e.g., `cnt` to `count`, `hum` to `humidity_percent`).
* **Normalization:** Converted humidity values into decimals for standard percentage representation.
* **Categorical Mapping:** Created dictionaries to transform numeric codes into descriptive strings for **Seasons** (Spring, Summer, Fall, Winter) and **Weather Conditions** (Clear, Rain, Snow, etc.).
* **Boolean Logic:** Mapped binary values to "Yes/No" for holiday and weekend status to simplify visualization.

# Business Insights
* **Weather Sensitivity:** Ridership significantly decreases during "Rain with Thunderstorm" and "Snowfall".
* **Seasonal Trends:** Identified which seasons drive peak volume to assist in fleet rebalancing.

# Tech Stack
* **Language:** Python
* **Libraries:** Pandas, Kaggle API, Zipfile
* **BI Tool:** Tableau

* ## Predictive Modeling (Machine Learning)
I extended this project by building a **Random Forest Regressor** to predict hourly bike demand based on environmental factors.



### Key Results:
* **Model Performance:** Achieved an **$R^2$ score of 0.24**, indicating that nearly a quarter of the fluctuations in London's bike demand can be explained by weather and temporal data alone.
* **Primary Drivers:** **Humidity** and **Wind Speed** were identified as the most significant predictors of ridership, followed closely by "Feels Like" temperature.
* **Business Application:** This model allows operators to anticipate demand surges or drops based on weather forecasts, enabling more efficient fleet rebalancing.
