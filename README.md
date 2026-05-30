# 🫀 Heart Disease Prediction App

A machine learning-powered web application that predicts the likelihood of heart disease based on 13 clinical parameters. Built with **Python**, **Scikit-learn**, and **Streamlit**.

---

## 📌 Overview

Heart disease is one of the leading causes of mortality worldwide. This project leverages supervised machine learning — specifically a **Random Forest Classifier** — to provide an accessible, real-time heart disease risk assessment tool. Users enter clinical data through an intuitive web form and receive an instant prediction.

---

## ✨ Features

- 🩺 Predict heart disease risk from 13 clinical inputs
- ⚡ Real-time prediction via interactive Streamlit web app
- 🎨 Color-coded output (green = low risk, red = high risk)
- 📊 Trained on the UCI Heart Disease Dataset (Cleveland Clinic)
- 🤖 Random Forest Classifier (200 estimators) — outperforms Logistic Regression baseline
- 💾 Model serialized with `pickle` for fast loading

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Python 3.10+ |
| ML Library | Scikit-learn |
| Web Framework | Streamlit |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Model Serialization | Pickle |
| Development | Jupyter Notebook / Google Colab |

---

## 📁 Project Structure

```
heart-disease-prediction/
│
├── app.py                    # Streamlit web application
├── heart_disease.ipynb       # Jupyter notebook (EDA + model training)
├── heart-disease-model.pkl   # Trained Random Forest model + scaler
├── heart - heart.csv         # UCI Heart Disease Dataset
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

---

## 🔬 Dataset

**Source:** UCI Heart Disease Dataset – Cleveland Clinic Foundation  
**Records:** 303 patients (302 after duplicate removal)  
**Features:** 13 clinical attributes + 1 target variable

| Feature | Description |
|---------|-------------|
| Age | Patient age in years |
| Gender | 1 = Male, 0 = Female |
| ChestPainType | 0 = Typical Angina, 1 = Atypical, 2 = Non-Anginal, 3 = Asymptomatic |
| RestingBp | Resting blood pressure (mm Hg) |
| Cholesterol | Serum cholesterol (mg/dL) |
| FastingBS | Fasting blood sugar > 120 mg/dL (1 = True) |
| RestingECG | Resting ECG results (0–2) |
| MaxHR | Maximum heart rate achieved |
| ExerciseAngina | Exercise-induced angina (1 = Yes) |
| ST_Depression | ST depression induced by exercise |
| ST_Slope | Slope of peak exercise ST segment (0–2) |
| MajorVessels | Number of major vessels (0–3) |
| Thalassemia | 1 = Normal, 2 = Fixed Defect, 3 = Reversible Defect |
| **HeartDisease** | **Target: 1 = Disease, 0 = No Disease** |

---

## 🔄 ML Pipeline

```
Raw Data
   ↓
Data Cleaning (remove duplicates, cap outliers via IQR)
   ↓
Feature Engineering (rename columns, one-hot encode categoricals)
   ↓
Standard Scaling (numerical features)
   ↓
Train / Test Split (80% / 20%, stratified)
   ↓
Model Training (Logistic Regression vs Random Forest)
   ↓
Model Evaluation (accuracy, confusion matrix, classification report)
   ↓
Model Serialization (pickle → heart-disease-model.pkl)
   ↓
Streamlit Deployment
```

---

## 📈 Model Performance

| Model | Accuracy |
|-------|----------|
| Logistic Regression | ~83–85% |
| **Random Forest (n=200)** | **~86–88%** ✅ Selected |

The Random Forest Classifier was selected for its lower false-negative rate — critical in clinical applications where missing a disease is more harmful than a false alarm.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10 or higher
- pip

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/heart-disease-prediction.git
cd heart-disease-prediction

# Install dependencies
pip install -r requirements.txt
```

### Run the App

```bash
streamlit run app.py
```

The application will open in your browser at `http://localhost:8501`.

---

## 📦 requirements.txt

```
streamlit
pandas
numpy
scikit-learn
```

---

## 🖥️ App Preview

> Enter patient data → Click **"Predict Heart Disease Risk"** → Get instant result

- ✅ **No Disease Detected** → Green success message  
- ⚠️ **High Risk Detected** → Red warning with cardiologist recommendation

---

## ⚠️ Disclaimer

This application is developed for **educational and research purposes only**. It is **not** a substitute for professional medical diagnosis. Always consult a qualified healthcare provider for medical advice.

---

## 🔮 Future Scope

- [ ] Expand dataset (incorporate additional UCI sub-datasets)
- [ ] Add SHAP explainability for feature importance visualization
- [ ] Explore XGBoost / LightGBM / MLP models
- [ ] Deploy on Streamlit Community Cloud / AWS
- [ ] Add BMI, smoking history, and inflammatory markers as features

---

## 📚 References

- Detrano et al. (1989) – Original Cleveland Heart Disease Dataset
- Mohan et al. (2019) – Effective Heart Disease Prediction Using Hybrid ML
- Scikit-learn: https://scikit-learn.org
- Streamlit: https://streamlit.io
- UCI Repository: https://archive.ics.uci.edu/ml/datasets/Heart+Disease

---

## 👤 Author

**Vaibhav S Pandey**
