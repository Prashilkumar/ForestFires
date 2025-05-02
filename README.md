
# 🔥 Algerian Forest Fires Prediction using Ridge Regression

## 📌 Project Overview

This project aims to **predict the Fire Weather Index (FWI)** — a numerical rating of fire intensity — using meteorological and weather-related attributes from two Algerian regions: **Bejaia** and **Sidi Bel-Abbes**. By leveraging Ridge Regression, the model forecasts FWI based on temperature, humidity, wind, and other fire behavior indicators.

---

## 📊 Dataset Description

The dataset comprises **244 records** collected between **June and September 2012**, with **122 records** from each region.

- **Target Variable**: `FWI` (Fire Weather Index)
- **Features**:
  1. `Date`: Date of observation (DD/MM/YYYY)
  2. `Temp`: Temperature at noon (°C)
  3. `RH`: Relative Humidity (%)
  4. `Ws`: Wind speed (km/h)
  5. `Rain`: Daily rain total (mm)
  6. `FFMC`: Fine Fuel Moisture Code
  7. `DMC`: Duff Moisture Code
  8. `DC`: Drought Code
  9. `ISI`: Initial Spread Index
  10. `BUI`: Buildup Index
  11. `FWI`: Fire Weather Index (target)

> Note: The `classes` column (fire / not fire) is used in original classification problems but **is not** the focus here — we are solving a **regression problem** to predict FWI.

---

## 🧠 Machine Learning Approach

### ✅ Steps Followed:
- **Exploratory Data Analysis (EDA)**: Uncovered feature distributions, correlations, and region-specific patterns.
- **Feature Engineering**: Transformed raw features and **removed the `Date` feature** as it was not relevant for predicting FWI.
- **Feature Selection**: Used statistical techniques and correlation analysis to retain only impactful predictors.
- **Model Training**: Employed Ridge Regression to handle multicollinearity and prevent overfitting.
- **Model Evaluation**: Assessed performance using metrics such as MAE, R² score.

---

## 🗂️ Project Structure

```bash
algerian-forest-fire/
│
├── models/
│   ├── scaler.pkl          # StandardScaler object used for input data
│   └── ridge.pkl           # Pickled Ridge Regression trained model
│
├── notebooks/
│   └── forest_fire_model.ipynb   # Full analysis, EDA, training, evaluation
│
├── templates/
│       └── index.html      # Frontend for user interactionapp/
│
├── dataset/
│   └── Algerian_forest_fires_dataset_UPDATE.csv  # Input dataset used in the project
│
│
├── application.py
├── requirements.txt        # All required libraries and versions
├── README.md               # Project documentation
└── .gitignore              # To ignore unnecessary files
```

---

## 🖥️ Web Application

A simple **Flask web app** is developed where users can input features like temperature, wind speed, humidity, etc., and receive the predicted **FWI** value using the trained Ridge model.

### 🔗 Running the Web App:

1. Clone the repository:
   ```bash
   git clone https://github.com/Prashilkumar/ForestFires.git
   cd ForestFires

   ```

3. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the Flask app:
   ```bash
   python application.py
   ```

5. Open the browser and go to:
   ```
   http://127.0.0.1:5000/
   http://127.0.0.1:5000/predictdata
   ```

---

## 🧪 Model Performance

| Metric       | Value        |
|--------------|--------------|
| MAE          | 0.564        |
| R² Score     | 0.984        |

*(Exact values depend on training output in notebook)*

---

## 📌 Conclusion

A robust predictive system for Algerian forest fire conditions using Ridge Regression was created, evaluated, and deployed via a web interface for real-world interaction.
