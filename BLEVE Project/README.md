

# 🚀 BLEVE Pressure Prediction using Machine Learning

Welcome to the repository for the project **"BLEVE Pressure Prediction using Machine Learning"**. This project leverages advanced machine learning techniques to predict the peak pressures resulting from Boiling Liquid Expanding Vapour Explosions (BLEVEs) in transportation scenarios involving hazardous materials like Liquefied Petroleum Gas (LPG).

## 📂 Repository Contents

This repository consists of the following files:

1. **`Main.ipynb`** - The main Jupyter Notebook containing the full implementation of the machine learning models, from data preprocessing to final predictions.
2. **`Project Documentation.pdf`** - Comprehensive documentation of the entire project, detailing the methodology, data processing steps, model selection, hyperparameter tuning, and results analysis.
3. **`Data/`** - This folder contains all the datasets used in this project, including:
   - **`training_data.csv`** - The dataset used to train the models.
   - **`prediction_data.csv`** - The dataset used for making predictions.
   - **`testing_data.csv`** - The dataset used for testing and evaluating the models.

## 📖 Project Overview

The transportation of hazardous materials, particularly LPG, through densely populated areas poses significant safety risks. This project aims to enhance predictive accuracy and response strategies by employing machine learning techniques to estimate peak pressures from BLEVEs.

### Key Steps:
- **Data Cleaning**: Addressing missing values, outliers, and duplicates.
- **Data Processing**: Feature engineering, scaling, and encoding.
- **Model Selection**: Testing and tuning various models including Random Forest, Support Vector Regression, Gradient Boosting, and XGBoost.
- **Prediction**: Utilizing the best-performing model (XGBoost) for final predictions.

## 📊 Results

The XGBoost model emerged as the best-performing model, achieving:
- **Mean Squared Error (MSE):** 0.00402
- **Mean Absolute Error (MAE):** 0.04332
- **R² Score:** 0.93827

These results highlight the effectiveness of ensemble methods in predicting complex outcomes like BLEVE peak pressures.

## 💡 Key Learnings and Future Work

- **Data Preprocessing:** Thorough data cleaning and preprocessing significantly improve model accuracy.
- **Feature Engineering:** Creating new features that capture nuanced information can enhance predictive performance.
- **Model Tuning:** Systematic hyperparameter tuning is crucial for optimizing model performance.

Future work could involve exploring more advanced machine learning models, gathering additional data, and applying the models in real-world scenarios.

## 📝 How to Use This Repository

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/YourUsername/BLEVE-Pressure-Prediction.git
   ```
2. **Run the Notebook:**
   - Open `Main.ipynb` in Google Colab or Jupyter Notebook.
   - Execute the cells to see the data processing, model training, and predictions.

## 🧑‍💻 Contributions

Contributions are welcome! Please feel free to fork this repository, create a branch, and submit a pull request with your improvements.

