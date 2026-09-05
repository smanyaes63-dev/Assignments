# California Housing Regression Analysis

## 📌 Project Overview

This project evaluates different regression techniques in supervised machine learning using the **California Housing dataset**. The objective is to implement multiple regression algorithms, evaluate their performance, and compare their results using standard regression metrics.

Five regression algorithms were implemented:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* Gradient Boosting Regressor
* Support Vector Regressor (SVR)

## 📊 Dataset

The **California Housing dataset** is obtained from `sklearn.datasets`.

* Number of samples: **20,640**
* Number of features: **8**
* Target variable: **MedHouseVal**
* Target represents the median house value for California districts.

### Features

* MedInc
* HouseAge
* AveRooms
* AveBedrms
* Population
* AveOccup
* Latitude
* Longitude

## 🔧 Data Preprocessing

The following preprocessing steps were performed:

1. The California Housing dataset was loaded using Scikit-learn.
2. The dataset was converted into a Pandas DataFrame.
3. Missing values were checked; no missing values were found.
4. The features and target variable were separated.
5. The dataset was divided into training and testing sets using an **80:20 split**.
6. Feature scaling using `StandardScaler` was applied for models that benefit from scaled features, particularly SVR and Linear Regression.

Tree-based models such as Decision Tree, Random Forest, and Gradient Boosting were trained using the original feature values because feature scaling is not required for these algorithms.

## 🤖 Regression Algorithms

### Linear Regression

Linear Regression models the relationship between the input features and the target variable using a linear equation. It was used as a baseline model to evaluate how well a simple linear relationship can represent the housing data.

### Decision Tree Regressor

Decision Tree Regressor predicts continuous values by splitting the dataset based on feature values. It can capture nonlinear relationships and does not require feature scaling.

### Random Forest Regressor

Random Forest combines predictions from multiple decision trees to produce a more robust prediction. It can capture complex nonlinear relationships and interactions between housing features.

### Gradient Boosting Regressor

Gradient Boosting builds decision trees sequentially, with each new tree attempting to reduce the errors made by previous trees. It is suitable for learning complex patterns in the dataset.

### Support Vector Regressor (SVR)

SVR predicts continuous values by finding a function that fits the data within a specified margin of error. An RBF kernel was used to capture nonlinear relationships. Feature scaling was applied because SVR is sensitive to feature scales.

## 📏 Evaluation Metrics

The models were evaluated using:

* **Mean Squared Error (MSE):** Lower values indicate better performance.
* **Mean Absolute Error (MAE):** Lower values indicate better performance.
* **R² Score:** Higher values indicate better performance.

## 📈 Results

| Model             |      MSE ↓ |      MAE ↓ |       R² ↑ |
| ----------------- | ---------: | ---------: | ---------: |
| Linear Regression |     0.5559 |     0.5332 |     0.5758 |
| Decision Tree     |     0.4952 |     0.4547 |     0.6221 |
| **Random Forest** | **0.2554** | **0.3275** | **0.8051** |
| Gradient Boosting |     0.2940 |     0.3716 |     0.7756 |
| SVR               |     0.3570 |     0.3986 |     0.7276 |

## 🏆 Best Performing Model

The **Random Forest Regressor** achieved the best overall performance.

It obtained:

* **MSE:** 0.2554
* **MAE:** 0.3275
* **R²:** 0.8051

It achieved the lowest MSE and MAE and the highest R² score among all five models. This indicates that Random Forest was able to capture the complex nonlinear relationships in the California Housing dataset effectively.

## 📉 Worst Performing Model

**Linear Regression** showed the weakest overall performance, with:

* **MSE:** 0.5559
* **MAE:** 0.5332
* **R²:** 0.5758

The results suggest that a simple linear relationship is not sufficient to fully represent the complex patterns between the housing features and median house values.

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn
* Jupyter Notebook
* GitHub

```

## ▶️ How to Run

1. Clone or download this repository.
2. Open `California_Housing_Regression.ipynb` using Jupyter Notebook or JupyterLab.
3. Install the required Python libraries if necessary.
4. Run the notebook cells from beginning to end.

## 📝 Conclusion

This project demonstrates the implementation and comparison of five supervised regression algorithms on the California Housing dataset. Among the evaluated models, **Random Forest Regressor performed the best**, achieving an R² score of 0.8051. The results show that ensemble and nonlinear models can capture the complex relationships in the dataset more effectively than simple Linear Regression.
