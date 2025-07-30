## Codeforces Rating Prediction

### Project Overview

This project aims to predict the **rank type (rating category)** of a user on the Codeforces competitive programming platform based on their performance in a series of contests. By analyzing contest scores, the goal is to develop a machine learning model that can classify users into different rank tiers (e.g., Master, Candidate Master, Grandmaster). This can help new users understand their potential rank, or serve as a performance indicator.

-----

### Technical Highlights

  * **Dataset**: [Kaggle - Codeforces Ratings Classification and Regression](https://www.kaggle.com/datasets/meruvulikith/codeforces-ratings-classification-and-regression)
  * **Size**: 1423 entries, 12 columns
  * **Key Features**:
      * `contest1` through `contest10` (scores in previous contests).
  * **Approach**:
      * Data Cleaning: Dropped 'userid' as it's a unique identifier. Filled missing numerical values (in `contest4` to `contest10`) with the mean. No duplicates were found.
      * Exploratory Data Analysis: Histograms, Boxplots, and Heatmaps were used for visualization to understand data distributions and correlations.
      * Label Encoding: Applied to all columns, including numerical ones and the target `rank-type`.
      * Data Standardization: Applied `StandardScaler` to numerical columns in training and test sets.
      * Multi-class Classification: The target variable `rank-type` has 8 distinct categories (e.g., 'Master', 'Candidate Master', 'Grandmaster').
      * Models Used:
          * Logistic Regression, Ridge Classifier, SVC, Random Forest, XGBoost, AdaBoost, Gradient Boosting, Bagging, Decision Tree.
  * **Best Accuracy**:
      * 100% with Gradient Boosting Classifier, Bagging Classifier, and Decision Tree Classifier.
      * 99.3% with XGBoost Classifier.
      * 98.2% with Random Forest Classifier.
      * The very high accuracies might suggest that contest scores are highly indicative of rank-type, or possibly a data-related artifact that makes classification straightforward.

-----

### Purpose and Applications

  * Predict the **Codeforces rank-type** of competitive programmers based on their contest performance.
  * Provide new users with an estimated rank category.
  * Serve as a performance monitoring tool for competitive programmers.
  * Offer insights into the progression of skills required to achieve higher ranks.

-----

### Installation

Clone the repository:

```bash
git clone https://github.com/BhaveshBhakta/Codeforces-Rating-Prediction-Using-ML.git
cd Codeforces-Rating-Prediction-Using-ML
```

Install the necessary libraries:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn xgboost
```

-----

### Collaboration

We welcome contributions to improve the project. You can help by:

  * Investigating the very high accuracy for potential data leakage or overfitting, especially for small class sizes within the target variable.
  * Exploring feature engineering to create more complex indicators from contest scores (e.g., average change in score, consistency).
  * Performing comprehensive hyperparameter tuning and cross-validation for all models.
  * Adding explainability (e.g., SHAP or LIME) to understand which contest performances are most influential in determining rank-type.
