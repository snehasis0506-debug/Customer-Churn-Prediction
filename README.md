
# Customer Churn Prediction

### Machine Learning • Explainable AI • Flask • Predictive Analytics • Render

An end-to-end **Customer Churn Prediction** system that uses machine learning to identify customers who are likely to leave a telecom service.

The project combines:

- Data preprocessing
- Exploratory Data Analysis (EDA)
- Machine Learning
- Model evaluation
- Feature importance analysis
- SHAP-based explainability
- Flask web application
- Prediction history
- Model performance visualization
- Cloud deployment using Render

---

## 🚀 Live Demo

The application is deployed and available online:

**Live Application:**  
`customer-churn-prediction-8pir.onrender.com`

---

## 📌 Project Overview

Customer churn is a major business problem for subscription-based businesses.

When customers leave a company, the business loses recurring revenue and may need to spend additional money acquiring new customers.

The goal of this project is to build a machine learning system that can answer:

> **Which customers are most likely to churn, and what factors contribute to their churn risk?**

The application takes customer information as input and produces a churn prediction along with probability, risk information, and supporting model insights.

---

## 🎯 Business Objective

The main objective is to help businesses identify customers who are at higher risk of leaving.

The prediction system can support:

- Customer retention campaigns
- Customer risk segmentation
- Marketing decisions
- Customer success teams
- Churn analysis
- Data-driven business decisions
- Identification of important churn factors

Instead of waiting until a customer leaves, businesses can use predicted churn risk to take proactive retention actions.

---

# 🧠 Machine Learning Workflow

The complete workflow of the project is:

```text
                    Customer Dataset
                          │
                          ▼
                Data Cleaning & Validation
                          │
                          ▼
                  Data Preprocessing
                          │
                          ▼
                 Feature Transformation
                          │
                          ▼
                  Model Training
                          │
                          ▼
                 Model Evaluation
                          │
                          ▼
                  Best Model Selection
                          │
             ┌────────────┴────────────┐
             ▼                         ▼
       Model Prediction          SHAP Analysis
             │                         │
             └────────────┬────────────┘
                          ▼
                  Churn Probability
                          │
                          ▼
                    Risk Category
                          │
                          ▼
                  Flask Web Application
                          │
                          ▼
                    Render Deployment
````

---

# 📊 Dataset

This project uses the **Telco Customer Churn dataset**.

The dataset contains information about customers, including:

### Customer Information

* Customer tenure
* Demographic information
* Contract information
* Payment method
* Monthly charges
* Total charges

### Services

* Internet service
* Online security
* Online backup
* Device protection
* Tech support
* Streaming TV
* Streaming movies

### Target Variable

The target variable is:

```text
Churn
```

The model predicts whether the customer is likely to leave the service.

---

# 🔧 Data Preprocessing

Raw customer data cannot always be directly provided to a machine learning model.

The project therefore includes a preprocessing pipeline responsible for preparing the data.

The preprocessing stage includes:

1. Loading the dataset
2. Data cleaning
3. Handling missing values
4. Converting data types
5. Separating numerical and categorical features
6. Encoding categorical variables
7. Transforming numerical variables
8. Preparing model-ready features
9. Saving the preprocessing pipeline

The trained preprocessing object is saved as:

```text
models/preprocessor.pkl
```

The same preprocessing pipeline is reused during prediction so that new customer data is transformed consistently with the training data.

---

# 🤖 Machine Learning Models

The project contains multiple trained model artifacts and evaluates model performance before selecting the final model.

The main trained artifacts include:

```text
models/
├── best_model.pkl
└── logistic.pkl
```

The final deployed application uses:

```text
best_model.pkl
```

for customer churn prediction.

Model comparison results are stored in:

```text
models/model_results.csv
```

This allows the project to compare model performance and retain the evaluation results.

---

# 📈 Model Evaluation

The project evaluates classification performance using several standard metrics.

### Evaluation Metrics

| Metric    | Description                                                 |
| --------- | ----------------------------------------------------------- |
| Accuracy  | Percentage of correctly classified predictions              |
| Precision | How many predicted churn customers actually churned         |
| Recall    | How many actual churn customers were correctly identified   |
| F1 Score  | Harmonic mean of precision and recall                       |
| ROC-AUC   | Measures the model's ability to distinguish between classes |

The project also generates visual evaluation artifacts.

### Evaluation Files

```text
models/
├── confusion_matrix.png
├── roc_curve.png
├── feature_importance.csv
└── shap_summary.png
```

These files provide different perspectives on model performance and interpretation.

> **Note:** Exact model scores should be taken directly from `models/model_results.csv` rather than manually entering estimated values in this README.

---

# 🔍 Explainable AI

A major feature of this project is **model explainability**.

A machine learning model should not only provide a prediction; it should also help explain why a prediction was made.

This project uses **SHAP (SHapley Additive exPlanations)** to understand feature contributions.

### SHAP helps answer:

> Why did the model predict that this customer is likely to churn?

SHAP analysis can help identify which customer characteristics have the strongest influence on churn predictions.

The project contains a SHAP summary visualization:

```text
models/shap_summary.png
```

This provides a global view of feature importance and model behavior.

---

# 🌐 Web Application

The machine learning model is integrated into a **Flask web application**.

The main application file is:

```text
app.py
```

The Flask application loads:

* The trained machine learning model
* The preprocessing pipeline
* Model evaluation results
* Dataset information
* SHAP visualization
* Feature importance information

### Application Features

The web application provides functionality for:

* Customer information input
* Churn prediction
* Churn probability
* Prediction confidence
* Risk classification
* Prediction history
* Model performance information
* Feature importance analysis
* SHAP visualization

---

# 🏗️ Project Structure

The project follows a modular structure that separates data, machine learning code, trained models, notebooks, and web application files.

```text
Customer-Churn-Prediction/
│
├── app.py
│   └── Main Flask web application
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│       └── Telco customer churn dataset
│
├── models/
│   ├── best_model.pkl
│   │   └── Final trained machine learning model
│   │
│   ├── logistic.pkl
│   │   └── Logistic regression model artifact
│   │
│   ├── preprocessor.pkl
│   │   └── Saved data preprocessing pipeline
│   │
│   ├── model_results.csv
│   │   └── Model comparison and evaluation results
│   │
│   ├── feature_importance.csv
│   │   └── Feature importance results
│   │
│   ├── confusion_matrix.png
│   │   └── Confusion matrix visualization
│   │
│   ├── roc_curve.png
│   │   └── ROC curve visualization
│   │
│   └── shap_summary.png
│       └── SHAP feature-importance visualization
│
├── notebooks/
│   └── EDA.ipynb
│       └── Exploratory Data Analysis
│
├── src/
│   ├── preprocessing.py
│   │   └── Data preprocessing functions
│   │
│   ├── train.py
│   │   └── Model training pipeline
│   │
│   ├── predict.py
│   │   └── Prediction-related functionality
│   │
│   ├── evaluation.py
│   │   └── Model evaluation and metrics
│   │
│   ├── explain.py
│   │   └── Explainability and SHAP analysis
│   │
│   ├── utils.py
│   │   └── Utility/helper functions
│   │
│   └── test_preprocessing.py
│       └── Tests for preprocessing functionality
│
├── static/
│   ├── css/
│   │   └── Frontend stylesheets
│   │
│   ├── js/
│   │   └── Frontend JavaScript
│   │
│   └── images/
│       └── Application images and visual assets
│
├── templates/
│   └── Flask HTML templates
│
├── catboost_info/
│   └── CatBoost training information/artifacts
│
├── requirements.txt
│   └── Python dependencies
│
├── runtime.txt
│   └── Python runtime configuration
│
├── .gitignore
│   └── Git ignored files and folders
│
├── LICENSE
│   └── Project license
│
└── README.md
    └── Project documentation
```

---

# 📂 Folder Responsibilities

## `data/`

Contains the dataset used by the project.

```text
data/
└── WA_Fn-UseC_-Telco-Customer-Churn.csv
```

The dataset contains customer information and the target churn variable.

---

## `models/`

Contains trained models, preprocessing objects, evaluation results, and visualization artifacts.

This directory is important because the Flask application loads the trained model and preprocessing pipeline from here.

---

## `notebooks/`

Contains Jupyter notebooks used for exploratory analysis.

```text
notebooks/
└── EDA.ipynb
```

The notebook can be used to investigate:

* Dataset structure
* Missing values
* Feature distributions
* Customer behavior
* Churn distribution
* Relationships between variables

---

## `src/`

Contains the core machine learning code.

### `preprocessing.py`

Responsible for preparing raw customer data for machine learning.

### `train.py`

Responsible for training machine learning models and generating trained model artifacts.

### `predict.py`

Contains prediction-related functionality.

### `evaluation.py`

Responsible for evaluating trained models using classification metrics.

### `explain.py`

Contains model explainability functionality, including SHAP analysis.

### `utils.py`

Contains reusable helper functions.

### `test_preprocessing.py`

Contains tests for preprocessing functionality.

---

## `templates/`

Contains the HTML templates used by the Flask application.

Flask uses these templates to render the web application's user interface.

---

## `static/`

Contains frontend assets such as:

* CSS
* JavaScript
* Images

These files control the visual appearance and client-side behavior of the web application.

---

## `app.py`

This is the main entry point of the Flask application.

It connects the machine learning pipeline with the web interface.

The application:

1. Receives customer information
2. Processes the input
3. Applies the saved preprocessing pipeline
4. Loads the trained model
5. Generates a churn prediction
6. Calculates prediction probability
7. Determines customer risk
8. Displays the result through the web interface

---

# 🔄 Prediction Pipeline

When a user submits customer information, the application follows this process:

```text
User Input
    │
    ▼
Flask Application
    │
    ▼
Input Validation
    │
    ▼
Preprocessing Pipeline
    │
    ▼
Feature Transformation
    │
    ▼
Trained ML Model
    │
    ▼
Prediction
    │
    ├── Churn Prediction
    ├── Probability
    └── Risk Classification
    │
    ▼
Web Application Result
```

---

# 🛠️ Technologies Used

| Technology       | Purpose                            |
| ---------------- | ---------------------------------- |
| Python           | Core programming language          |
| Pandas           | Data manipulation                  |
| NumPy            | Numerical computation              |
| Scikit-learn     | Machine learning and preprocessing |
| Joblib           | Model serialization                |
| SHAP             | Explainable AI                     |
| Matplotlib       | Data visualization                 |
| Flask            | Web application                    |
| Gunicorn         | Production WSGI server             |
| Jupyter Notebook | Exploratory Data Analysis          |
| Render           | Cloud deployment                   |
| Git & GitHub     | Version control                    |

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/snehasis0506-debug/Customer-Churn-Prediction.git
```

## 2. Navigate to the Project

```bash
cd Customer-Churn-Prediction
```

## 3. Create a Virtual Environment

### Windows

```bash
python -m venv venv
```

Activate the environment:

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
```

Activate:

```bash
source venv/bin/activate
```

## 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Run the Application Locally

Start the Flask application:

```bash
python app.py
```

The application will be available at:

```text
http://127.0.0.1:5000
```

Open the address in your browser to access the application.

---

# 🧪 Testing

The project includes preprocessing tests:

```text
src/test_preprocessing.py
```

Run the tests using:

```bash
pytest
```

Testing helps verify that the preprocessing functionality behaves as expected.

---

# 🚀 Deployment

The application is deployed using **Render**.

### Build Command

```bash
pip install -r requirements.txt
```

### Start Command

```bash
gunicorn app:app
```

### Deployment Architecture

```text
GitHub Repository
       │
       ▼
     Render
       │
       ▼
    Gunicorn
       │
       ▼
   Flask App
       │
       ├───────────────┐
       ▼               ▼
Preprocessor       ML Model
       │               │
       └───────┬───────┘
               ▼
       Churn Prediction
               │
               ▼
        Web Application
```

---

# 📊 Model Artifacts

The repository stores important model-related artifacts inside the `models/` directory.

| File                     | Purpose                               |
| ------------------------ | ------------------------------------- |
| `best_model.pkl`         | Final selected model                  |
| `logistic.pkl`           | Logistic regression model             |
| `preprocessor.pkl`       | Saved preprocessing pipeline          |
| `model_results.csv`      | Model evaluation results              |
| `feature_importance.csv` | Feature importance information        |
| `confusion_matrix.png`   | Confusion matrix                      |
| `roc_curve.png`          | ROC curve                             |
| `shap_summary.png`       | SHAP feature-importance visualization |

---

# 💡 Business Value

The project demonstrates how machine learning can be used to support customer retention strategies.

### 1. Customer Retention

Identify customers with a high probability of churn.

### 2. Risk Segmentation

Classify customers according to their predicted churn risk.

### 3. Customer Analytics

Analyze customer characteristics associated with churn.

### 4. Targeted Marketing

Prioritize retention campaigns for high-risk customers.

### 5. Decision Support

Provide data-driven insights to customer success and marketing teams.

### 6. Explainable Predictions

Use SHAP analysis to understand the factors influencing model predictions.

---

# 🔍 Why Explainability Matters

A prediction such as:

```text
Churn = Yes
```

does not tell a business why the customer is likely to leave.

An explainable machine learning system can provide additional insight into the factors contributing to the prediction.

For example, factors such as:

* Contract type
* Monthly charges
* Tenure
* Internet service
* Payment method
* Customer support services

may influence churn probability.

SHAP analysis helps make these model predictions easier to interpret.

---

# ⚠️ Limitations

This project is intended primarily for:

* Learning
* Demonstration
* Portfolio development
* Machine learning experimentation
* Educational purposes

Model predictions should not be treated as guaranteed outcomes.

Real-world deployment would require:

* Continuous model monitoring
* Regular retraining
* Data drift detection
* Larger and more representative datasets
* Business validation
* Security improvements
* Production-grade logging
* Robust API validation

---

# 🔮 Future Improvements

Potential improvements include:

* Hyperparameter optimization
* Additional machine learning algorithms
* Automated model retraining
* Cross-validation improvements
* Advanced feature engineering
* Customer lifetime value prediction
* Churn probability calibration
* REST API development
* Docker containerization
* CI/CD pipeline
* Model monitoring
* Data drift monitoring
* Automated testing
* Cloud database integration
* Authentication and authorization

---

# 📚 Project Learning Outcomes

This project demonstrates practical experience with:

* End-to-end machine learning workflows
* Data preprocessing
* Exploratory data analysis
* Classification algorithms
* Model evaluation
* Feature importance
* Explainable AI
* SHAP
* Model serialization
* Flask development
* Frontend integration
* Automated testing
* Git/GitHub
* Cloud deployment
* Production-style ML application structure

---

# 👨‍💻 Author

**Snehasis Chatterjee**

Machine Learning / Data Science Project

GitHub: `snehasis0506-debug`

---

# 📄 License

This project is available under the license included in the repository.

See:

```text
LICENSE
```

---

# ⭐ Acknowledgement

This project was developed as an end-to-end machine learning portfolio project demonstrating how predictive analytics, explainable AI, and web application deployment can be combined into a single solution.

---

## ⭐ If you find this project useful

Consider giving the repository a ⭐ on GitHub.

````
