# Customer Churn Prediction System - Telco Dataset

## Project Overview

This project focuses on building a **Customer Churn Prediction System** using a Telco customer dataset. The goal is to predict whether a customer will churn (i.e., stop using the service) based on features like contract type, monthly charges, and tenure. Given the dataset's imbalanced nature, **SMOTEENN** (Synthetic Minority Over-sampling Technique combined with Edited Nearest Neighbors) is used to handle class imbalance and enhance model performance.

## Workflow Summary

1. **Data Preprocessing**
   - Loaded and cleaned the dataset, handling missing values and transforming categorical variables with **one-hot encoding**.
   - Detected an imbalance in the target variable (`Churn`), with a 73:27 split between non-churners and churners.

2. **Feature Engineering**
   - Converted categorical variables into numeric format.
   - Grouped customers by tenure and removed irrelevant features like `CustomerID`.

3. **Exploratory Data Analysis (EDA)**
   - Visualized relationships between customer features (e.g., monthly charges, tenure) and churn.
   - Found that **short tenure**, **high monthly charges**, and the absence of **tech support** or **security services** were correlated with churn.

4. **Model Building**
   - Built several models:
     - **Decision Tree Classifier**: Baseline model.
     - **Random Forest Classifier**: Enhanced performance with hyperparameter tuning (max depth = 6).
   - Used **SMOTEENN** to resample the dataset, addressing the class imbalance for better prediction of churners.

5. **Model Evaluation**
   - Evaluated models using precision, recall, and F1 score, focusing on the **recall** of churned customers.
   - Achieved **94% accuracy** with **Random Forest + SMOTEENN**, significantly improving the recall for the minority class (churners).

6. **Model Saving**
   - Saved the final **Random Forest Classifier** using **Pickle** for future use in APIs or a user interface.

## Front-End Integration
- The front end is designed using **Streamlit** to create an interactive user interface where customers' data can be input and churn prediction results are displayed.

## Key Libraries and Tools
- **Python**
- **pandas**, **numpy** for data manipulation
- **seaborn**, **matplotlib** for data visualization
- **scikit-learn** for machine learning models
- **imblearn** for handling class imbalance (SMOTEENN)
- **Streamlit** for the front-end interface
- **pickle** for saving and loading trained models

## How to Use

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/Customer-Churn-Prediction-System.git
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**:
   ```bash
   streamlit run app.py
   ```

4. **Make Predictions**:
   - Enter customer data through the Streamlit interface and receive churn prediction results.

## Future Scope
- Deploy the model as an API for real-time predictions.
- Test advanced models like **XGBoost** or **Gradient Boosting** to further improve accuracy.
