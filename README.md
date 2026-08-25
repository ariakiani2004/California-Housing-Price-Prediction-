# California Housing Price Prediction 

A compact end-to-end Machine Learning project for predicting median house values in California using structured housing data.

This project is designed as a clean and beginner-friendly GitHub portfolio project. It demonstrates the complete supervised learning workflow, from data inspection and preprocessing to model comparison, evaluation, and feature importance analysis.

---

## Project Overview

The objective of this project is to predict **`median_house_value`** using demographic, geographic, and housing-related features.

The notebook compares three regression approaches:

- **Median Baseline**
- **Linear Regression**
- **Random Forest Regressor**

The final results show that the Random Forest model performs substantially better than the linear model, suggesting that the relationship between the available housing features and house prices contains important non-linear patterns and interactions.

---

## Dataset

The dataset contains:

- **20,640 rows**
- **10 columns**
- Numerical and categorical features
- Missing values in some observations
- Target variable: **`median_house_value`**

### Main Features

| Feature | Description |
|---|---|
| `longitude` | Geographic longitude |
| `latitude` | Geographic latitude |
| `housing_median_age` | Median age of houses in the area |
| `total_rooms` | Total number of rooms |
| `total_bedrooms` | Total number of bedrooms |
| `population` | Population of the area |
| `households` | Number of households |
| `median_income` | Median household income |
| `ocean_proximity` | Categorical location relative to the ocean |
| `median_house_value` | Target variable |

---

## Machine Learning Workflow

The project follows a simple and reproducible workflow:

1. Load and inspect the dataset
2. Examine data types and missing values
3. Perform exploratory data analysis
4. Investigate relationships between features and house values
5. Split the data into training and testing sets
6. Build preprocessing pipelines for numerical and categorical variables
7. Train multiple regression models
8. Compare models using standard regression metrics
9. Visualize actual vs. predicted values
10. Analyze Random Forest feature importance

---

## Data Preprocessing

The preprocessing pipeline is built with **scikit-learn** using `ColumnTransformer` and `Pipeline`.

### Numerical Features

Numerical variables are processed using:

- `SimpleImputer`
- `StandardScaler`

### Categorical Features

The categorical variable is processed using:

- `SimpleImputer`
- `OneHotEncoder`

Using pipelines helps prevent data leakage and keeps the preprocessing and modeling workflow reproducible.

---

## Models

### 1. Median Baseline

A `DummyRegressor` using the median strategy is used as a baseline.

This provides a simple reference point for determining whether the Machine Learning models actually learn useful patterns from the data.

### 2. Linear Regression

Linear Regression provides an interpretable linear benchmark.

### 3. Random Forest Regressor

The Random Forest model is configured with:

```python
RandomForestRegressor(
    n_estimators=120,
    max_depth=14,
    min_samples_leaf=2,
    random_state=42,
    n_jobs=-1
)
```

---

## Model Performance

The models are evaluated using:

- **MAE — Mean Absolute Error**
- **RMSE — Root Mean Squared Error**
- **R² — Coefficient of Determination**

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| **Random Forest** | **32,391** | **49,656** | **0.812** |
| Linear Regression | 50,670 | 70,059 | 0.625 |
| Median Baseline | 87,404 | 117,312 | -0.050 |

### Best Model

The **Random Forest Regressor** achieved the strongest performance:

- **MAE:** 32,391
- **RMSE:** 49,656
- **R²:** 0.812

An R² score of approximately **0.81** indicates that the model explains a substantial portion of the variation in median house values in the test set.

---

## Visualizations

The notebook includes several visual analyses, including:

- Distribution of the target variable
- Relationship between median income and house value
- Correlation analysis
- Actual vs. predicted values
- Random Forest feature importance

These visualizations help interpret both the dataset and the final model.

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---

## Project Structure

```text
california-housing-price-prediction/
│
├── california_housing_price_prediction.ipynb
├── housing.csv
└── README.md
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/ariakiani2004/california-housing-price-prediction.git
cd california-housing-price-prediction
```

Install the required libraries:

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

---

## Running the Project

Make sure that `housing.csv` is located in the same directory as the notebook.

Then start Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
california_housing_price_prediction.ipynb
```

and run the cells from top to bottom.

The notebook also checks the following dataset paths:

```text
housing.csv
housing(1).csv
data/housing.csv
```

---

## Key Takeaways

This project demonstrates several fundamental Machine Learning concepts:

- Building a complete regression workflow
- Handling missing values
- Encoding categorical features
- Scaling numerical features
- Using `ColumnTransformer` and `Pipeline`
- Establishing a baseline model
- Comparing linear and non-linear algorithms
- Evaluating regression models with multiple metrics
- Interpreting feature importance

The results also highlight an important modeling insight: **Random Forest captures the structure of this dataset significantly better than Linear Regression**, indicating that housing prices are influenced by non-linear relationships and feature interactions.

---

## Possible Future Improvements

This project is intentionally kept compact, but it could be extended with:

- Cross-validation
- Additional feature engineering
- Hyperparameter tuning
- Gradient Boosting or XGBoost
- Model persistence with `joblib`
- A Streamlit web application
- More detailed geographic visualizations

---

## Why This Project?

The purpose of this repository is to demonstrate a clear and reproducible introductory Machine Learning workflow without unnecessary complexity.

It is suitable for:

- Machine Learning practice
- Data Science portfolios
- GitHub project showcases
- Learning scikit-learn pipelines
- Practicing regression model evaluation

---

## Author

Created as a Machine Learning portfolio project.

If you find this project useful, feel free to star the repository. 
