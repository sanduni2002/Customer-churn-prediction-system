# Customer Churn Prediction System - Telco Dataset

## Project Overview

This project focuses on building a **Customer Churn Prediction System** using a sample Telco customer dataset. The system aims to predict whether a customer will churn (i.e., stop using the company's service) based on various features like contract type, monthly charges, tenure, and more. Given the dataset's imbalanced nature, techniques like **SMOTEENN** (Synthetic Minority Over-sampling Technique combined with Edited Nearest Neighbors) were used to handle class imbalance and improve the model's performance.

## Workflow Summary

1. **Data Preprocessing**
   - Loaded the Telco dataset and cleaned it by handling missing values and transforming categorical features using **one-hot encoding**.
   - Checked for data imbalance in the target variable (`Churn`), which showed a 73:27 imbalance between non-churners and churners.

2. **Feature Engineering**
   - Converted relevant categorical variables into numeric ones.
   - Grouped customers by tenure and removed irrelevant features like `CustomerID`.

3. **Exploratory Data Analysis**
   - Visualized the relationships between customer features (e.g., **monthly charges**, **tenure**, **total charges**) and churn.
   - Found insights, such as **higher churn for customers with short tenure, high monthly charges, and no tech support or security services**.

4. **Model Building**
   - Built multiple models to predict churn:
     - **Decision Tree Classifier**: Initial model with low performance on an imbalanced dataset.
     - **Random Forest Classifier**: Improved performance with a depth of 6, leading to better accuracy.
   - Handled class imbalance using **SMOTEENN** to resample the dataset for better classification of minority classes (churners).

5. **Evaluation**
   - Evaluated models based on recall, precision, and F1 score for the minority class, especially focusing on **recall** to capture more churners.
   - Achieved **94% accuracy** with **Random Forest and SMOTEENN**, and significantly improved recall for churned customers.

6. **Model Saving**
   - Final **Random Forest Classifier** was saved using **Pickle** for future use in APIs or UI integration.

## Key Libraries and Tools
- **Python**: Programming language used for development.
- **pandas, numpy**: For data manipulation and analysis.
- **seaborn, matplotlib**: For data visualization.
- **sklearn**: For model building, evaluation, and metrics.
- **imblearn**: For handling class imbalance with SMOTEENN.
- **pickle**: To save and load the trained models.

## Future Scope
- Deploy the model as an API to integrate with a UI for real-time churn prediction.
- Test different machine learning models such as **XGBoost** or **Gradient Boosting** for further performance improvements.

## How to Use

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/Customer-Churn-Prediction-System.git
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the model**:
   - Load the saved model (`model.sav`) and use it for predictions:
     ```python
     import pickle
     loaded_model = pickle.load(open('model.sav', 'rb'))
     # Use the loaded model for predictions
     loaded_model.predict(X_test)
     ```

4. **Run the application**:
   - If integrated with a UI or API, start the server and use the model for real-time predictions.

This project provides a solid foundation for predicting customer churn using machine learning models, ensuring that organizations can proactively engage customers and reduce churn.
