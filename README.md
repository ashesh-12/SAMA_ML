🧠 Disease Prediction System using Machine Learning
📌 Project Overview
This project aims to build a Disease Prediction System that predicts the most likely disease based on input symptoms. The core idea is to assist in preliminary diagnosis using Machine Learning, specifically Random Forest Classifier, trained on a structured dataset of symptoms and diseases.

✅ Project Type
ML Domain: Supervised Learning

Task Type: Multi-Class Classification

Data Type: Tabular Data

Application Area: Healthcare AI / Medical Diagnosis

📂 Dataset Description
Source: CSV file with symptom indicators and target diseases.

Initial Size: ~49,000 rows, 492 columns (symptoms + target label)

Preprocessing Steps:

Removed null and duplicate rows

Handled outliers and imbalance

Reduced dataset to relevant features (≈151 columns)

Final dataset used for modeling: symptom_reduced.csv

🧪 Sampling for Initial Training
To avoid memory issues and improve development speed, a sampled version (10,000 rows) was created:

Used for initial model development

Visualized top 30 important features using RandomForestClassifier.feature_importances_

📊 Feature Importance Visualization

Top 30 symptoms influencing disease prediction (sampled dataset)

🤖 Final Model Training: Random Forest
After testing on sampled data, the full symptom_reduced.csv dataset was used to train the final model.

Model Used
RandomForestClassifier(n_estimators=100, random_state=42)

Evaluation Metrics
Accuracy: 0.70 or 70%

Weighted Avg Precision/Recall/F1: ~0.70

Macro Avg: Lower due to class imbalance

Classification Report (Excerpt)
mathematica
Copy
Edit
Accuracy                           0.70     37921
Macro Avg                         0.57     0.53     0.54
Weighted Avg                      0.71     0.70     0.70


💾 Model Saving & Usage
The trained model was saved as:

# Save the model
import joblib
joblib.dump(rf_model, "rf_model_all.pkl")
To load the model later:

python
Copy
Edit
# Load the model
rf_model = joblib.load("rf_model_all.pkl")


📁 Directory Structure (Recommended)
mathematica
Copy
Edit
SAMA_ML/
│
├── Datasets/
│   └── symptom_reduced.csv
│
├── Models/
│   └── rf_model_all.pkl
│
├── Notebooks/
│   └── Disease_Prediction_Model.ipynb
│
└── README.md


📈 Future Scope
Try advanced models like XGBoost, LightGBM, or Neural Networks

Improve class balance using SMOTE or class-weighting

Deploy with a Flask/Streamlit app

Add a symptom checker interface