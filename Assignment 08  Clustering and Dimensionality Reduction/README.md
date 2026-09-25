# California Housing Regression and Evaluation

## Project Overview

This project implements and evaluates multiple regression algorithms using the **California Housing dataset** from Scikit-learn.

The main objective is to compare different regression models, evaluate their performance using multiple metrics, apply cross-validation and hyperparameter tuning, and select the most suitable model based on the experimental results.

---

## Dataset

The California Housing dataset contains information about housing districts in California.

* **Samples:** 20,640
* **Input Features:** 8
* **Target Variable:** `MedHouseVal`

### Features

| Feature    | Description                         |
| ---------- | ----------------------------------- |
| MedInc     | Median income in the block group    |
| HouseAge   | Median house age                    |
| AveRooms   | Average number of rooms             |
| AveBedrms  | Average number of bedrooms          |
| Population | Block group population              |
| AveOccup   | Average number of household members |
| Latitude   | Geographic latitude                 |
| Longitude  | Geographic longitude                |

The target variable `MedHouseVal` represents the median house value.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Data Preprocessing

The dataset was loaded using `fetch_california_housing()` and converted into a Pandas DataFrame.

The following preprocessing steps were performed:

1. Dataset inspection
2. Missing-value checking
3. Duplicate checking
4. Exploratory Data Analysis (EDA)
5. Train-test splitting
6. Feature scaling using `StandardScaler`

Scaling was applied to models that are sensitive to feature magnitudes, particularly **Linear Regression and SVR**. The scaler was fitted only on the training data and then used to transform the test data to avoid data leakage.

---

## Exploratory Data Analysis

EDA was performed using:

* Descriptive statistics
* Target-variable distribution
* Feature distributions
* Correlation heatmap
* Feature correlation with the target variable

These visualizations were used to understand the structure of the dataset and relationships between the features and house values.

---

## Regression Models

Five regression algorithms were implemented:

### 1. Linear Regression

A basic linear regression model used as a baseline for comparison.

### 2. Decision Tree Regressor

A tree-based model that learns decision rules from the training data.

### 3. Random Forest Regressor

An ensemble of multiple decision trees. It can capture nonlinear relationships and generally provides more robust predictions than a single decision tree.

### 4. Gradient Boosting Regressor

An ensemble method that builds models sequentially, where each new model attempts to improve the errors made by previous models.

### 5. Support Vector Regression (SVR)

A support-vector-based regression algorithm. Feature scaling was applied because SVR is sensitive to feature magnitudes.

---

## Model Evaluation

The models were evaluated using:

* **Mean Squared Error (MSE)** — lower values indicate smaller squared prediction errors.
* **Mean Absolute Error (MAE)** — lower values indicate smaller average absolute prediction errors.
* **R² Score** — higher values indicate that the model explains a larger proportion of the variation in the target variable.

### Final Test-Set Results

| Model             |      MSE |      MAE | R² Score |
| ----------------- | -------: | -------: | -------: |
| Linear Regression | 0.555892 | 0.533200 | 0.575788 |
| Decision Tree     | 0.408405 | 0.431115 | 0.688338 |
| Random Forest     | 0.255867 | 0.327930 | 0.804743 |
| Gradient Boosting | 0.237774 | 0.327401 | 0.818549 |
| SVR               | 0.313522 | 0.373005 | 0.760745 |

The tuned Gradient Boosting model obtained the highest test R² and the lowest MSE and MAE among the evaluated models.

---

## Cross-Validation

Five-fold cross-validation was performed on the training dataset.

### Baseline CV Results

| Model             | Mean CV R² |
| ----------------- | ---------: |
| Linear Regression |     0.6115 |
| Decision Tree     |     0.5973 |
| Random Forest     |     0.8045 |
| Gradient Boosting |     0.7881 |
| SVR               |     0.7363 |

Cross-validation was used to obtain a more reliable estimate of model performance across different validation folds.

---

## Hyperparameter Tuning

Hyperparameter tuning was performed using **GridSearchCV** for Linear Regression, Decision Tree, Random Forest, and Gradient Boosting.

**RandomizedSearchCV** was used for SVR because searching through the parameter combinations can be computationally expensive.

### Best Hyperparameters

| Model             | Best Hyperparameters                                        | Tuned CV R² |
| ----------------- | ----------------------------------------------------------- | ----------: |
| Linear Regression | `fit_intercept=True`                                        |      0.6115 |
| Decision Tree     | `max_depth=10`, `min_samples_leaf=4`, `min_samples_split=2` |      0.7101 |
| Random Forest     | `max_depth=20`, `min_samples_split=2`, `n_estimators=100`   |      0.8046 |
| Gradient Boosting | `learning_rate=0.1`, `max_depth=4`, `n_estimators=200`      |      0.8217 |
| SVR               | `C=50`, `gamma='scale'`, `epsilon=0.2`                      |      0.7622 |

### Effect of Hyperparameter Tuning

Hyperparameter tuning improved the performance of several models.

The largest improvement was observed for the Decision Tree, whose CV R² increased from approximately **0.5973 to 0.7101**.

Gradient Boosting improved from approximately **0.7881 to 0.8217**.

Random Forest showed only a small improvement because its baseline configuration was already performing strongly.

---

## Final Model

Based on the evaluation, cross-validation, and hyperparameter tuning results, the **tuned Gradient Boosting Regressor** was selected as the final model for this experiment.

### Selected Hyperparameters

```text
learning_rate = 0.1
max_depth = 4
n_estimators = 200
```

### Performance

* **Test R²:** 0.8185
* **Test MSE:** 0.2378
* **Test MAE:** 0.3274
* **Tuned CV R²:** 0.8217

Random Forest also showed strong performance with a test R² of approximately **0.8047**.

---

## Model Analysis

Additional analysis was performed using:

* Actual vs Predicted plot
* Residual plot
* Residual distribution

These plots were used to examine the prediction behaviour and error distribution of the final Gradient Boosting model.

---

## How to Run

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
```

### 2. Open the project folder

### 3. Install the required libraries

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook and run the cells sequentially.

---

## Conclusion

This project demonstrates the implementation, evaluation, cross-validation, and hyperparameter tuning of five regression algorithms on the California Housing dataset.

The experiment showed that ensemble tree-based methods performed strongly on this dataset. After tuning and evaluation, the **Gradient Boosting Regressor** achieved the strongest performance among the evaluated models, with a test R² of **0.8185** and a tuned cross-validation R² of **0.8217**.

The project provides a practical comparison of regression algorithms and demonstrates the importance of model evaluation, cross-validation, and hyperparameter tuning in selecting a regression model.
