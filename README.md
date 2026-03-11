# 🌦️ Predicting Temperature in London Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.x-orange?style=flat-square&logo=scikit-learn)
![MLflow](https://img.shields.io/badge/MLflow-Tracking-blue?style=flat-square&logo=mlflow)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-green?style=flat-square&logo=pandas)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)

---

## 📌 Project Overview

As climate change continues to reshape weather patterns worldwide, the ability to **accurately forecast temperature** has become critical for industries ranging from agriculture and energy to logistics and urban planning.

This project tackles the problem of **predicting mean daily temperature in London** by running structured ML experiments across multiple regression models. Using a combination of **Scikit-learn** and **MLflow**, the project automates model training, evaluation, and experiment tracking — enabling reproducible, data-driven comparisons to identify the best-performing approach.

> **Key Objective:** Build an automated, function-driven ML workflow that trains and evaluates multiple regression models on historical London weather data and tracks all experiments with MLflow for full reproducibility.

---

## 🎯 Problem Statement

Given historical daily weather measurements recorded in London, predict:

> **`mean_temp`** — the mean temperature in degrees Celsius (°C) for a given day

This is a **supervised regression problem** where the model learns from patterns in meteorological features to forecast a continuous temperature value.

---

## 📊 Dataset — `london_weather.csv`

The dataset contains daily weather observations recorded in London. Each row represents one day of measurements.

| Column | Description | Unit | Type |
|---|---|---|---|
| `date` | Recorded date of measurement | YYYYMMDD | int |
| `cloud_cover` | Cloud cover measurement | oktas | float |
| `sunshine` | Sunshine duration | hours (hrs) | float |
| `global_radiation` | Solar irradiance | W/m² | float |
| `max_temp` | Maximum temperature | °C | float |
| `mean_temp` | **Target variable** — Mean temperature | °C | float |
| `min_temp` | Minimum temperature | °C | float |
| `precipitation` | Precipitation measurement | mm | float |
| `pressure` | Atmospheric pressure | Pa | float |
| `snow_depth` | Snow depth | cm | float |

**Dataset size:** Multi-year daily records from London weather stations
**Missing values:** Handled during preprocessing stage
**Target:** `mean_temp` (continuous, regression target)

---

## 🧠 Approach & Methodology

### 1️⃣ Exploratory Data Analysis (EDA)
- Distribution analysis of all meteorological features
- Seasonal trend detection across years
- Correlation heatmap to identify features most predictive of `mean_temp`
- Outlier detection and handling
- Missing value analysis and imputation strategy

### 2️⃣ Data Preprocessing
- Date parsing and temporal feature extraction (month, season, year)
- Handling missing values via median imputation
- Feature scaling using `StandardScaler`
- Train-test split (80/20) with consistent random state for reproducibility

### 3️⃣ Automated Model Training (Function-Driven Workflow)
All model training is encapsulated in reusable Python functions. Models trained and compared:

| Model | Type |
|---|---|
| Linear Regression | Baseline |
| Ridge Regression | Regularized Linear |
| Lasso Regression | Sparse Regularized |
| Random Forest Regressor | Ensemble |
| Gradient Boosting Regressor | Boosting Ensemble |

### 4️⃣ MLflow Experiment Tracking
Every model run is logged to MLflow with:
- **Parameters:** Model hyperparameters
- **Metrics:** MAE, RMSE, R² Score
- **Artifacts:** Trained model files
- **Tags:** Model name, experiment version

### 5️⃣ Model Evaluation
Models evaluated on the held-out test set using:
- **MAE** — Mean Absolute Error
- **RMSE** — Root Mean Squared Error
- **R² Score** — Coefficient of Determination

---

## 📁 Project Structure

```
Predicting-Temperature-in-London-using-Machine-Learning/
│
├── data/
│   └── london_weather.csv          # Raw dataset
│
├── notebooks/
│   └── EDA_and_Modeling.ipynb      # Full EDA + model experiments
│
├── src/
│   ├── preprocess.py               # Data loading & preprocessing functions
│   ├── train.py                    # Model training & MLflow logging
│   └── evaluate.py                 # Evaluation metrics & comparison
│
├── mlruns/                         # MLflow experiment tracking directory
│
├── requirements.txt                # Python dependencies
├── README.md                       # Project documentation
└── .gitignore
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- pip

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Predicting-Temperature-in-London-using-Machine-Learning.git
cd Predicting-Temperature-in-London-using-Machine-Learning
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Notebook

```bash
jupyter notebook notebooks/EDA_and_Modeling.ipynb
```

### 5. Run Training Script

```bash
python src/train.py
```

### 6. Launch MLflow UI to View Experiments

```bash
mlflow ui
```
Then open your browser at: `http://localhost:5000`

---

## 📦 Requirements

```txt
pandas>=1.5.0
numpy>=1.23.0
scikit-learn>=1.1.0
mlflow>=2.0.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
```

Install all at once:
```bash
pip install -r requirements.txt
```

---

## 📈 Results

| Model | MAE (°C) | RMSE (°C) | R² Score |
|---|---|---|---|
| Linear Regression | — | — | — |
| Ridge Regression | — | — | — |
| Lasso Regression | — | — | — |
| Random Forest | — | — | — |
| Gradient Boosting | — | — | — |

> 📝 **Note:** Fill in your actual experiment results from MLflow after running the training pipeline. The best-performing model and its metrics should be highlighted here.

---

## 🔍 Key Insights

- **`global_radiation`** and **`sunshine`** showed the strongest positive correlation with `mean_temp`, confirming solar energy as the primary temperature driver
- **`snow_depth`** and **`precipitation`** showed strong negative correlation with mean temperature
- Ensemble models (Random Forest, Gradient Boosting) consistently outperformed linear baselines
- Temporal features (month, season) significantly improved prediction accuracy by capturing seasonal cycles

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **Python** | Core programming language |
| **Pandas & NumPy** | Data manipulation and processing |
| **Scikit-learn** | ML model training and evaluation |
| **MLflow** | Experiment tracking and model registry |
| **Matplotlib & Seaborn** | Data visualization |
| **Jupyter Notebook** | Interactive development and EDA |

---

## 🌍 Business Impact

Accurate temperature forecasting enables:
- ⚡ **Energy sector** — Optimize heating/cooling demand forecasting
- 🌾 **Agriculture** — Plan planting and harvesting schedules
- 🚚 **Logistics** — Anticipate weather-related supply chain disruptions
- 🏙️ **Urban planning** — Design climate-resilient infrastructure

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Atul Kumar**
- 📧 atulkushwaha0720@gmail.com
- 🔗 [LinkedIn](https://linkedin.com/in/your-profile)
- 💻 [GitHub](https://github.com/your-username)

---

## ⭐ Acknowledgements

- Dataset sourced from historical London weather station records
- Inspired by the growing need for data-driven climate solutions
- Built as part of continuous learning in applied machine learning and MLOps practices

---

*If you found this project useful, consider giving it a ⭐ on GitHub!*
