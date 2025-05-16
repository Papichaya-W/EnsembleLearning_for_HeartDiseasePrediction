# Heart Attack Prediction

This project aims to build a machine learning model to predict risk of having a heart attack based on  health-related and lifestyle features using data from https://www.kaggle.com/datasets/alexteboul/heart-disease-health-indicators-dataset

## 📂 Table of Contents

* [Data Loading](#data-loading)
* [Data Cleaning](#data-cleaning)
* [Data Preprocessing](#data-preprocessing)
* [Model Architecture](#model-architecture)
* [Proposed Model](#proposed-model)
* [Evaluation](#evaluation)

---

## Dataset Description

The dataset includes health and lifestyle survey responses. The **target variable** is:

* `HeartDiseaseorAttack`: Whether the respondent ever had coronary heart disease (CHD) or myocardial infarction (MI)

  * *(1 = Yes, 0 = No)*

### Input Features:

| Feature             | Description                                                                 |
| ------------------- | --------------------------------------------------------------------------- |
| `HighBP`            | High blood pressure diagnosis                                               |
| `HighChol`          | High cholesterol diagnosis                                                  |
| `CholCheck`         | Had cholesterol checked in the past 5 years                                 |
| `BMI`               | Body Mass Index                                                             |
| `Smoker`            | Smoked at least 100 cigarettes in lifetime                                  |
| `Stroke`            | History of stroke                                                           |
| `Diabetes`          | Diabetes status *(2 = yes, 1 = pre-diabetes, 0 = no/only during pregnancy)* |
| `PhysActivity`      | Physical activity in past 30 days                                           |
| `Fruits`            | Eats fruit ≥1 time/day                                                      |
| `Veggies`           | Eats vegetables ≥1 time/day                                                 |
| `HvyAlcoholConsump` | Heavy alcohol consumption                                                   |
| `AnyHealthcare`     | Has healthcare coverage                                                     |
| `NoDocbcCost`       | Could not see a doctor due to cost                                          |
| `GenHlth`           | General health (1 = Excellent to 5 = Poor)                                  |
| `MentHlth`          | Days with poor mental health (0–30)                                         |
| `PhysHlth`          | Days with poor physical health (0–30)                                       |
| `DiffWalk`          | Difficulty walking or climbing stairs                                       |
| `Sex`               | (1 = Male, 0 = Female)                                                      |
| `Age`               | Age category (1 = 18–24, ..., 13 = 80+)                                     |
| `Education`         | Education level (1 = none to 6 = college grad)                              |
| `Income`            | Income level (1 = <10K to 8 = ≥75K USD)                                     |

---

## Data Loading

Data is loaded from a structured CSV file containing the features and target label. The initial loading step ensures correct data types and handles missing values if present.

---

## Data Cleaning

* Removed or imputed missing values
* Checked for outliers in `BMI`, `MentHlth`, and `PhysHlth`
* Converted categorical variables into suitable format

---

## Data Preprocessing

* Applied label encoding or one-hot encoding as needed
* Scaled numerical features using StandardScaler
* Balanced the dataset (e.g. using undersampling or SMOTE) to handle class imbalance

---

## Model Architecture

The model pipeline includes the following steps:

1. **Feature Selection**: Based on domain relevance and correlation
2. **Train-Test Split**: Stratified 80-20 or cross-validation approach
3. **Modeling**: Compared different classifiers such as:

   * Logistic Regression
   * Decision Tree
   * Random Forest
   * XGBoost

---

## Proposed Model

The final selected model was a **\[optimized Stacking with tuned XGBoost, Bagging, AdaBoost, and Decision tree as base learner (Final estimator = XGBoost)]** based on performance metrics.

Model training used:

* Cross-validation
* Hyperparameter tuning

---

## Evaluation

Model performance was evaluated using:

* Accuracy
* Precision, Recall, F1-Score
* ROC-AUC curve
* Confusion Matrix
