# 🚀 BLEVE Pressure Prediction using Machine Learning

## 📌 Project Overview

This project applies machine learning to predict **peak pressure values** associated with **Boiling Liquid Expanding Vapour Explosion (BLEVE)** scenarios. BLEVEs are high-risk industrial safety events that can occur during hazardous material transportation, particularly involving substances such as Liquefied Petroleum Gas (LPG).

The aim of this project is to build a predictive model that can estimate BLEVE peak pressure more accurately from structured scenario data. The project follows a complete machine learning workflow, including data cleaning, preprocessing, feature engineering, model selection, hyperparameter tuning, evaluation, and final prediction.

The final model selected was **XGBoost**, which achieved the strongest overall performance among the tested models.

---

## 🎯 Purpose of the Project

The main purpose of this project is to explore how machine learning can support **industrial risk analysis and emergency response planning** by predicting peak pressure outcomes from simulated BLEVE scenarios.

More specifically, the project aims to:

- Clean and prepare BLEVE scenario data for machine learning.
- Engineer useful features from tank and scenario-related variables.
- Compare multiple regression models for peak pressure prediction.
- Tune model hyperparameters to improve performance.
- Select the best-performing model based on regression metrics.
- Generate final predictions using the strongest model.

---

## 🧠 Problem Statement

Traditional approaches to estimating BLEVE pressure effects can struggle because the physical processes involved are complex and non-linear. Factors such as tank dimensions, scenario conditions, and pressure propagation patterns may interact in ways that are difficult to capture using simple linear assumptions.

This project addresses that challenge by testing different machine learning regression models to identify which model can best learn the relationship between the available input features and the target pressure values.

---

## 📁 Repository Structure

```text
BLEVE_Pressure_Prediction/
│
├── README.md
├── Main.ipynb
├── Project Documentation.pdf
│
└── Data/
    ├── training_data.csv
    ├── testing_data.csv
    └── prediction_data.csv
```

### Folder and File Guide

| File / Folder | Description |
|---|---|
| `README.md` | Main project summary and guide. |
| `Main.ipynb` | Jupyter Notebook containing the full machine learning workflow. |
| `Project Documentation.pdf` | Full written report explaining the methodology, models, results, limitations, and conclusion. |
| `Data/training_data.csv` | Dataset used to train the machine learning models. |
| `Data/testing_data.csv` | Dataset used to evaluate model performance. |
| `Data/prediction_data.csv` | Dataset used to generate final predictions using the selected model. |

---

## 🔗 Full Code and Results

The full implementation is available in the notebook:

```text
Main.ipynb
```

If the notebook is uploaded to GitHub, you can add a Google Colab badge here:

```markdown
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](PASTE_YOUR_COLAB_LINK_HERE)
```

---

## 🧹 Data Cleaning

Data cleaning was an important part of this project because the quality of the input data directly affects model performance.

The following cleaning steps were applied:

### 1. Missing Values

- The `Tank Length` column contained zero values.
- These zero values were treated as invalid because a tank length of zero is not physically meaningful.
- The zero values were replaced with missing values (`NaN`).
- Rows containing missing values in `Tank Length` were removed because this feature was important for modelling BLEVE pressure outcomes.

### 2. Outlier Treatment

- Outliers were detected across numerical columns using the **Interquartile Range (IQR)** method.
- Values below `Q1 - 1.5 × IQR` or above `Q3 + 1.5 × IQR` were treated as outliers.
- Instead of deleting these rows, outliers were capped at the lower and upper bounds.
- This reduced the influence of extreme values while preserving the dataset size.

### 3. Duplicate Checks

- The dataset was checked for duplicate records.
- Removing duplicates helped prevent the model from learning repeated patterns that could lead to biased or overfitted results.

### 4. Incorrect or Unrealistic Entries

- The dataset was reviewed for values that were not realistic within the context of BLEVE scenario modelling.
- Invalid entries were corrected or removed where appropriate to improve data reliability.

### 5. Gaussian Noise

- Gaussian noise was added to selected numerical features to make the data more realistic and test model robustness.
- This helped simulate small variations that may occur in real-world data.

---

## ⚙️ Data Processing and Feature Engineering

After cleaning, the data was processed so that it could be used effectively by machine learning models.

### Techniques Used

| Technique | Purpose |
|---|---|
| Feature engineering | Created additional useful variables from existing features. |
| Dummy encoding | Converted categorical variables into numerical format. |
| Scaling / standardisation | Ensured numerical features were on comparable scales. |
| Train-test preparation | Prepared separate datasets for training, testing, and prediction. |
| Consistent transformation | Applied the same preprocessing logic to training and testing data. |

### Feature Engineering Example

A new feature called `Width_Length_Ratio` was created by dividing tank height by tank length.

This feature was useful because it represented the relationship between tank dimensions, which may influence how pressure behaves in the BLEVE scenario.

---

## 🤖 Machine Learning Models Used

Several regression models were tested to compare their predictive performance.

| Model | Why It Was Used |
|---|---|
| Linear Regression | Used as a simple baseline model to test linear relationships. |
| Decision Tree Regressor | Used for interpretability and to capture non-linear patterns. |
| Random Forest Regressor | Used because ensemble trees can handle non-linear relationships and reduce overfitting. |
| Support Vector Regression (SVR) | Used to test performance in higher-dimensional feature spaces. |
| Gradient Boosting Regressor | Used because boosting can improve predictions by learning from previous errors. |
| XGBoost Regressor | Used because it is powerful for structured/tabular data and often performs well on regression tasks. |

---

## 🔧 Hyperparameter Tuning

Hyperparameter tuning was carried out to improve model performance and reduce the risk of underfitting or overfitting.

### Tuning Method

- **GridSearchCV** was used to test different parameter combinations.
- Models were compared using cross-validation.
- The aim was to find the best balance between model complexity and predictive accuracy.

### Examples of Tuned Parameters

| Model | Parameters Tuned |
|---|---|
| Random Forest | `n_estimators`, `max_depth` |
| SVR | `C`, `kernel` |
| Gradient Boosting | `learning_rate`, `max_depth` |
| XGBoost | `learning_rate`, `max_depth`, `n_estimators` |

The selected XGBoost configuration used:

```text
learning_rate = 0.1
max_depth = 5
n_estimators = 200
```

---

## 📊 Model Performance Results

The models were evaluated using three regression metrics:

- **Mean Squared Error (MSE)**: Measures average squared prediction error. Lower is better.
- **Mean Absolute Error (MAE)**: Measures average absolute prediction error. Lower is better.
- **R² Score**: Measures how much variance in the target variable is explained by the model. Higher is better.

| Model | MSE | MAE | R² Score |
|---|---:|---:|---:|
| Linear Regression | 0.02279 | 0.11635 | 0.65045 |
| Decision Tree | 0.00926 | 0.05635 | 0.85798 |
| SVR | 0.00532 | 0.05724 | 0.91837 |
| Random Forest | 0.00420 | 0.04129 | 0.93559 |
| Gradient Boosting | 0.00410 | 0.04386 | 0.93709 |
| **XGBoost** | **0.00402** | **0.04332** | **0.93827** |

---

## 🏆 Best Model: XGBoost

**XGBoost** was selected as the final model because it achieved the best overall performance:

```text
MSE: 0.00402
MAE: 0.04332
R² Score: 0.93827
```

This means that XGBoost explained approximately **93.8% of the variance** in the target pressure values.

### Why XGBoost Performed Best

XGBoost performed well because:

- The dataset was structured/tabular, which suits tree-based boosting models.
- It captured non-linear relationships better than Linear Regression.
- It corrected prediction errors sequentially through boosting.
- It handled feature interactions effectively.
- It achieved slightly better performance than Random Forest and Gradient Boosting.

---

## 🔍 Key Findings

- Data cleaning and preprocessing had a major impact on final model accuracy.
- Outlier handling was important because extreme values could distort regression performance.
- Feature engineering improved the model’s ability to learn useful relationships.
- Ensemble models performed better than simpler models.
- XGBoost produced the strongest predictive results among all tested models.
- The project showed that machine learning can be useful for modelling complex industrial safety scenarios involving non-linear relationships.

---

## 🧪 How to Run the Project

### Option 1: Run in Jupyter Notebook

1. Clone or download this repository.
2. Open the notebook:

```text
Main.ipynb
```

3. Install the required Python libraries if needed.
4. Run the notebook cells from top to bottom.

### Option 2: Run in Google Colab

1. Upload `Main.ipynb` to Google Colab.
2. Upload the required CSV files from the `Data/` folder.
3. Run all cells.

---

## 🛠️ Main Tools and Libraries

| Tool / Library | Purpose |
|---|---|
| Python | Main programming language. |
| Pandas | Data loading, cleaning, and preprocessing. |
| NumPy | Numerical operations. |
| Scikit-learn | Model training, preprocessing, metrics, and GridSearchCV. |
| XGBoost | Final best-performing regression model. |
| Jupyter Notebook / Google Colab | Development and experimentation environment. |

---

## ⚠️ Limitations

Although the project achieved strong results, there are some limitations:

- The dataset was based on simulated BLEVE scenarios, so real-world testing would be needed before practical deployment.
- More domain-specific features could improve predictive accuracy.
- The project focused on regression performance rather than full deployment.
- The model may not generalise perfectly to BLEVE scenarios outside the range of the training data.
- Further validation would be required before using the model in any real safety-critical setting.

---

## 🚀 Future Improvements

Future work could include:

- Collecting more data from additional BLEVE scenarios.
- Testing more advanced ensemble models.
- Exploring deep learning models if a larger dataset becomes available.
- Performing more systematic feature selection.
- Creating a simple web app or dashboard for user-friendly predictions.
- Adding visual explanations of feature importance.
- Testing the model on real-world or higher-fidelity simulation data.

---

## 🧾 Summary

This project demonstrates a complete machine learning pipeline for BLEVE peak pressure prediction. After cleaning and processing the data, several regression models were tested and tuned. XGBoost achieved the best performance, showing strong predictive accuracy with an R² score of **0.93827**.

The project highlights the value of machine learning in supporting risk analysis, industrial safety research, and emergency planning by modelling complex non-linear pressure outcomes from simulated BLEVE scenarios.

---

## 👤 Author

**Gautam Kumar Rai Ramessur**  
Machine Learning Project — COMP3010 / COMP6013
