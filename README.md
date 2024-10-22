# Falcon 9 Landing Prediction - IBM Data Science Capstone Project

Welcome to the **Falcon 9 Landing Prediction** repository, a part of the **IBM Data Science Professional Certificate**. This project uses **machine learning** to predict the reusability of the first stage of the Falcon 9 rocket, helping to estimate the costs of space launches.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Motivation](#motivation)
3. [Data Sources](#data-sources)
4. [Technologies Used](#technologies-used)
5. [Setup Instructions](#setup-instructions)
6. [Modeling Process](#modeling-process)
   - [Data Preprocessing](#data-preprocessing)
   - [Model Training](#model-training)
7. [Results](#results)
8. [Future Work](#future-work)
9. [Contributors](#contributors)
10. [License](#license)

---

## Project Overview
This project simulates a real-world scenario where **Space Y**, a new rocket company, seeks to compete with **SpaceX**. By analyzing public data from SpaceX's launches, we build predictive models to determine whether the first stage of the Falcon 9 rocket will successfully land and be reused, which plays a major role in reducing the cost of launches.

---

## Motivation
Reusability is key in reducing costs for space missions. Understanding when and why the **Falcon 9 first stage** successfully lands helps improve decision-making and optimize pricing for future launches. This project applies machine learning techniques to make such predictions and help potential competitors of SpaceX.

---

## Data Sources
The data used in this project comes from public SpaceX launch data and includes:
- **Launch Dates**
- **Payload Mass**
- **Orbital Parameters**
- **Launch Sites**
- **Grid Fins and Legs Usage**
- **Landing Outcomes** (successful or failed)

The data was obtained from the SpaceX API and web scraping Wikipedia pages for Falcon 9 and Falcon Heavy launches, covering launches from 2010 to 2020.

---

## Technologies Used
This project leverages the following tools and technologies:
- **Python**: Programming language used for data manipulation and model development.
- **Pandas**: Data analysis and manipulation library.
- **NumPy**: Efficient numerical computations.
- **Scikit-learn**: Machine learning algorithms and tools.
- **Matplotlib & Seaborn**: Data visualization libraries.
- **Plotly Dash**: For building interactive dashboards.
- **Folium**: For creating interactive maps.
- **Jupyter Notebook**: For interactive development and analysis.

---

## Setup Instructions
To set up this project locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/falcon9-landing-prediction-ibm-capstone.git
   cd falcon9-landing-prediction-ibm-capstone
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Jupyter notebooks for data exploration, feature engineering, and model training:
   ```bash
   jupyter notebook
   ```

4. To launch the Plotly Dash dashboard, run:
   ```bash
   python spacex_dash_app.py
   ```

---

## Modeling Process

### Data Preprocessing

- **Data Cleaning**: Handling missing values in features like `LandingPad` and `PayloadMass`.
- **Feature Engineering**: One-hot encoding categorical variables such as `Orbit`, `LaunchSite`, and `LandingPad`.
- **Scaling**: Standardized numeric features using `StandardScaler()`.

### Model Training

- **Logistic Regression**: Used for initial classification of landing success.
- **Decision Trees**: Trained to identify decision paths leading to landing success.
- **K-Nearest Neighbors (KNN)**: Implemented for proximity-based classification.
- **Support Vector Machine (SVM)**: Explored for boundary classification with different kernels.
- **GridSearchCV**: Applied to tune hyperparameters and select the best-performing models.

---

## Results
The models achieved the following accuracies on the test set:

- **Logistic Regression**: 84.6% accuracy
- **Support Vector Machine (SVM)**: 84.8% accuracy
- **Decision Trees**: 83.3% accuracy
- **K-Nearest Neighbors (KNN)**: 83.3% accuracy

The confusion matrices revealed that false positives were the most common issue in classification. In particular, the models struggled to distinguish between failed and successful landing attempts in some cases.

---

## Future Work
- **Feature Expansion**: Include weather data and launch time to improve prediction accuracy.
- **Model Optimization**: Fine-tune hyperparameters and experiment with advanced models like Random Forests and XGBoost.
- **Deployment**: Deploy the model as an API using Flask or FastAPI for real-time predictions.

---

## Contributors
- **Manuel Luján Vilchez** - Data Scientist and Project Lead
- **IBM Data Science Capstone Project Team** - Instructors and resources for guidance.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
