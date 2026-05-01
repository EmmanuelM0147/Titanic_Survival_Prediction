# Titanic Survival Prediction Project

## Project Overview
This project aims to predict the survival of passengers on the Titanic using various machine learning techniques. We perform comprehensive exploratory data analysis (EDA), data preprocessing, and build a classification model to predict survival outcomes. The dataset includes passenger information such as age, gender, passenger class, fare, and family details.

## Table of Contents
1.  [Setup and Configuration](#setup-and-configuration)
2.  [Data Loading and Initial Exploration](#data-loading-and-initial-exploration)
3.  [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4.  [Data Preprocessing and Feature Engineering](#data-preprocessing-and-feature-engineering)
5.  [Model Training and Evaluation](#model-training-and-evaluation)
6.  [Key Findings](#key-findings)

## Setup and Configuration
Before running the notebook, ensure you have:
*   **GitHub Personal Access Token (PAT):** Stored in Colab Secrets named `GITHUB_TOKEN` with notebook access enabled. This is used for syncing the notebook with GitHub.
*   **Git Configuration:** Your GitHub username and email configured for Git commits.

## Data Loading and Initial Exploration
This section loads the `train.csv` dataset, which contains passenger information and survival status. It includes:
*   Loading data into a Pandas DataFrame.
*   Displaying basic information (`.info()`).
*   Checking for missing values (`.isnull().sum()`).
*   Calculating the overall survival rate.
*   Providing summary statistics (`.describe()`).

## Exploratory Data Analysis (EDA)
Visualizations are used to understand data distributions, relationships between features, and their impact on survival. Key visualizations include:
*   Survival rates by gender.
*   Survival rates by passenger class (Pclass).
*   Age distribution by survival status.
*   Correlation heatmap of key features.

## Data Preprocessing and Feature Engineering
This section prepares the data for model training:
*   **Handling Missing Values:**
    *   `Age` is imputed using the median age grouped by `Pclass` and `Sex`.
    *   `Fare` is imputed with its median.
    *   `Embarked` is imputed with the most frequent value (mode).
*   **Feature Engineering:**
    *   `FamilySize` is created from `SibSp` and `Parch`.
    *   `IsAlone` indicates if a passenger traveled alone.
    *   `Title` is extracted from `Name` and categorized.
*   **Column Dropping:** Irrelevant columns like `PassengerId`, `Name`, `Ticket`, and `Cabin` are removed.
*   **One-Hot Encoding:** Categorical features (`Sex`, `Embarked`, `Title`, `Pclass`) are converted into numerical format.

## Model Training and Evaluation
A Random Forest Classifier is used for predicting survival:
*   **Data Preparation:** Features (`X`) and target (`y`) are defined.
*   **Cross-Validation:** The model is evaluated using 5-fold cross-validation to assess generalization performance.
*   **Train-Test Split:** The dataset is split into training and testing sets (80/20 ratio).
*   **Model Training:** The Random Forest Classifier is trained on the training data.
*   **Prediction and Evaluation:**
    *   Predictions are made on the test set.
    *   Accuracy, classification report, and confusion matrix are displayed.
    *   Feature importances are visualized to identify the most influential factors in survival prediction.

## Key Findings
*   **Gender:** Females had a significantly higher survival rate than males.
*   **Passenger Class:** Passengers in higher classes (Pclass 1) had better survival chances.
*   **Age:** Children and younger adults generally had better survival rates, while older individuals had lower rates.
*   **Family Size:** Passengers traveling with small families (not alone) sometimes had better survival odds than those traveling alone or with very large families.
*   **Important Features:** `Fare`, `Sex`, `Age`, and `Title` were identified as the most impactful features for predicting survival.
