# 🏠 House Price Prediction — Ames Housing Dataset

A machine learning regression project that predicts house sale prices using the Ames Housing dataset.

## 📌 Project Overview

The goal of this project is to predict the sale price of houses in Ames, Iowa, based on 79+ features describing each property (size, quality, location, year built, etc.). This is a **supervised regression** problem.

## 📊 Dataset

- **Source:** [Ames Housing Dataset](http://jse.amstat.org/v19n3/decock/AmesHousing.txt) (Dean De Cock, 2011)
- **Size:** 2,930 rows × 82 columns
- **Target variable:** `SalePrice`

## 🛠️ Tools & Libraries

- Python
- Pandas, NumPy — data manipulation
- Scikit-learn — model building, evaluation, hyperparameter tuning
- Matplotlib, Seaborn — data visualization

## 🔄 Project Workflow

1. **Data Loading** — Loaded the dataset directly from source into a pandas DataFrame.
2. **Exploratory Data Analysis (EDA)** — Explored data types, distributions, and missing values.
3. **Data Cleaning**
   - Dropped columns with >40% missing values (e.g., Pool QC, Alley, Fence).
   - Filled categorical missing values with `'None'` where NaN meant "feature absent."
   - Filled numeric missing values with the column median.
4. **Feature Encoding** — Applied one-hot encoding (`pd.get_dummies`) to convert 37 categorical columns into numeric format.
5. **Train/Test Split** — Split data into 80% training and 20% testing sets.
6. **Model Training** — Trained and compared two models:
   - Linear Regression (baseline)
   - Random Forest Regressor
7. **Hyperparameter Tuning** — Used `GridSearchCV` with 3-fold cross-validation to find optimal Random Forest parameters.
8. **Model Evaluation** — Evaluated using MAE, RMSE, and R² score.
9. **Feature Importance Analysis** — Identified which features most influence house prices.

## 📈 Results

| Model | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Linear Regression | $16,302.94 | $29,146.00 | 0.8940 |
| Random Forest (default) | $15,806.29 | $26,457.73 | 0.9127 |
| Random Forest (tuned) | $15,742.85 | $26,806.20 | 0.9104 |

**Best model:** Random Forest Regressor, explaining ~91% of the variance in house prices.

## 🔑 Key Insight — Feature Importance

The top factors driving house price were:

1. **Overall Quality** (60.6%) — by far the strongest predictor
2. **Ground Living Area** (10.2%) — total above-ground living space
3. **1st Floor SF, Total Basement SF, 2nd Floor SF** — overall size-related features
4. **Full Bath, Garage Area/Cars** — convenience features

**Takeaway:** Overall build quality and living space are the two biggest levers affecting a home's sale price — far more impactful than lot size or age.

## 🚀 How to Run

1. Open `ames_housing_price_prediction.ipynb` in Google Colab or Jupyter Notebook.
2. Run all cells in order — the dataset loads automatically from the source URL.
3. No API keys or local files required.

## 📁 Repository Structure

```
├── ames_housing_price_prediction.ipynb   # Main notebook with full analysis
├── README.md                              # Project documentation
└── requirements.txt                       # Python dependencies
```

## 👤 Author

Built as part of a Machine Learning project.
