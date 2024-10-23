# Falcon 9 Landing Prediction - IBM Data Science Capstone Project

Welcome to the **Falcon 9 Landing Prediction** repository, part of the **IBM Data Science Professional Certificate**. This project leverages **machine learning** to predict the reusability of the Falcon 9 rocket's first stage, aiming to reduce the cost of space launches by forecasting landing success.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Motivation](#motivation)
3. [Data Sources](#data-sources)
4. [Technologies Used](#technologies-used)
5. [Setup Instructions](#setup-instructions)
6. [Modeling Process](#modeling-process)
   - [Data Preprocessing](#data-preprocessing)
   - [Model Training](#model-training)
7. [Exploratory Data Analysis](#exploratory-data-analysis)
8. [Results](#results)
9. [Dashboard Implementation](#dashboard-implementation)
   - [Dashboard Features](#dashboard-features)
   - [Interactive Plots](#interactive-plots)
10. [Future Work](#future-work)
11. [Appendix](#appendix)
12. [Contributors](#contributors)
13. [License](#license)

---

## Project Overview
This project simulates a scenario where **Space Y**, a new competitor to **SpaceX**, uses **machine learning** techniques to analyze the reusability of the Falcon 9 first stage. By predicting successful landings, Space Y aims to optimize launch costs and increase the sustainability of its space program.

---

## Motivation
The reusability of rockets is crucial in reducing the costs of space missions. By understanding when the **Falcon 9 first stage** successfully lands, this project can provide insights that help optimize operational decisions and cost structures for future launches. **Machine learning** allows us to analyze historical launch data and forecast the landing outcomes.

---

## Data Sources
The dataset used in this project includes public data from SpaceX, which was obtained from:
- **SpaceX API**: For fetching launch data and outcomes.
- **Wikipedia**: Web scraping using `BeautifulSoup` to collect historical data on Falcon 9 and Falcon Heavy launches.
- **Additional Data**: Launch dates, payload mass, orbital parameters, launch sites, and landing outcomes covering launches from 2010 to 2020.

---

## Technologies Used
This project utilizes the following technologies and libraries:

- **Python**: Main programming language.
- **Pandas**: Data analysis and manipulation.
- **NumPy**: Numerical computations.
- **Scikit-learn**: Machine learning library for model development.
- **Matplotlib & Seaborn**: For visualizing data trends and patterns.
- **Plotly Dash**: Used to build interactive dashboards.
- **Folium**: To create interactive maps for visualizing launch sites.
- **Jupyter Notebook**: For interactive analysis and development.
- **SQLite & SQLAlchemy**: For SQL queries and data management.

---

## Setup Instructions

### 1. Clone the repository:
```bash
git clone https://github.com/yourusername/falcon9-landing-prediction-ibm-capstone.git
cd falcon9-landing-prediction-ibm-capstone
```

### 2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

### 3. Launch Jupyter Notebooks for exploration and model training:
```bash
jupyter notebook
```

### 4. Run the Plotly Dash dashboard:
```bash
python spacex_dash_app.py
```

---

## Modeling Process

### Data Preprocessing
- **Data Cleaning**: Missing values were imputed or removed to maintain dataset integrity.
- **Feature Engineering**: Used `get_dummies()` for one-hot encoding of categorical variables like `Orbit`, `LaunchSite`, and `LandingPad`.
- **Scaling**: All numeric columns were standardized using `StandardScaler()` to optimize model performance.

### Model Training
Several machine learning models were trained, tuned, and evaluated:
- **Logistic Regression**: Basic classifier used as a baseline.
- **Support Vector Machine (SVM)**: Tested with various kernels for boundary classification.
- **Decision Trees**: Used for rule-based classification of landing outcomes.
- **K-Nearest Neighbors (KNN)**: Applied to cluster data based on proximity.
- **GridSearchCV**: Hyperparameter tuning to optimize the model.

---

## Exploratory Data Analysis
Key visualizations produced during the EDA phase included:
- **Flight Number vs. Launch Site**: Analyzed how launch success varied across different sites.
- **Payload vs. Orbit**: Identified the relationship between payload mass and orbital success.
- **Launch Success Yearly Trend**: Visualized trends in landing success over time.
- **Success Rate by Orbit Type**: Compared landing success rates across different orbits.
- **Total Payload by NASA**: Showcased the total payload mass for NASA-sponsored launches.

---

## Results
The following accuracies were achieved on the test data:
- **Logistic Regression**: 83.3%
- **SVM**: 83.3%
- **Decision Trees**: 88.9% (Best Performing)
- **K-Nearest Neighbors (KNN)**: 83.3%

### Confusion Matrix for Best Model:
The **Decision Tree** model achieved the highest accuracy with an accuracy score of **88.9%**. The confusion matrix showed a relatively high true positive rate, but a small percentage of false positives.

---

## Dashboard Implementation

### Dashboard Features
- **Launch Site Selection**: Users can filter by launch site to view success/failure ratios.
- **Payload Range Slider**: Interactive slider to filter launches by payload mass.
- **Pie Charts**: Visual representation of success/failure ratios per launch site.
- **Scatter Plots**: Payload vs. Launch Outcome scatter plots color-coded by booster version.

### Interactive Plots
- **Success Pie Charts**: Showed the success rate for all launch sites.
- **Payload vs. Outcome Scatter Plot**: Helped identify trends in payload mass and landing success.

---

## Future Work
- **Incorporate Weather Data**: Introduce weather data to refine the landing prediction model.
- **Advanced Modeling**: Test advanced models like Random Forest and XGBoost to improve classification accuracy.
- **Deployment**: Deploy the prediction model using Flask or FastAPI for real-time predictions.

---

## Appendix
Relevant assets for this project include:
- **SQL Queries**: Used to filter and aggregate data (e.g., payload mass, landing outcomes).
- **Code Snippets**: Python functions for feature engineering and model evaluation.
- **Charts**: Visualizations produced during EDA (e.g., bar charts, scatter plots).
- **Notebook Outputs**: Key results from Jupyter notebooks used in the project.

---

## Contributors
- **Manuel Luján Vilchez** - Data Scientist and Project Lead
- **IBM Data Science Capstone Project Team** - Instructors and resources for guidance.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
