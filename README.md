# ml-med-buddy

MedBuddy.ML is a Machine Learning based web application designed to predict the risk of heart disease from a patient's clinical information.

# Problem Statement

Heart disease is one of the major health problems that requires timely identification and proper medical evaluation. Identifying the possibility of heart disease from multiple patient health parameters can be difficult and time-consuming when performed manually.

The main problem addressed by this project is to develop a Machine Learning based system that can analyze a patient's clinical information and predict whether the patient is likely to have heart disease.

Traditional approaches may require expert analysis of multiple health parameters such as age, blood pressure, cholesterol, chest pain type, maximum heart rate, exercise-induced angina, and other clinical measurements. Therefore, there is a need for a simple computational system that can process these parameters and provide a quick preliminary prediction.

The **MedBuddy.ML** project addresses this problem by training a Machine Learning classification model on a Heart Disease dataset. The selected Random Forest model analyzes the patient's input features and predicts one of two classes: **heart disease detected** or **no heart disease detected**.

The trained model is integrated with a **FastAPI backend** and a **Streamlit frontend**, allowing users to enter patient information through a web interface and receive the model's prediction and probability score.

The system is intended as a **Machine Learning-based prediction and educational support tool**, not as a replacement for professional medical diagnosis.


# Dataset Description

The project uses the `heart.csv` dataset.

The dataset contains **1,025 records and 14 columns**. The 13 feature columns are used as input variables and `target` is used as the output variable.

## Dataset Features

| Feature | Description | Type |
|---|---|---|
| `age` | Age of the patient in years | Numerical |
| `sex` | Sex of the patient, where 1 represents male and 0 represents female | Categorical |
| `cp` | Chest pain type | Categorical |
| `trestbps` | Resting blood pressure in mm Hg | Numerical |
| `chol` | Serum cholesterol level in mg/dl | Numerical |
| `fbs` | Whether fasting blood sugar is greater than 120 mg/dl | Categorical |
| `restecg` | Resting electrocardiographic result | Categorical |
| `thalach` | Maximum heart rate achieved | Numerical |
| `exang` | Exercise-induced angina | Categorical |
| `oldpeak` | ST depression induced by exercise | Numerical |
| `slope` | Slope of the peak exercise ST segment | Categorical |
| `ca` | Number of major vessels colored by fluoroscopy | Numerical |
| `thal` | Thalassemia status | Categorical |
| `target` | Heart disease presence | Target |

The categorical features in the supplied dataset are already encoded numerically, so an additional categorical encoding step is not required.

## Target Variable

The `target` column represents the prediction class:

- `0` → No heart disease
- `1` → Heart disease
---


## 🚀 Features

- Heart disease prediction using Machine Learning
- Random Forest Classification model
- FastAPI backend for prediction API
- Streamlit frontend
- Model probability prediction
- REST API integration
- Deployed backend using Render
- Streamlit Cloud frontend

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Random Forest
- FastAPI
- Pydantic
- Streamlit
- Joblib
- Requests
- python-dotenv
- Render
- Streamlit Cloud

## 📁 Project Structure

```text
ml-med-buddy/
│
├── backend/
│   ├── main.py
│   ├── predictor.py
│   └── training.py
│
├── Frontend/
│   └── app.py
│
├── dataset/
│   └── heart.csv
│
├── model_dir/
│   └── heart_disease_prediction_model.joblib
│
├── logs/
│   └── app.log
│
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

## 📥 Clone the Repository

Open PowerShell or Command Prompt and run:

```bash
git clone https://github.com/Vaghnai123/ml-med-buddy.git
```

Move into the project directory:

```bash
cd ml-med-buddy
```

## ⚙️ Environment Variables

Create a `.env` file in the project root:

```env
PROJECT_ROOT="C:/Projects/ml-med-buddy"

LOG_DIR=logs
DATASET_DIR=dataset
MODEL_DIR=model_dir

DATASET_NAME=heart.csv
LOG_NAME=app.log
MODEL_NAME=heart_disease_prediction_model.joblib

TARGET_COL=target
TEST_SIZE=0.15
RANDOM_STATE=42

API_URL=http://127.0.0.1:8000/predict-heart-disease
```

> **Important:** Do not commit your `.env` file to GitHub. Add `.env` to `.gitignore`.

## 🚀 Run the FastAPI Backend

From the project root, run:

```bash
uvicorn backend.main:app 
```

The API will be available at:

```text
http://127.0.0.1:8000
```

### Check API Health

Open:

```text
http://127.0.0.1:8000/health
```

Expected response:

```json
{
    "status": "ok"
}
```

### API Documentation

FastAPI automatically provides Swagger documentation at:

```text
http://127.0.0.1:8000/docs
```

## 🌐 Deployment

# Running the Project Locally

## Step 1: Create Virtual Environment

```bash
python -m venv .venv
```

## Step 2: Activate Virtual Environment on Windows

```powershell
.\.venv\Scripts\Activate.ps1
```

## Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

## Step 4: Train the Model

```bash
python backend/training.py
```

This creates the trained Joblib model.

## Step 5: Start FastAPI

```bash
uvicorn backend.main:app --reload
```

The API will normally be available at:

```text
http://127.0.0.1:8000
```

## Step 6: Start Streamlit

Open another terminal and run:

```bash
streamlit run frontend/app.py
```

The Streamlit application will open in the browser.

### Backend

The FastAPI backend is deployed using Render.

```text
https://ml-med-buddy.onrender.com
```

Health check:

```text
https://ml-med-buddy.onrender.com/health
```

---

