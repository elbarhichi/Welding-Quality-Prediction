# Welding Quality Prediction Project

## Table of Contents
- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Preprocessing](#preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Modeling and Evaluation Metrics](#modeling-and-evaluation-metrics)
- [Conclusion](#conclusion)
- [References](#references)

## Project Overview

This project leverages machine learning techniques to enhance the assessment of welding quality by predicting key mechanical properties. Our approach addresses the limitations of traditional methods reliant on expert judgment, which can be inconsistent and subjective. Using both supervised and semi-supervised learning, we focused on critical variables influencing weld quality, with applications in industries like wind turbine manufacturing where welding quality impacts safety and performance. 

Our study aims to create a data-driven model that ensures consistent and reliable weld assessments, helping to optimize industrial processes by minimizing dependency on expert knowledge.

## Prerequisites

Ensure that Python 3.10+ is installed on your system.

To install the necessary dependencies, run:
```bash
pip install -r requirements.txt
```

### Cloning the Repository

Clone the repository using the command below:
```bash
git clone git@github.com:elbarhichi/Welding-Quality-Prediction.git
```

The dataset and additional details can be found at [WeldDB](https://www.phase-trans.msm.cam.ac.uk/map/data/materials/welddb-b.html).

## Preprocessing

The dataset, containing 1652 rows and 44 columns, was prepared through rigorous preprocessing steps, which included:

- **Handling Missing Values**: Non-numeric data entries and missing values were identified and managed. Missing values were replaced using iterative imputation to maintain data integrity.
- **Data Cleaning and Standardization**:
  - **Special Characters**: Non-standard characters were removed or converted to maintain uniformity.
  - **Unit Conversion**: Values with units embedded in text were extracted and standardized.
- **Feature Engineering**:
  - Created a new `Power` column as the product of Voltage and Current, capturing the interaction between these variables.
  - Categorical variables were encoded, and ranges were averaged to provide consistent numeric values.
- **Scaling and Normalization**: To ensure comparability, variables with differing units or magnitudes were normalized. For example, elemental concentrations were converted from ppm to weight percentages (%).

This preprocessing step provided a clean, consistent dataset, enabling more effective model training.

## Exploratory Data Analysis

EDA provided insights into data distribution and feature relationships, crucial for understanding the underlying patterns in the dataset. Key analyses included:

- **Correlation Analysis**: A heatmap highlighted relationships between mechanical properties and chemical compositions. For example, yield strength was positively correlated with ultimate tensile strength.
- **Data Visualizations**:
  - **Heatmap**: Displayed correlations to help identify redundant or highly related variables.
  - **Histograms**: Illustrated distributions of key mechanical properties like yield strength and elongation, showing variability within the dataset.

EDA guided feature selection, informed model choices, and highlighted essential data trends.

## Modeling and Evaluation Metrics

The modeling process utilized both supervised and semi-supervised learning techniques to predict weld quality effectively:

- **Supervised Learning**:
  - **PCA (Principal Component Analysis)**: Reduced dimensionality, retaining the most significant features for models, including Gradient Boosting and Random Forest.
  - **XGBoost (Without PCA)**: Directly utilized all features, providing better predictive accuracy than PCA-based models for some targets.
- **Semi-Supervised Learning**: For targets with substantial missing data (e.g., hardness with 91.6% missing), we used self-training with XGBoost and Random Forest, iteratively labeling missing data for improved predictions.

### Evaluation Metrics

To assess model performance, we employed several metrics:

- **Mean Squared Error (MSE)** and **Root Mean Squared Error (RMSE)**: Captured average prediction errors, with RMSE in the target variable’s unit.
- **Mean Absolute Error (MAE)**: Quantified average absolute errors, less influenced by outliers than MSE.
- **R-Squared (R²) and Adjusted R²**: Evaluated model fit, with values closer to 1 indicating better predictions.
- **Cross-Validation (CV)**: Ensured model robustness and generalization across multiple data splits.

## Conclusion

The project demonstrated that machine learning can effectively predict weld quality, enhancing reliability over traditional expert-driven methods. Supervised learning, particularly using PCA with different models and XGBoost without PCA, provided strong performance for most targets, while self-training approaches showed improvement for targets with high missing data. These findings support a scalable solution applicable to other industries requiring consistent quality assessments.

Future work may explore additional semi-supervised methods like label propagation or integrate domain-specific constraints for enhanced model interpretability and performance.

## References

1. Theo Boutin et al. "Classification des paramètres procédés de soudage par analyse expérimentale et apprentissage automatique." *25e Congrès Français de Mécanique*, 2022.
2. Olivier Chapelle, Bernhard Schölkopf, and Alexander Zien. *Semi-supervised learning*. MIT Press, 2006.
3. T. Cool, H.K.D.H. Bhadeshia, and D.J.C. MacKay. "The yield and ultimate tensile strength of steel welds." *Materials Science and Engineering: A*, 1997.
4. Aurélien Géron. *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow*. O'Reilly Media, 2019.
5. ISO 15614-1:2017. *Specification and qualification of welding procedures for metallic materials*.
