# Fraudulent Claim Detection  

This project was developed to build a machine learning system that can automatically identify fraudulent insurance claims. By leveraging historical claim data and customer profiles, the model helps distinguish fraudulent claims from genuine ones at the approval stage, reducing losses and improving efficiency.  

## Problem Statement  
Insurance companies face significant financial losses due to fraudulent claims, many of which are detected only after payouts. The goal of this project is to create a predictive model that classifies claims as either fraudulent or legitimate at the approval stage.  

## Dataset  
- 1000 rows and 40 columns  
- Target variable: `fraud_reported` (Yes/No)  
- Features: customer demographics, policy information, incident details, claim amounts  

## Data Preprocessing  
- Missing values filled with median (numeric) and mode (categorical)  
- Dropped redundant columns such as IDs  
- Encoded categorical variables  
- Grouped low-frequency categories into “Other”  
- Scaled numerical features using StandardScaler  
- Addressed class imbalance using RandomOverSampler  

## Exploratory Data Analysis  
- Univariate and bivariate analysis performed on numeric and categorical features  
- Strong correlations observed between:  
  - Incident severity and fraud  
  - Total claim amount  
  - Vehicle claim amounts  
- Visualizations used: heatmaps, boxplots, histograms  

## Model Building  
Two models were trained and compared:  
- Logistic Regression (with RFECV for feature selection)  
- Random Forest Classifier (with hyperparameter tuning)  

## Model Evaluation  
- Logistic Regression: 78% accuracy, 75% recall, 79% specificity  
- Random Forest: 82% accuracy, 80% recall, 83% specificity  
- Random Forest showed the best balance between sensitivity and specificity  

## Key Predictive Features  
- Total claim amount  
- Policy annual premium  
- Incident severity  
- Number of vehicles involved  
- Availability of police report  
- Claim ratios (injury/property/vehicle claims relative to total claim)  

## Business Impact  
- Random Forest model can detect 4 out of 5 fraudulent claims (80% sensitivity)  
- Legitimate claims are processed efficiently (83% specificity), reducing unnecessary delays  
- Enables proactive fraud detection, lowering financial risks  

## Recommendations  
- Deploy Random Forest as the preferred model  
- Regularly retrain with updated data to capture evolving fraud patterns  
- Combine model predictions with human review for final decisions  
- Analyze false positives to refine detection rules  

## Future Improvements  
- Experiment with SMOTE and other resampling techniques  
- Test advanced models like XGBoost or Neural Networks  
- Integrate external fraud databases and claim history for richer features  

## Tech Stack  
- Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)  
- Jupyter Notebook for model development  
- PDF and PPT reports for documentation and presentation  

## Applications  
- Automated fraud detection during claim approval  
- Reduces financial losses for insurers  
- Improves efficiency of claims management systems  
- Provides a scalable framework adaptable to other financial fraud detection tasks  
