# ML_CS_Project: Welding Quality Prediction

A data-driven approach to predict the quality of steel welds by extracting, standardizing, and analyzing welding expertise, with potential applications across various industries.

## Table of Contents
- [Project Overview](#project-overview)
- [Preprocessing](#preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Modeling and Evaluation Metrics](#modeling-and-evaluation-metrics)
- [Conclusion](#conclusion)
- [References](#references)

## Project Overview

This project focuses on predicting weld quality using machine learning models, emphasizing **Hardness**, **Ultimate Tensile Strength**, **Yield Strength**, **Elongation**, and **Reduction of Area** of steel welds. The dataset includes chemical compositions and mechanical properties of weld deposits. The project explored both supervised and semi-supervised learning approaches, using Principal Component Analysis (PCA) for dimensionality reduction and models such as XGBoost and Random Forest. Semi-supervised learning methods, like self-training, were applied to improve predictions for targets with high missing values.

### Prerequisites
Make sure Python 3.10+ is installed.

```bash
pip install -r requirements.txt
```

### Cloning the Repository

```bash
git clone git@gitlab-student.centralesupelec.fr:yousra.yakhou/ml_cs_project.git
```

The dataset and detailed description are available here: [WeldDB](https://www.phase-trans.msm.cam.ac.uk/map/data/materials/welddb-b.html).

## Preprocessing 
The preprocessing steps were implemented in the `preprocessing.ipynb` script and include:
- Handling missing values using iterative imputation.
- Addressing non-numeric data, such as special characters and unit conversions.
- Feature scaling and normalization, especially converting measurements from ppm to weight percentage.
- Feature engineering, such as creating a Power column from Voltage and Current.

## Exploratory Data Analysis
Exploratory Data Analysis (EDA) was conducted in the `eda.ipynb` script and includes:
- Generating correlation matrices to study relationships between mechanical and chemical properties.
- Producing visualizations, such as heatmaps and histograms, to understand the distribution of key features.

## Modeling and Evaluation Metrics

Machine learning models are implemented in the `main.ipynb` script.

### Supervised Learning Models:
- **Principal Component Analysis (PCA)** followed by models such as:
  - Linear Regression, Ridge Regression, Lasso Regression, ElasticNet, Decision Trees, Random Forest, Gradient Boosting, and Support Vector Regressor (SVR).

PCA was used for dimensionality reduction and helped improve model performance for certain targets. XGBoost without PCA achieved the highest accuracy across many variables.

### Semi-Supervised Learning Models:
- **Self-Training** was applied using Random Forest and XGBoost to handle targets with limited labeled data, primarily predicting hardness.

### Evaluation Metrics:
- R² Score
- Adjusted R² Score
- Root Mean Squared Error (RMSE)

## Conclusion

This project demonstrated how machine learning models, including semi-supervised approaches, can predict key weld quality metrics like hardness and tensile strength. The XGBoost model, especially when applied without PCA, outperformed others. Future work could explore deep learning approaches and refine semi-supervised learning methods for further improvement.

## References
1. Theo Boutin et al. “Classification des paramètres procédé de soudage par analyse expérimentale et apprentissage automatique,” 25e Congrès Français de Mécanique, 2022.
2. T. Cool, H.K.D.H. Bhadeshia, and D.J.C. MacKay. “The yield and ultimate tensile strength of steel welds,” Materials Science and Engineering: A, 1997.

