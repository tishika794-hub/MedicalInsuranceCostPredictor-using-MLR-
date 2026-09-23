# Medical Insurance Cost Predictor using Multiple Linear Regression (MLR)

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Dataset](https://img.shields.io/badge/Kaggle-Dataset-20BEFF.svg)](https://www.kaggle.com/datasets/mirichoi0218/insurance)
[![Framework](https://img.shields.io/badge/scikit--learn-MLR-orange.svg)](https://scikit-learn.org/)

---

## 📌 Project Overview
The **Medical Insurance Cost Predictor** is an end-to-end Machine Learning project developed to forecast individual healthcare insurance expenditures based on demographic and physiological indicators (such as age, BMI, smoking status, number of children, and geographic region).

Utilizing **Multiple Linear Regression (MLR)** with Ordinary Least Squares (OLS) optimization, this project quantifies the marginal cost impact of lifestyle choices and personal characteristics on medical bills, providing valuable actuarial insights for insurance pricing and risk assessment.

---

## 📊 Dataset Information
- **Dataset Name:** Medical Cost Personal Datasets
- **Source:** Kaggle ([`mirichoi0218/insurance`](https://www.kaggle.com/datasets/mirichoi0218/insurance))
- **Total Records:** 1,338 observations (0 missing values)
- **Target Variable:** `charges` (Annual medical costs billed by health insurance)

### Feature Dictionary
| Feature | Type | Description | Values / Range |
| :--- | :--- | :--- | :--- |
| `age` | Integer | Age of primary beneficiary | 18 – 64 years |
| `sex` | Categorical | Insurance contractor gender | `male` (0), `female` (1) |
| `bmi` | Float | Body mass index ($kg/m^2$) | 15.96 – 53.13 |
| `children` | Integer | Number of children/dependents | 0 – 5 |
| `smoker` | Categorical | Smoking status | `yes` (1), `no` (0) |
| `region` | Categorical | US residential area | `northeast`, `northwest`, `southeast`, `southwest` |
| **`charges`** | Float | **Target: Individual medical charges** | **$1,121.87 – $63,770.43** |

---

## 🚀 Key Results & Model Performance
The Multiple Linear Regression model was fitted on an 80/20 train/test split:

- **Coefficient of Determination ($R^2$ - Test):** **`0.7836` (~78.4% variance explained)**
- **Root Mean Squared Error (RMSE):** **`$5,796.28`**
- **Mean Absolute Error (MAE):** **`$4,181.19`**
- **Train $R^2$:** **`0.7417`** (demonstrates solid generalization without overfitting)

### Actuarial Insights (Feature Impact)
1. **Smoking Status ($\beta_{smoker} \approx +\$23,651$):** The primary driver of healthcare costs. Smokers incur over \$23,600+ in extra annual medical charges.
2. **Body Mass Index ($\beta_{bmi} \approx +\$337$):** Every unit increase in BMI adds ~\$337 to annual charges, with compounding spikes for obese smokers ($BMI \ge 30$).
3. **Age ($\beta_{age} \approx +\$257$):** Medical costs increase predictably by ~\$257 per year of life.

---

## 📁 Repository & Project Deliverables

```
.
├── Ishika_MedicalInsuranceCostPredictor.ipynb  # Complete Jupyter Notebook (EDA, Preprocessing, MLR Model, Evaluation, Inferences)
├── Ishika_ProjectReport.docx                   # Comprehensive Project Report in Microsoft Word (.docx) format
├── requirements.txt                            # Project dependencies and Python libraries
├── README.md                                   # Project documentation and setup guide
├── insurance.csv                               # Raw dataset (1,338 records)
└── insurance_cleaned.csv                       # Preprocessed and encoded dataset
```

---

## 🛠️ Technologies Used
- **Programming Language:** Python 3.9+
- **Data Manipulation & Analysis:** `pandas`, `numpy`
- **Machine Learning:** `scikit-learn`
- **Data Visualization:** `matplotlib`, `seaborn`
- **Documentation & Reporting:** `python-docx`, Jupyter Notebook

---

## ⚙️ Setup & Installation Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/tishika794-hub/MedicalInsuranceCostPredictor-using-MLR-.git
cd MedicalInsuranceCostPredictor-using-MLR-
```

### 2. Create and Activate a Virtual Environment (Optional but Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

---

## ▶️ How to Run the Project

### Running the Complete Jupyter Notebook
Launch Jupyter Notebook or Jupyter Lab:
```bash
jupyter notebook Ishika_MedicalInsuranceCostPredictor.ipynb
```
Execute the cells sequentially to observe:
1. **Dataset Loading & Statistical Audit**
2. **Exploratory Visualizations** (Distributions, Violin plots, Scatter plots with hue)
3. **Data Encoding & Preprocessing** (saving `insurance_cleaned.csv`)
4. **Model Training & Coefficient Analysis**
5. **Model Evaluation & Residual Diagnostics**
6. **Live Cost Prediction Tool (`predict_insurance_cost`)**

---

## 🔮 Sample Prediction Tool
The notebook includes an interactive inference helper:

```python
# Sample Usage
predicted_cost = predict_insurance_cost(
    age=45, 
    sex='male', 
    bmi=33.2, 
    children=2, 
    smoker='yes', 
    region='southeast'
)
print(f"Estimated Insurance Charges: ${predicted_cost:,.2f}")
# Output: Estimated Insurance Charges: $34,484.58
```

---

## 👤 Author
- **Author:** Ishika
- **GitHub:** [@tishika794-hub](https://github.com/tishika794-hub)

---

## 📜 License
This project is open-source and available under the [MIT License](LICENSE).
