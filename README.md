# 🏡 House Price Prediction - Kaggle Competition

This project is a solution to the classic **Kaggle House Prices - Advanced Regression Techniques** competition. The objective is to predict the final sale price of homes based on various features.

## 📊 Dataset

The dataset contains 80 features describing various aspects of residential homes in Ames, Iowa. It includes both numeric and categorical data.

- **Train Data**: 1460 rows
- **Test Data**: 1459 rows

## 🔧 Workflow

### 1. Data Preprocessing
- Combined `train` and `test` datasets for uniform preprocessing.
- Dropped columns with too many missing values or low predictive power:
  - `Alley`, `PoolQC`, `Fence`, `MiscFeature`, `Utilities`, etc.
- Label encoded all categorical columns.
- Imputed missing numerical values using the **mean** strategy.

### 2. Models Used
Applied multiple regression models and compared performance using **Cross-Validated RMSE**:

| Model               | RMSE     |
|--------------------|----------|
| Linear Regression   | 0.15844  |
| Ridge Regression    | 0.15828  |
| Lasso Regression    | 0.19818  |
| Random Forest       | 0.14457  |
| **Gradient Boosting** | **0.13413** ✅ |
| XGBoost             | 0.14432  |

### 3. Best Model
✅ **GradientBoostingRegressor** performed best and was used to generate final predictions.

## 📁 Files

- `train.csv` - Training data
- `test.csv` - Test data (without target)
- `submission.csv` - Final predictions submitted to Kaggle
- `model_comparison.py` - All model training and comparison code
- `README.md` - Project overview

## 🚀 How to Run

```bash
# Install required libraries
pip install -r requirements.txt

# Run the training and evaluation script
python model_comparison.py
