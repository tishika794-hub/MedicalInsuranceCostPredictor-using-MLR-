# Medical Insurance Cost Prediction

This project explores the relationship between various physiological and demographic factors and medical insurance costs. It leverages a dataset downloaded from Kaggle to clean the raw data and build a Multiple Linear Regression model for predicting charges.

## Contents
- `insurance.csv`: The raw dataset originally sourced from the Kaggle dataset (`mirichoi0218/insurance`).
- `data_cleaning.ipynb`: A Jupyter Notebook that loads the raw dataset, checks for missing data, and encodes all independent categorical variables (like sex, smoker, and region) into a numerical format suitable for machine learning algorithms. 
- `insurance_cleaned.csv`: The materialized, preprocessed output of `data_cleaning.ipynb` where regions are one-hot encoded and binary variables are zero/one mapped.
- `model_prediction.ipynb`: A Jupyter Notebook housing the Multiple Linear Regression model. It reads the cleaned dataset, splits it into an 80/20 train/test split, calculates the model's coefficients, and performs validations computing Mean Squared Error, Root Mean Squared Error, and the R-squared score.

## Model Summary
A scikit-learn Multiple Linear Regression model was built for this dataset, incorporating all variables available (age, sex, bmi, children, smoker, and regions). 
- **R-squared (Accuracy):** ~0.784
- **Root Mean Squared Error (RMSE):** ~5796

The model concludes that `smoker` explicitly correlates heavily with medical cost along with age and BMI.

## Running the Project Locally
Ensure you have Python 3 installed alongside `pandas`, `numpy`, `scikit-learn`, `matplotlib`, and `seaborn`.

1. Run the `data_cleaning.ipynb` notebook to see the preprocessing rules.
2. Run the `model_prediction.ipynb` notebook to see the feature splits, model fitting, and performance testing.
