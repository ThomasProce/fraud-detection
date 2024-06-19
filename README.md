# Fraud Detection Project

## Overview

This project aims to detect fraudulent transactions within a highly imbalanced dataset. Various techniques and models are employed to handle the imbalance and the presence of outliers, ensuring robust and accurate detection.

## Sample Selection

To reduce computational time, a stratified sample of 20,000 observations (approximately 10% of the original dataset) was used for visualization and model testing. Statistical tests confirmed that this sample is representative of the original dataset, maintaining similar means, standard deviations, and target variable proportions.

## Class Imbalance

Fraud detection datasets typically exhibit significant class imbalance, with fraudulent transactions being much rarer than normal ones. To address this, stratified k-fold cross-validation was employed. Additionally, oversampling, undersampling, and adjusting class weights are considered to balance the class distribution.

## Outliers

Outliers, while present, hold crucial information about fraudulent activities. Instead of removing them, robust models such as <span style="color:blue">**XGBoost**</span> and <span style="color:blue">**Random Forests**</span> were utilized, which can effectively handle the presence of outliers.

## Data Preprocessing

- **Transformations:** 
  - The 'Amount' variable was transformed using <span style="color:green">**logarithmic transformation**</span> to handle skewness.
  - The <span style="color:green">**Yeo-Johnson transformation**</span> was applied to other variables (V1, V2, ...) to address kurtosis and skewness, and to handle negative and zero values.
- **VIF and PCA:** 
  - <span style="color:green">**PCA**</span> was applied initially to the data, ensuring VIF levels are within acceptable ranges and eliminating issues related to multicollinearity.

## Visualizations

Exploratory analysis revealed:
- The 'Amount' variable exhibits pronounced kurtosis and skewness.
- The 'Time' variable shows a unique tri-modal distribution.
- Individual features (V1, V2, ...) display varying levels of kurtosis and skewness, highlighting areas for further investigation.

## Model Training

The final model, <span style="color:blue">**XGBoost**</span>, was selected based on its superior performance during testing. All models were evaluated using stratified k-fold cross-validation to maintain a balanced representation of classes.

## Potential Options to Explore

- **Oversampling or Undersampling:** Techniques to adjust the class distribution and address imbalance. <span style="color:red">*Note: Be cautious of overfitting.*</span>
- **Optimize Hyperparameters:** Utilize <span style="color:purple">**GridSearch, RandomizedSearch,**</span> or <span style="color:purple">**Bayesian optimization**</span> to find the best hyperparameters for the final model.

## Conclusion

This project underscores the importance of handling class imbalance and outliers in fraud detection. The strategies employed ensure robust model performance and reliable detection of fraudulent transactions.
