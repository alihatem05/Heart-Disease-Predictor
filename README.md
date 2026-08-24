# Heart Disease Data Mining

A data mining and machine learning project for predicting the presence of heart disease from patient health data.

The project covers data preprocessing, exploratory analysis, multiple classification algorithms, and model comparison using the same dataset and train/test split.

## Features

* Data cleaning and preprocessing
* Missing-value handling
* Duplicate removal
* Outlier analysis using the IQR method
* One-hot encoding of categorical features
* Exploratory data analysis and visualizations
* Heart disease classification using:

  * Logistic Regression
  * Random Forest
  * Decision Tree
  * K-Nearest Neighbors (KNN)
  * Naive Bayes
* Model evaluation using:

  * Accuracy
  * Precision
  * Recall
  * F1-Score
  * Error rate
* Confusion matrices and feature-importance visualizations
* Automatic comparison of all models

## Dataset

The project uses `heart.csv`, containing patient health attributes and a binary `target` indicating whether heart disease is present.

The dataset contains features such as:

* Age
* Sex
* Chest pain type
* Resting blood pressure
* Cholesterol
* Maximum heart rate
* Exercise-induced angina
* ST depression
* Slope
* Number of major vessels
* Thalassemia

## Project Structure

```text
DATA-MINING/
│
├── heart.csv
├── main.py
├── heart_preprocessing.py
├── heart_analysis.py
│
├── model_logistic_regression.py
├── model_random_forest.py
├── model_decision_tree.py
├── model_knn.py
├── model_naive_bayes.py
│
└── outputs/
    ├── processed_data.csv
    ├── X_train.csv
    ├── X_test.csv
    ├── y_train.csv
    ├── y_test.csv
    ├── models_comparison.csv
    ├── project_observations.csv
    ├── outlier_summary.csv
    ├── prediction files
    └── plots/
```

## How It Works

### 1. Preprocessing

`heart_preprocessing.py`:

* Loads the dataset
* Removes duplicate rows
* Handles missing numerical values using the median
* Handles missing categorical values using the mode
* Detects numerical outliers using IQR
* Generates exploratory plots
* One-hot encodes categorical features
* Splits the data into 80% training and 20% testing sets
* Saves the processed datasets under `outputs/`

### 2. Exploratory Analysis

`heart_analysis.py` generates visualizations and basic observations about the relationship between patient characteristics and heart disease, including age, cholesterol, blood pressure, chest pain, sex, and exercise-induced angina.

### 3. Model Training

Each model has its own Python script and evaluates its predictions on the test data.

The models used are:

| Model               | Purpose                         |
| ------------------- | ------------------------------- |
| Logistic Regression | Linear classification baseline  |
| Decision Tree       | Rule-based classification       |
| Random Forest       | Ensemble of decision trees      |
| KNN                 | Similarity-based classification |
| Naive Bayes         | Probabilistic classification    |

Some models also use feature selection or scaling as part of their pipeline. The Naive Bayes implementation performs its own preprocessing directly from `heart.csv`.

### 4. Model Comparison

`model_comparison.py` collects the predictions from all models and compares their performance using accuracy, precision, recall, F1-score, and error rate.

The current stored results are:

| Model               | Accuracy | Precision | Recall | F1-Score |
| ------------------- | -------: | --------: | -----: | -------: |
| Logistic Regression |   91.80% |    91.77% | 91.86% |   91.79% |
| Decision Tree       |   90.16% |    90.14% | 90.14% |   90.14% |
| Naive Bayes         |   90.16% |    90.22% | 90.30% |   90.16% |
| KNN                 |   88.52% |    88.49% | 88.58% |   88.51% |
| Random Forest       |   86.89% |    86.94% | 87.02% |   86.88% |

Based on the generated results, Logistic Regression achieved the highest accuracy among the tested models.

## Requirements

Python 3.x with the following libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Running the Project

Run the entire pipeline with:

```bash
python main.py
```

This automatically runs the preprocessing, model training, analysis, and model comparison scripts in sequence.

The generated datasets, predictions, metrics, and visualizations are saved in the `outputs/` directory.

## Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn

## Purpose

This project was developed as a practical application of data mining and machine learning concepts, covering the complete workflow from raw data preprocessing and analysis to classification and model evaluation.
