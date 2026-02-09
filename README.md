# London Bike Sharing: Data Pipeline & Analytics
### [View Interactive Tableau Dashboard Here](https://public.tableau.com/app/profile/luis.cuevas4516/viz/Book1_17703395580450/LondonBikeRides?publish=yes)

## Business Case: Optimizing Urban Mobility
Urban bike-sharing systems often struggle with **supply-demand imbalance**, leading to lost revenue and operational waste. This project serves as a strategic solution for **Transport for London (TfL)** to:
* **Reduce Operational Costs:** Predicting low-demand periods for proactive maintenance.
* **Increase Revenue:** Identifying seasonal trends for targeted marketing.
* **Improve User Experience:** Ensuring bike availability through weather-responsive rebalancing.

## Data Pipeline (Python ETL)
The data processing was handled in a Jupyter Notebook (`bikeRidesLondon.ipynb`) to create a clean, analysis-ready dataset:
* **Direct Ingestion:** Streamlined data retrieval using the Kaggle API.
* **Feature Engineering:** Renamed raw headers (e.g., `cnt`, `t1`, `hum`) to business-friendly terms like `count`, `temp_real_C`, and `humidity_percent`.
* **Data Normalization:** Transformed `humidity_percent` into a true decimal format.
* **Categorical Mapping:** Developed dictionaries to map numeric codes into human-readable strings for **Seasons** and **Weather Conditions**.
* **Boolean Translation:** Mapped `is_holiday` and `is_weekend` to "Yes/No" strings to enhance visualization clarity.



## Predictive Modeling (Machine Learning)
To move from descriptive to predictive analytics, I implemented a **Random Forest Regressor** to forecast hourly demand.

### The ML Toolkit
* **Preprocessing:** `OneHotEncoder` via `pd.get_dummies` to transform categorical strings (Season, Weather) into numeric inputs.
* **Model:** `RandomForestRegressor` from `scikit-learn` for its robustness in handling non-linear relationships.
* **Validation:** Used `train_test_split` (80/20) and evaluated performance using **R² Score** and **Feature Importance**.

### Key Results
* **Performance:** Achieved an **$R^2$ score of 0.24**, capturing nearly a quarter of demand variance through environmental data alone.
* **Primary Drivers:** **Humidity** and **Wind Speed** were identified as the most significant predictors of ridership, followed by "Feels Like" temperature.
* **Business Application:** This model allows operators to anticipate demand drops during adverse weather, enabling more efficient fleet rebalancing.



## Business Insights & Visualizations
* **Weather Sensitivity:** Ridership significantly decreases during "Rain with Thunderstorm" and "Snowfall".
* **Seasonal Trends:** Identified Summer and Spring as peak volume drivers, providing a baseline for fleet expansion.

## Tech Stack
* **Language:** Python 3.x
* **Libraries:** Pandas (Data Wrangling), Scikit-Learn (ML), Matplotlib/Seaborn (Visualization), Kaggle API (Ingestion)
* **BI Tool:** Tableau Public

## Conclusion & Final Recommendations
By integrating a **Data Pipeline**, **Business Intelligence**, and **Predictive Modeling**, this project provides a scalable framework for optimizing shared mobility infrastructure.

#### **Data-Driven Business Actions**
* **Optimized Maintenance:** Prioritize bike maintenance during high-humidity/high-wind forecasts when predicted demand is low.
* **Fleet Rebalancing:** Pre-emptively move bikes to commuter hubs during "Optimal" weather windows identified by the model.
* **Revenue Growth:** Launch "Off-Peak" membership incentives during Winter and Fall to stabilize ridership.
* **Infrastructure Justification:** Use consistent weekend usage patterns to justify the expansion of leisure-focused cycleways.
