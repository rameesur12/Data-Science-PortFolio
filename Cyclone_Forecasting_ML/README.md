# 🌪️ Machine Learning for Tropical Cyclone Intensity Prediction

## 📌 Project Overview

This project applies **machine learning and deep learning techniques** to predict and analyse **tropical cyclone intensity**. The main prediction target is **maximum wind speed**, which is used as a practical indicator of cyclone strength.

The project combines cyclone track data with atmospheric and oceanic variables to investigate whether data-driven models can support cyclone intensity analysis. It also uses statistical hypothesis testing to check whether important meteorological relationships are visible in the data before comparing different predictive models.

This repository is the GitHub portfolio version of my MSc Data Science dissertation:

**Using Machine Learning to Predict and Analyse Cyclone Events: A Data-Driven Approach to Tropical Storm Forecasting**

The full dissertation report is included in the project folder as supporting documentation. The README gives a clear project summary, methodology, techniques used, hypotheses, model results, findings and folder guide.

---
## 🔗 Full Code and Results

The complete notebook, including data preprocessing, exploratory data analysis, hypothesis testing, model training, evaluation metrics, and visual outputs, is available here:

[Open in Google Colab]
https://colab.research.google.com/drive/1znLXIi6CMnMk_Uu-z6iZUISnyBzw0Vgw?usp=sharing

## 🎯 Project Aim

The aim of this project was to evaluate how effectively machine learning and deep learning models can predict and explain tropical cyclone intensity using structured meteorological data.

The project focused on:

1. Cleaning and preparing cyclone-related datasets.
2. Integrating cyclone track data with environmental variables.
3. Engineering useful features for cyclone intensity prediction.
4. Testing meteorological hypotheses using statistical correlation methods.
5. Training and comparing multiple machine learning and deep learning models.
6. Explaining why some models performed better than others.

This project is **not intended to replace official meteorological forecasting systems**. It is a data science project showing how machine learning can be used as a supporting analytical tool for cyclone intensity research and disaster preparedness.

---

## ❓ Problem Statement

Tropical cyclone intensity prediction is difficult because cyclone behaviour is affected by several interacting factors, including central pressure, wind speed, sea surface temperature, storm duration, basin location and atmospheric conditions.

Traditional forecasting systems remain the operational standard, but machine learning can help identify patterns in historical cyclone and environmental data. This project investigates whether ML models can learn useful relationships from cyclone data and predict maximum wind speed with reasonable accuracy.

---

## 📂 Datasets Used

The project is mainly based on two core data sources.

### 1. IBTrACS Cyclone Data

The **International Best Track Archive for Climate Stewardship (IBTrACS)** provides tropical cyclone track and intensity records. In this project, it was used for cyclone-related features such as:

- Storm identifier
- Date and time
- Latitude and longitude
- Basin
- Maximum wind speed
- Minimum central pressure
- Storm duration

### 2. ERA5 Reanalysis Data

The **ERA5 reanalysis dataset** provides atmospheric and oceanic variables. In this project, ERA5 files were processed in NetCDF format and used for variables such as:

- Mean Sea Level Pressure (MSLP)
- Sea Surface Temperature (SST)
- 10 m U-wind component
- 10 m V-wind component

The cyclone data and ERA5 variables were combined to create a modelling dataset for hypothesis testing and machine learning.

### Practical Dataset Scope

The GitHub project files are organised around the **2019-2020 modelling workflow**, as reflected in the processed files:

- `ibtracs_era5_2019_2020.csv`
- `train_unscaled_2019_2020.csv`
- `test_unscaled_2019_2020.csv`
- `baseline_results_2019_2020.csv`
- `scaled_artifacts_2019_2020.pkl`

---

## 🗂️ Recommended Repository Structure

The main GitHub page should contain only the README, the main Python script and the project files folder.

```text
cyclone-forecasting-ml/
│
├── README.md
├── cyclone_forecasting_ml.py
│
└── project_files/
    │
    ├── notebooks/
    │   └── CST4090_Dissertation.ipynb
    │
    ├── data/
    │   ├── raw/
    │   │   ├── storms.csv
    │   │   ├── era5_20160628_box.nc
    │   │   ├── era5_20160628_box (1).nc
    │   │   └── era5_test.nc
    │   │
    │   └── processed/
    │       ├── ibtracs_era5_2019_2020.csv
    │       ├── train_unscaled_2019_2020.csv
    │       ├── test_unscaled_2019_2020.csv
    │       └── baseline_results_2019_2020.csv
    │
    ├── models/
    │   └── scaled_artifacts_2019_2020.pkl
    │
    ├── reports/
    │   ├── CST4090_M01038646_Dissertation_Report.pdf
    │   ├── CST4090-E-Poster_Gautam_Kumar_Rai_Ramessur.pdf
    │   └── Project_Proposal_CST4090.pdf
    │
    └── outputs/
        └── model_results_and_visuals/
```

---

## 🧭 Folder and File Guide

| File / Folder | Purpose |
|---|---|
| `README.md` | Main project explanation for GitHub. This is what recruiters should read first. |
| `cyclone_forecasting_ml.py` | Clean Python script showing the main workflow from loading data to model comparison. |
| `project_files/notebooks/CST4090_Dissertation.ipynb` | Original Jupyter Notebook containing the full analysis and experimentation. |
| `project_files/data/raw/storms.csv` | Raw cyclone/storm data file. |
| `project_files/data/raw/era5_20160628_box.nc` | ERA5 NetCDF weather data file. |
| `project_files/data/raw/era5_20160628_box (1).nc` | Second ERA5 NetCDF file from the project folder. |
| `project_files/data/raw/era5_test.nc` | ERA5 test NetCDF file used during experimentation or testing. |
| `project_files/data/processed/ibtracs_era5_2019_2020.csv` | Main merged dataset combining cyclone records and ERA5 predictors. |
| `project_files/data/processed/train_unscaled_2019_2020.csv` | Training dataset before scaling. |
| `project_files/data/processed/test_unscaled_2019_2020.csv` | Test dataset before scaling. |
| `project_files/data/processed/baseline_results_2019_2020.csv` | Baseline/model result file used to store model performance outputs. |
| `project_files/models/scaled_artifacts_2019_2020.pkl` | Saved preprocessing artifact, such as scaling objects or related model preparation files. |
| `project_files/reports/CST4090_M01038646_Dissertation_Report.pdf` | Full dissertation report. This is supporting evidence, not the main project explanation. |
| `project_files/reports/CST4090-E-Poster_Gautam_Kumar_Rai_Ramessur.pdf` | E-poster summarising the project visually. Useful as demonstration material. |
| `project_files/reports/Project_Proposal_CST4090.pdf` | Original project proposal. |
| `project_files/outputs/model_results_and_visuals/` | Folder for exported charts, model result tables and demonstration outputs. |

---

## 🛠️ Tools and Libraries Used

The project was implemented in **Python** using **Google Colab**.

| Tool / Library | Purpose |
|---|---|
| `pandas` | Loading, cleaning and manipulating tabular data. |
| `numpy` | Numerical calculations and array operations. |
| `xarray` | Handling ERA5 NetCDF weather files. |
| `matplotlib` | Creating plots and visualisations. |
| `seaborn` | Statistical visualisation during exploratory analysis. |
| `scikit-learn` | Preprocessing, scaling, model training and evaluation. |
| `scipy` | Pearson and Spearman correlation testing. |
| `xgboost` | Training the XGBoost regression model. |
| `lightgbm` | Training the LightGBM regression model. |
| `tensorflow` / `keras` | Training deep learning models such as LSTM and TCN. |
| `pickle` / `.pkl` files | Saving preprocessing artifacts such as scalers. |

---

## 🔄 Data Science Workflow

The project followed a complete data science workflow.

### 1. Data Collection

Cyclone track data was collected from IBTrACS and environmental data was extracted from ERA5 reanalysis files.

IBTrACS provided the core cyclone information, while ERA5 provided additional atmospheric and oceanic variables that could help explain cyclone intensity.

### 2. Data Cleaning

The cleaning stage included:

- Removing duplicate cyclone records.
- Handling missing values.
- Interpolating missing wind speed or pressure values where appropriate.
- Standardising storm identifiers.
- Filtering the dataset to keep only relevant variables.
- Checking date, latitude, longitude, wind speed and pressure fields.
- Preparing the data for merging with ERA5 variables.

This was important because cyclone data can come from different reporting agencies and may contain inconsistencies.

### 3. ERA5 NetCDF Processing

ERA5 data was stored in `.nc` NetCDF format. These files were processed using `xarray`.

The processing included:

- Loading NetCDF files.
- Selecting relevant variables such as SST, MSLP, U-wind and V-wind.
- Restricting data to the relevant tropical cyclone region.
- Matching ERA5 values to cyclone latitude and longitude points.
- Aligning ERA5 time values with cyclone observation times.
- Using interpolation where required to match environmental data with cyclone records.

### 4. Data Integration

The cyclone records and ERA5 environmental predictors were merged into one modelling dataset.

The final modelling data included two broad feature groups:

**Storm-specific features**

- Maximum wind speed
- Minimum central pressure
- Latitude
- Longitude
- Basin
- Storm duration

**Environmental features**

- Sea surface temperature
- Mean sea level pressure
- U-wind component
- V-wind component
- Wind magnitude features

### 5. Feature Engineering

Feature engineering transformed raw meteorological variables into predictors that could be used by the models.

| Feature | Why it was used |
|---|---|
| Storm duration | Longer storms may have more time to intensify. |
| Average latitude | Used to test whether cyclone location is related to intensity. |
| Minimum central pressure | A key structural indicator of cyclone intensity. |
| Wind speed magnitude | Created from U-wind and V-wind components. |
| SST-related features | Used to represent ocean surface conditions. |
| Basin information | Captures regional differences between cyclone basins. |

### 6. Scaling and Normalisation

Different models required different preprocessing strategies.

- Classical ML models used standardisation where required.
- Deep learning models used normalisation to stabilise training.
- Numerical variables were scaled so that variables with larger units did not dominate the model unfairly.

### 7. Exploratory Data Analysis

Exploratory Data Analysis was used to understand the dataset before model training.

The EDA included:

- Wind speed by basin.
- Sea surface temperature distribution.
- Central pressure distribution.
- Wind speed distribution.
- Geographical distribution of cyclone tracks.
- Model comparison charts.

The EDA showed that:

- Central pressure was strongly linked with storm intensity.
- Sea surface temperature values were within realistic cyclone-supporting ranges.
- Wind speed was imbalanced, with weaker storms being more common than extreme storms.
- Cyclone tracks were distributed across recognised cyclone basins.
- Basin and spatial information were useful contextual features.

---

## 🧪 Hypothesis Testing

This project included statistical hypothesis testing to connect the machine learning work with meteorological theory.

Two correlation methods were used:

- **Pearson correlation**: used to measure linear relationships.
- **Spearman correlation**: used to measure monotonic relationships, even when the relationship is not perfectly linear.

---

## ⏱️ Hypothesis 1: Storm Duration vs Maximum Wind Speed

### Hypothesis

**Null hypothesis:** There is no statistically significant correlation between cyclone duration and maximum wind speed.

**Alternative hypothesis:** Longer cyclone duration is positively associated with higher maximum wind speed.

### Why this hypothesis was tested

This hypothesis is based on cyclone lifecycle theory. A longer-lasting cyclone has more time to interact with favourable conditions such as warm sea surface temperature, moisture and lower wind shear. This can allow the storm to organise and intensify.

### Result

| Test | Result |
|---|---:|
| Pearson correlation | r = 0.51, p < 0.001 |
| Spearman correlation | ρ = 0.62, p < 0.001 |
| Final decision | Accepted |

### Interpretation

The result showed a moderate to strong positive relationship. Longer-lasting storms generally reached higher maximum wind speeds. However, storm duration was not the strongest predictor because cyclone intensity is also affected by pressure, SST, wind shear and other atmospheric conditions.

---

## 📍 Hypothesis 2: Latitude vs Maximum Wind Speed

### Hypothesis

**Null hypothesis:** Cyclone latitude has no statistically significant relationship with maximum wind speed.

**Alternative hypothesis:** Cyclone latitude is significantly associated with maximum wind speed.

### Why this hypothesis was tested

Latitude was tested because cyclones require sufficient Coriolis force to form, and this is linked to distance from the equator. However, the project tested whether latitude remains important for predicting maximum wind speed after the cyclone has already formed.

### Result

| Test | Result |
|---|---:|
| Pearson correlation | r = -0.10, p = 0.157 |
| Spearman correlation | ρ = -0.10, p = 0.139 |
| Final decision | Not supported |

### Interpretation

Latitude had a weak and statistically insignificant relationship with maximum wind speed. This suggests that latitude is more important for cyclone formation than for predicting final cyclone intensity in this dataset.

---

## 📉 Hypothesis 3: Minimum Central Pressure vs Maximum Wind Speed

### Hypothesis

**Null hypothesis:** Minimum central pressure has no statistically significant correlation with maximum wind speed.

**Alternative hypothesis:** Lower central pressure is associated with higher maximum wind speed.

### Why this hypothesis was tested

This hypothesis is based on the pressure-wind relationship in meteorology. A lower central pressure usually creates a stronger pressure gradient, which leads to stronger winds around the cyclone centre.

### Result

| Test | Result |
|---|---:|
| Pearson correlation | r = -0.97, p < 0.001 |
| Spearman correlation | ρ = -0.96, p < 0.001 |
| Final decision | Strongly accepted |

### Interpretation

This was the strongest relationship in the project. Lower central pressure was strongly associated with higher maximum wind speed. This confirmed that minimum central pressure was the most important predictor of cyclone intensity in the dataset.

---

## ✅ Summary of Hypothesis Findings

| Hypothesis | Predictor | Relationship Tested | Result | Meaning |
|---|---|---|---|---|
| H1 | Storm duration | Longer duration → higher wind speed | Accepted | Duration is a useful secondary predictor. |
| H2 | Latitude | Latitude → wind speed | Not supported | Latitude was weak for predicting final intensity. |
| H3 | Minimum central pressure | Lower pressure → higher wind speed | Strongly accepted | Central pressure was the strongest predictor. |

Overall, the hypotheses showed that:

1. **Minimum central pressure** was the most reliable predictor.
2. **Storm duration** was useful but less powerful than pressure.
3. **Latitude** was not very useful for predicting maximum wind speed after cyclone formation.

---

## 🤖 Machine Learning Models Used

Six model types were tested:

1. Random Forest
2. XGBoost
3. LightGBM
4. Support Vector Regression
5. Long Short-Term Memory Network
6. Temporal Convolutional Network

The target variable was **maximum wind speed**.

The models were evaluated using:

- **RMSE**: Root Mean Squared Error
- **MAE**: Mean Absolute Error
- **R²**: Coefficient of Determination

Lower RMSE and MAE values indicate better performance. Higher R² values indicate that the model explains more variance in the target variable.

---

## 📊 Model Results

| Model | RMSE | MAE | R² | Performance Summary |
|---|---:|---:|---:|---|
| LightGBM | 7.72 | 5.23 | 0.925 | Best-performing model overall. |
| XGBoost | 8.45 | 5.64 | 0.910 | Strong second-best model. |
| Random Forest | 9.84 | 6.36 | 0.878 | Reliable baseline model. |
| SVR | 12.78 | 7.71 | 0.794 | Captured some non-linear patterns but weaker than tree ensembles. |
| LSTM | 15.83 | 11.02 | 0.673 | Underperformed due to limited sequence data and dataset size. |
| TCN Run 1 | 20.34 | 13.38 | 0.461 | Weakest performance. |
| TCN Run 2 | 18.75 | 12.77 | 0.542 | Slightly improved but still weaker than classical ML models. |

---

## 🏆 Best Model: LightGBM

**LightGBM** was the best-performing model.

It achieved:

- **RMSE:** 7.72
- **MAE:** 5.23
- **R²:** 0.925

This means the model explained approximately **92.5% of the variance** in maximum wind speed.

### Why LightGBM performed best

LightGBM performed well because the dataset was mainly structured and tabular. Tree-based boosting models are very strong for this type of data because they can:

- Capture non-linear relationships.
- Handle feature interactions.
- Focus on difficult prediction errors.
- Work well with smaller or medium-sized datasets.
- Use important predictors such as central pressure effectively.

In this project, the strongest signal came from **minimum central pressure**, and LightGBM was able to use this relationship very effectively.

---

## 🌳 Why Classical Machine Learning Performed Better Than Deep Learning

A key finding of the project was that classical machine learning models performed better than deep learning models.

The overall ranking was:

1. LightGBM
2. XGBoost
3. Random Forest
4. SVR
5. LSTM
6. TCN

### Main reasons

#### 1. The data was structured and tabular

The dataset mainly contained tabular features such as pressure, wind speed, latitude, longitude, SST and duration. Tree-based models are usually very strong for structured tabular datasets.

#### 2. The dataset was not large enough for deep learning

Deep learning models usually require much larger datasets. The LSTM and TCN models needed more long-term sequence data to learn storm evolution properly.

#### 3. The strongest predictor was static

Minimum central pressure was the strongest predictor. This is a structural feature, not a complex image or long sequence. Tree-based models handled this better than deep learning models.

#### 4. Deep learning needed more tuning

LSTM and TCN models are sensitive to sequence length, number of layers, kernel size, dilation rate, learning rate and training epochs. With limited computing resources, deep learning performance was harder to optimise.

#### 5. Boosting models were more sample-efficient

LightGBM and XGBoost learned useful patterns from the available dataset more efficiently than the deep learning models.

---

## 🔍 Model-by-Model Explanation

### Random Forest

Random Forest worked as a strong baseline model. It handled non-linear relationships and feature interactions reasonably well. However, it was not as accurate as boosting models because it averages many decision trees rather than correcting errors step by step.

### XGBoost

XGBoost performed very well. It improved on Random Forest by using gradient boosting, which allows the model to focus more on difficult prediction cases. It was especially useful for handling interactions between variables such as pressure, duration and wind speed.

### LightGBM

LightGBM was the best model. It was fast, accurate and effective for structured meteorological data. Its leaf-wise tree growth helped it capture complex relationships more efficiently than the other models.

### Support Vector Regression

SVR captured some non-linear patterns but did not perform as well as the tree-based ensemble models. It struggled more with the size, noise and complexity of the cyclone dataset.

### LSTM

LSTM was included because cyclone development is a time-dependent process. However, it underperformed because the dataset did not provide enough long sequential information for the model to fully benefit from its architecture.

### TCN

TCN was tested as another sequence-based deep learning approach. It performed worse than the classical ML models. The likely reasons were limited training data, sensitivity to hyperparameters and the need for richer spatiotemporal inputs.

---

## 📌 Key Findings

The main findings of the project were:

1. **LightGBM was the best-performing model**, achieving the lowest prediction error and highest R² score.
2. **XGBoost also performed strongly**, confirming that boosting methods are effective for cyclone intensity prediction.
3. **Classical machine learning models outperformed deep learning models** on this structured dataset.
4. **Minimum central pressure was the strongest predictor** of maximum wind speed.
5. **Storm duration was a useful secondary predictor** because longer storms had more opportunity to intensify.
6. **Latitude was not a strong predictor** of maximum wind speed after cyclone formation.
7. **Deep learning models require larger and richer time-series datasets** to perform well in this type of problem.
8. **The project supports the use of machine learning as a complementary tool** for cyclone intensity analysis.

---

## 🌍 Practical Value of the Project

This project has practical value because cyclone intensity prediction is important for disaster preparedness, emergency planning and climate resilience.

The project shows that machine learning can help identify useful patterns in cyclone data, especially when working with variables such as:

- Minimum central pressure
- Maximum wind speed
- Storm duration
- Sea surface temperature
- Basin and spatial location
- Wind components

The results suggest that tree-based machine learning models could be useful for supporting cyclone intensity analysis when structured meteorological data is available.

---

## ⚠️ Limitations

The project had several limitations:

1. **Limited time period**  
   The modelling dataset was restricted to a manageable period due to computational constraints.

2. **Limited feature set**  
   Important variables such as ocean heat content, vertical wind shear, relative humidity and upper-level outflow were not fully included.

3. **Deep learning underperformance**  
   LSTM and TCN models did not perform as well because the dataset was not large enough and did not contain sufficiently rich sequential inputs.

4. **Correlation does not prove causation**  
   The hypothesis tests identified relationships between variables, but they do not prove direct causality.

5. **Operational forecasting requires more validation**  
   The model would need testing on larger multi-year datasets before being considered useful in real operational settings.

---

## 🚀 Future Improvements

Future versions of this project could be improved by:

- Extending the dataset across multiple decades.
- Adding vertical wind shear, humidity and ocean heat content.
- Including satellite imagery or gridded storm fields.
- Testing Transformer-based models.
- Developing hybrid models combining LightGBM with deep learning.
- Adding SHAP or LIME for better model interpretability.
- Evaluating rapid intensification cases separately.
- Testing the model across different ocean basins.
- Adding a small interactive dashboard or Streamlit demo.

---

## ▶️ How to Run the Project

The project can be explored in two ways.

### Option 1: Run the main Python script

```bash
python cyclone_forecasting_ml.py
```

### Option 2: Open the notebook

Open the notebook below in Jupyter Notebook or Google Colab:

```text
project_files/notebooks/CST4090_Dissertation.ipynb
```

Make sure the dataset paths match the folder structure shown in this README.

---

## 🧾 Expected Outputs

Depending on the script or notebook section being run, the project can produce:

- Cleaned and merged datasets.
- EDA charts.
- Hypothesis testing results.
- Model performance tables.
- RMSE, MAE and R² comparisons.
- Model ranking summary.
- Visual outputs for project demonstration.

---


## 🧠 Main Skills Demonstrated

This project demonstrates skills in:

- Data cleaning and preprocessing
- Working with CSV and NetCDF files
- Meteorological data handling
- Feature engineering
- Exploratory Data Analysis
- Statistical hypothesis testing
- Machine learning regression
- Deep learning experimentation
- Model evaluation using RMSE, MAE and R²
- Technical interpretation of model results
- Structuring a data science project for GitHub

---

## 📚 Supporting Documents

The folder `project_files/reports/` contains the full dissertation report, e-poster and project proposal. These files provide academic background and detailed explanation, while this README presents the project in a more concise and practical GitHub format.

---

## ✅ Final Conclusion

This project found that **classical machine learning models**, especially **LightGBM** and **XGBoost**, performed better than deep learning models for cyclone intensity prediction using this structured dataset.

The most important predictor was **minimum central pressure**, which had a very strong inverse relationship with maximum wind speed. Storm duration was also useful, while latitude was not a strong predictor of final intensity.

Overall, the project shows that machine learning can provide useful support for cyclone intensity analysis, especially when strong meteorological predictors are properly cleaned, engineered and evaluated.
