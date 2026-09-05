Customer Churn Prediction
<p align="center"> <b>Machine Learning • Explainable AI • Flask • Predictive Analytics</b> </p> <p align="center"> An end-to-end machine learning application for predicting customer churn and identifying customers who are at risk of leaving a telecom service. </p> <p align="center">










</p>
🚀 Live Demo

Try the deployed application:

Customer Churn Prediction — Live Demo

Source Code:

GitHub Repository

📌 Project Overview

Customer churn is a major business challenge for subscription-based companies. Identifying customers who are likely to leave allows organizations to take proactive retention measures before the customer churns.

This project develops a complete Customer Churn Prediction system using machine learning.

The application:

Predicts whether a customer is likely to churn
Calculates churn probability
Provides prediction confidence
Categorizes customers according to risk
Uses a trained machine learning model for inference
Provides model performance metrics
Includes feature-importance analysis
Uses SHAP for model explainability
Provides a web interface through Flask
Is deployed as a production web application using Render

The project combines data science, machine learning, explainable AI and web deployment into a single end-to-end solution.

🎯 Business Problem

Customer acquisition is often more expensive than retaining existing customers.

The objective of this project is to answer:

"Which customers are most likely to leave, and what factors contribute to their churn risk?"

The prediction system can help businesses:

Identify high-risk customers
Prioritize retention campaigns
Understand customer behavior
Analyze important churn drivers
Improve customer retention strategies
Support data-driven decision making
🧠 Machine Learning Workflow
                 Customer Data
                       │
                       ▼
              Data Preprocessing
                       │
                       ▼
             Feature Engineering
                       │
                       ▼
              Train ML Models
                       │
                       ▼
              Model Evaluation
                       │
                       ▼
             Select Best Model
                       │
             ┌─────────┴─────────┐
             ▼                   ▼
       Model Prediction      SHAP Analysis
             │                   │
             └─────────┬─────────┘
                       ▼
                Churn Probability
                       │
                       ▼
                Risk Assessment
                       │
                       ▼
              Flask Web Application
                       │
                       ▼
                 Render Deployment
📊 Dataset

The project uses the Telco Customer Churn dataset.

The dataset contains customer demographic, account, service and billing information.

The repository includes the dataset under:

data/
└── WA_Fn-UseC_-Telco-Customer-Churn.csv

The application uses customer information such as:

Customer tenure
Monthly charges
Total charges
Contract type
Internet service
Payment method
Online services
Technical support
Streaming services
Demographic information
Account-related information

The target variable is:

Churn

where the model predicts whether a customer is likely to leave the service.

🔧 Data Preprocessing

The preprocessing pipeline prepares raw customer information for machine learning.

Major preprocessing steps include:

Data cleaning
Handling missing values
Converting numerical variables
Encoding categorical variables
Feature transformation
Preparing training and testing data
Saving the preprocessing pipeline for inference

The trained preprocessor is stored in:

models/preprocessor.pkl

This allows the same preprocessing logic to be applied when new customer information is submitted to the application.

🤖 Machine Learning Models

The project includes multiple trained model artifacts and evaluates model performance before selecting the final model.

Current model artifacts include:

models/
├── best_model.pkl
├── logistic.pkl
├── preprocessor.pkl
├── model_results.csv
├── confusion_matrix.png
├── roc_curve.png
├── feature_importance.csv
└── shap_summary.png

The final application uses:

best_model.pkl

for customer churn predictions.

📈 Model Evaluation

The project evaluates model performance using commonly used classification metrics:

Accuracy
Precision
Recall
F1 Score
ROC-AUC

Visual evaluation outputs are also included:

Confusion Matrix
ROC Curve
Feature Importance
SHAP Summary Plot

These artifacts are stored in the models/ directory.

Note: Model metrics should be updated here with the final values from models/model_results.csv if you want the README to display the exact achieved scores.

Example:

Metric	Score
Accuracy	—
Precision	—
Recall	—
F1 Score	—
ROC-AUC	—
🔍 Explainable AI

A major component of this project is model interpretability.

Instead of only returning:

Churn = Yes

the system also provides insights into the factors influencing predictions.

The project uses SHAP (SHapley Additive exPlanations) to analyze feature contributions.

Why SHAP?

SHAP helps answer:

"Why did the model predict that this customer is at risk of churn?"

This makes the machine learning model more transparent and useful for business decision-making.

The repository contains:

models/shap_summary.png

for global feature-importance analysis.

🌐 Web Application

The machine learning model is integrated into a Flask web application.

The main application is:

app.py

The Flask application loads the trained model and preprocessing pipeline and uses them to generate predictions for new customers.

Application capabilities
Customer information input
Churn prediction
Churn probability
Prediction confidence
Risk classification
Historical prediction tracking
Model performance information
Feature analysis
SHAP visualization
🏗️ Project Structure
Customer-Churn-Prediction/
│
├── app.py
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── models/
│   ├── best_model.pkl
│   ├── logistic.pkl
│   ├── preprocessor.pkl
│   ├── model_results.csv
│   ├── feature_importance.csv
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   └── shap_summary.png
│
├── notebooks/
│   └── EDA.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── train.py
│   ├── predict.py
│   ├── evaluation.py
│   ├── explain.py
│   ├── utils.py
│   └── test_preprocessing.py
│
├── static/
│   ├── css/
│   ├── js/
│   └── images/
│
├── templates/
│   └── ...
│
├── requirements.txt
├── runtime.txt
├── LICENSE
└── README.md

The repository currently contains dedicated modules for preprocessing, training, prediction, evaluation and explainability, along with the Flask application and supporting frontend assets.

⚙️ Installation
1. Clone the repository
git clone https://github.com/snehasis0506-debug/Customer-Churn-Prediction.git
2. Navigate into the project
cd Customer-Churn-Prediction
3. Create a virtual environment

Windows:

python -m venv venv

Activate:

venv\Scripts\activate

Linux/macOS:

python3 -m venv venv
source venv/bin/activate
4. Install dependencies
pip install -r requirements.txt

The repository currently pins Flask, Gunicorn, Pandas, NumPy, Scikit-learn, Joblib, Matplotlib and SHAP in requirements.txt.

▶️ Run Locally

Start the Flask application:

python app.py

Then open:

http://127.0.0.1:5000
🚀 Deployment

The application is deployed using Render.

Build Command
pip install -r requirements.txt
Start Command
gunicorn app:app
Production Architecture
                 GitHub
                    │
                    ▼
             Render Deployment
                    │
                    ▼
              Gunicorn Server
                    │
                    ▼
               Flask App
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
     ML Model             Preprocessor
          │                   │
          └─────────┬─────────┘
                    ▼
              Churn Prediction
🧪 Testing

The repository includes a preprocessing test module:

src/test_preprocessing.py

You can run the available tests using:

pytest
📊 Key Technologies
Technology	Purpose
Python	Core programming language
Pandas	Data manipulation
NumPy	Numerical computation
Scikit-learn	Machine learning & preprocessing
Joblib	Model serialization
SHAP	Explainable AI
Matplotlib	Data visualization
Flask	Web application
Gunicorn	Production WSGI server
Render	Cloud deployment
Jupyter Notebook	Exploratory data analysis
💡 Business Value

The system demonstrates how machine learning can move beyond prediction and support practical business decisions.

Potential business applications

Customer Retention

Identify customers with high churn probability and prioritize retention efforts.

Risk Segmentation

Divide customers into different risk categories based on predicted probability.

Customer Analytics

Understand which customer characteristics are associated with churn.

Decision Support

Provide data-driven information that can assist customer success and marketing teams.

Explainable Predictions

Use SHAP-based analysis to understand the factors influencing individual or global predictions.

🔮 Future Improvements

Potential future enhancements include:

 Real-time prediction API
 Customer segmentation
 Automated model retraining
 Model monitoring and drift detection
 Advanced hyperparameter optimization
 Cloud-based database integration
 Authentication and user management
 REST API endpoints
 Interactive business analytics dashboard
 Automated CI/CD pipeline
 Docker containerization
 Improved model explainability
 Customer retention recommendation engine
📌 Disclaimer

This project is intended for educational, portfolio and demonstration purposes.

Predictions generated by the system should not be treated as guaranteed outcomes. Machine learning predictions depend on the quality, representativeness and limitations of the underlying data.

👨‍💻 Author

Snehasis Chatterjee

Data Science | Machine Learning | Python | Predictive Analytics

GitHub

@snehasis0506-debug

Project

Customer Churn Prediction

⭐ If you find this project useful

Consider giving the repository a star ⭐ and exploring the code, notebooks and machine learning workflow.
