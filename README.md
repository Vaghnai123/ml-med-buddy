# ml-med-buddy

This repository contains the code for **MedBuddy.ML**, a Machine Learning project developed for **Heart Disease Prediction**.

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

## 🐍 Create Virtual Environment

Create a Python virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

## 📦 Install Dependencies

Install all required Python packages:

```bash
pip install -r requirements.txt
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

## 🖥️ Run the Streamlit Frontend

Open another terminal and activate the virtual environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

Then run:

```bash
streamlit run Frontend/app.py
```

The application will open in your browser, usually at:

```text
http://localhost:8501
```

## 🔗 API Endpoint

The heart disease prediction API endpoint is:

```text
POST /predict-heart-disease
```

Example local URL:

```text
http://127.0.0.1:8000/predict-heart-disease
```

The API accepts patient information and returns:

- Prediction
- Probability
- Diagnosis

## 🌐 Deployment

### Backend

The FastAPI backend is deployed using Render.

```text
https://ml-med-buddy.onrender.com
```

Health check:

```text
https://ml-med-buddy.onrender.com/health
```

### Frontend

The Streamlit frontend is deployed using Streamlit Cloud.

The Streamlit Cloud application uses the Render API URL through the `API_URL` secret.
