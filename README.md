# Intelligent Ventilation Control System for Onion Storage
## Machine Learning Module

---

## 📌 Project Overview

This project implements a Machine Learning-based system to automatically control ventilation in onion storage bins using environmental sensor data.

The system monitors:

- Gas concentration
- Temperature (Min/Max)
- Humidity (Min/Max)

Using these parameters, a trained ML model predicts the required fan speed to prevent spoilage and maintain optimal storage conditions.

The output is mapped to PWM/RPM values and used for real-time fan control via ESP32.

---

## 📁 Project Structure
ventilation_onion_system/
│
├── Dataset/
│ └── final_onion_ventilation_dataset.csv
│
├── Model/
│ ├── final_fan_speed_model.pkl
│ └── model_columns.pkl
│
├── Code/
│ ├── ML_Training_and_Testing.ipynb
│ └── predict.py
│
├── Report/
│ └── ML_Module_Report.pdf
│
├── requirements.txt
└── README.md


---

## 📊 Dataset Description

The final dataset contains 198 samples with the following features:

| Column | Description |
|--------|-------------|
| Gas | Rotten onion gas concentration (ppm) |
| Temp_Min | Minimum temperature (°C) |
| Temp_Max | Maximum temperature (°C) |
| Hum_Min | Minimum humidity (%) |
| Hum_Max | Maximum humidity (%) |
| Speed | Fan speed label (2 = Normal, 3 = Danger) |

The dataset is fully cleaned and contains no missing values.

---

## 🧠 Machine Learning Model

- Algorithm Used: Random Forest Classifier
- Type: Supervised Learning (Binary Classification)
- Classes:
  - 2 → Normal / Warning
  - 3 → Dangerous Condition

### Key Features:
- Class imbalance handled using class_weight="balanced"
- Hyperparameter tuning using GridSearchCV
- Optimized using Macro F1-score
- Cross-validation applied

---

## ⚙️ Software Requirements

All dependencies are listed in `requirements.txt`.

To install:

```bash
pip install -r requirements.txt

Main Libraries:
numpy
pandas
scikit-learn
joblib
matplotlib
seaborn

🚀 How to Run the Project
Step 1: Install Dependencies
      pip install -r requirements.txt
Step 2: View Training Process
      Code/ML_Training_and_Testing.ipynb
This file contains:
1)Data preprocessing
2)Label engineering
3)Model training
4)Tuning
5)Evaluation
6)Testing
7)Model saving

Step 3: Run Prediction Script
Open terminal in project folder and run:
        python Code/predict.py
This will:
-Load trained model
-Accept sample inputs
-Output predicted fan speed

🔁 Model Reusability
The trained model is saved using joblib:
        final_fan_speed_model.pkl (It can be reused without retraining.)

Model loading example:
        import joblib
        model = joblib.load("final_fan_speed_model.pkl")

🌬️ Fan Speed Mapping

The ML output is mapped to fan speed as follows:

ML Output Condition	      RPM	        PWM
2	Normal/ Warning 	~1800 RPM	    150
3	Dangerous	        ~3000 RPM	    255

This mapping is used in ESP32 for motor control.

🧪 Testing and Validation
@The model was tested using:
-Manual test cases
-Stress testing
-Noise robustness testing
-Boundary condition testing
-Confusion matrix analysis
-Cross-validation

@Key Result:
-Accuracy: 86%
-Macro F1-score: 0.79
-Danger Recall: 97%
This ensures high reliability and safety.

🔌 System Integration
-System workflow:
Sensors → ESP32 → ML Model → Speed Prediction → PWM → Fan

Steps:
1)ESP32 collects sensor values
2)Data is sent to ML module
3)Model predicts speed
4)PWM controls fan motor

⚠️ Limitations
1)Small dataset size
2)Limited seasonal data
3)Few healthy samples
4)Depends on sensor accuracy
5)These factors may affect long-term generalization.

🔮 Future Scope
1)Larger dataset collection
2)Cloud-based monitoring
3)Real-time dashboards
4)Deep learning integration
5)Adaptive learning models
6)Mobile app integration


