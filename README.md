# Stroke Prediction

I predict stroke risk from health and demographic data. I keep the workflow short and readable so a reviewer can follow it in a few minutes.

## Goal
Predict which people are more likely to have a stroke.

## Why it matters
Even a small gain in recall can help flag people for earlier screening.

## Data
- Demographics, medical history, and lifestyle indicators
- Target: stroke (binary)
- I do not commit raw data. See data/README.md

## Method
- Encode categorical features and handle missing BMI with a flag and the train median
- Stratified train, validation, and test split
- I tried Logistic Regression, Decision Tree, Random Forest, and XGBoost
- Final model: Random Forest

## Results
- Cross validation: F1 ≈ 0.959, ROC AUC ≈ 0.993
- Test set at threshold 0.45: accuracy ≈ 0.91, precision ≈ 0.17, recall ≈ 0.20, ROC AUC ≈ 0.786
- Top drivers: age, work type, residence type, BMI, heart disease, glucose

## Limitations and next steps
- Low recall for stroke cases at common thresholds due to class imbalance
- Next steps: lower the threshold, try class weights or focused resampling, and collect more positive cases

## How to run
1. pip install -r requirements.txt
2. Place the dataset in the data/ folder
3. Open stroke_final_ready.ipynb and run all
