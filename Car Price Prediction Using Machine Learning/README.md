# 🚗 Car Price Prediction Using Machine Learning

## 📌 Project Overview

This project focuses on predicting automobile prices using machine learning regression algorithms.

A Chinese automobile company plans to enter the US market and wants to understand the factors that influence car prices. Using historical automobile data, this project analyses vehicle characteristics, identifies important pricing factors, and develops machine learning models to predict car prices.

The main objective is to identify the best-performing regression model and provide useful insights for automobile pricing decisions.

## 🎯 Objectives

* Perform Exploratory Data Analysis (EDA) to understand the dataset.
* Clean and preprocess the data for machine learning.
* Analyse relationships between vehicle features and car prices.
* Implement and compare five regression algorithms.
* Identify important features influencing car prices.
* Perform hyperparameter tuning to improve model performance.
* Select the best-performing model for price prediction.

## 📂 Dataset Description

**Dataset:** CarPrice_Assignment.csv

* Number of records: 205
* Number of columns: 26
* Target variable: `price`
* Input features: Vehicle specifications and characteristics.

The dataset contains information about engine size, horsepower, curb weight, fuel type, car body, mileage, and other automobile features.

## 🛠️ Technologies and Libraries Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

## 🔍 Project Workflow

### 1. Data Loading and Inspection

* Loaded the dataset using Pandas.
* Examined dataset dimensions and data types.
* Checked for missing values and duplicate records.

### 2. Exploratory Data Analysis (EDA)

* Univariate analysis using histograms and count plots.
* Bivariate analysis using scatter plots and box plots.
* Multivariate analysis using correlation heatmaps.

### 3. Data Preprocessing

* Removed the irrelevant `car_ID` column.
* Separated independent features and the target variable.
* Identified numerical and categorical features.
* Applied One-Hot Encoding to categorical variables.
* Split the dataset into training and testing sets.
* Applied feature scaling for Support Vector Regression.

### 4. Model Building

Five regression algorithms were implemented:

1. Linear Regression
2. Decision Tree Regressor
3. Random Forest Regressor
4. Gradient Boosting Regressor
5. Support Vector Regressor (SVR)

### 5. Model Evaluation

The models were evaluated using:

* R² Score
* Mean Squared Error (MSE)
* Mean Absolute Error (MAE)

### 6. Feature Importance Analysis

Random Forest feature importance was used to identify the most influential features in predicting car prices.

### 7. Hyperparameter Tuning

GridSearchCV with five-fold cross-validation was used to tune the Random Forest Regressor.

## 📊 Model Performance Comparison

| Model             | R² Score |        MSE |      MAE |
| ----------------- | -------: | ---------: | -------: |
| Linear Regression |   0.4737 | 41,547,030 | 4,177.30 |
| Decision Tree     |   0.8559 | 11,376,020 | 2,200.14 |
| Random Forest     |   0.9535 |  3,674,318 | 1,365.35 |
| Gradient Boosting |   0.9306 |  5,478,929 | 1,700.99 |
| SVR               |  -0.1017 | 86,973,310 | 5,705.03 |

## 🏆 Best Model: Tuned Random Forest Regressor

Random Forest Regressor achieved the best performance among the five initial models.

After hyperparameter tuning using GridSearchCV, the model achieved:

| Evaluation Metric |  Tuned Model |
| ----------------- | -----------: |
| R² Score          |       0.9545 |
| MSE               | 3,588,950.11 |
| MAE               |     1,338.71 |

### Best Hyperparameters

* `n_estimators`: 300
* `max_depth`: None
* `min_samples_split`: 2
* `min_samples_leaf`: 2

The tuned model showed a slight improvement over the original Random Forest model.

## ⭐ Important Features

The feature importance analysis identified the following important features:

| Feature     | Importance |
| ----------- | ---------: |
| Engine Size |     0.5408 |
| Curb Weight |     0.2949 |
| Highway MPG |     0.0434 |
| Horsepower  |     0.0383 |
| Car Width   |     0.0134 |

Engine size and curb weight were the two most influential features in the Random Forest model.

## 💡 Key Insights

* Engine size has the highest predictive importance.
* Curb weight is another major contributor to price prediction.
* Horsepower and highway mileage also contribute to the model.
* The tuned Random Forest model achieved an R² score of approximately 95.45%.

## ⚠️ Limitations

* The dataset contains only 205 records.
* The dataset may not represent the entire US automobile market.
* Model performance depends on the available dataset and its characteristics.
* Feature importance indicates predictive contribution, not causation.


## ▶️ How to Run the Project

1. Clone the repository.
2. Install the required Python libraries.
3. Open Jupyter Notebook.
4. Open `Car_Price_Prediction.ipynb`.
5. Run the notebook cells sequentially.

## 🔮 Future Scope

* Use a larger and more recent automobile dataset.
* Explore additional regression algorithms.
* Develop a web application for interactive car price prediction.
* Improve model generalization through additional validation.

## 👩‍💻 Author

**Smanya E S**



GitHub: [smanyaes63-dev](https://github.com/smanyaes63-dev)
