# Airline Passenger Satisfaction — ML Analysis (University Project)

## Project Overview
This project analyzes **airline passenger satisfaction** using multiple machine learning models.  
The goal is to identify key drivers of satisfaction and predict whether a passenger is satisfied based on their flight experience.

The workflow covers:
- Data preprocessing & feature engineering
- Training multiple classifiers (Logistic Regression, Random Forest, XGBoost, LightGBM)
- Model evaluation with cross-validation and test set metrics
- Model explainability using SHAP



## Tech Stack
- Python (pandas, numpy, matplotlib, seaborn)  
- Scikit-learn for baseline models and evaluation  
- XGBoost & LightGBM for gradient boosting  
- SHAP for explainability  


## Repository Structure
├── notebooks/
│ └── airline_satisfaction.ipynb # main workflow notebook
├── data/
│ ├── train.csv
│ └── test.csv
├── README.md



## Workflow

### 1. Data Preprocessing
- Removed ID columns  
- Handled missing values (`Arrival Delay in Minutes`)  
- Encoded target variable (`satisfied = 1`, `neutral/dissatisfied = 0`)  
- One-hot encoded categorical features  

### 2. Model Training & Validation
- Logistic Regression (baseline)  
- Random Forest  
- XGBoost  
- LightGBM  
- 5-fold cross-validation on training set  
- Final evaluation on test set  

### 3. Explainability (SHAP)
- Global importance bar plots  
- Beeswarm plots to show direction & distribution of effects  


## Results

| Model                | CV Mean | Test Accuracy | Test Precision | Test Recall | Test F1 |
|----------------------|---------|---------------|----------------|-------------|---------|
| Logistic Regression  | 0.866   | 0.864         | 0.852          | 0.835       | 0.843   |
| Random Forest        | 0.952   | 0.953         | 0.954          | 0.938       | 0.946   |
| XGBoost              | 0.963   | 0.963         | 0.970          | 0.945       | 0.957   |
| LightGBM             | 0.965   | 0.964         | 0.974          | 0.944       | 0.959   |

**LightGBM** achieved the best overall performance.


## Business Insights

From the SHAP analysis and model results, we identify several key drivers of passenger satisfaction:

- **Type of Travel (Business vs Personal):** Business travelers report higher satisfaction, likely due to upgraded service and loyalty perks.  
- **Class (Economy vs Business/First):** Premium class strongly boosts satisfaction, highlighting the role of comfort and service quality.  
- **Flight Delays:** Longer delays significantly reduce satisfaction, especially arrival delays.  
- **Inflight Service Ratings (e.g., WiFi, Food, Entertainment, Cleanliness):** Consistently among the top predictors of satisfaction.  
- **Loyalty (Customer Type: Returning vs First-time):** Returning customers tend to be more satisfied, possibly reflecting loyalty programs and familiarity.  

