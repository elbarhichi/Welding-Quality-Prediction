# ML_CS_Project:  Welding Quality Prediction

A data-driven approach to predict the quality of steel welds by extracting, standardizing, and analyzing welding expertise, with potential applications across various industries.

## Table of Contents
- [Project Overview](#project-overview)
- [Preprocessing](#exploratory-data-analysis)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Evaluation Metrcis](#metrics)
- [Machine Learning Models](#modeling)
- [Conclusion](#conclusion)
- [References](#references)

## Project Overview

This project focuses on predicting weld quality using machine learning models, with a particular emphasis on predicting **Hardness**, **Ultimate Tensile Strength**, **Yield Strength**, **Elongation**, **Reduction of Area** of steel welds. The dataset includes chemical compositions and mechanical properties of weld deposits. Different supervised and semi-supervised models are explored to enhance prediction accuracy.


### Prerequisites
Make sure Python 3.10+ is installed.

```bash
pip install -r requirements.txt
```

### Cloning the Repository

```bash
git clone git@gitlab-student.centralesupelec.fr:yousra.yakhou/ml_cs_project.git
```

The dataset and detailed description are available here: ([WeldDB](https://www.phase-trans.msm.cam.ac.uk/map/data/materials/welddb-b.html)).

## Preprocessing 
The Preprocessing was conducted in the preprocessing.ipynb script and includes:
- Addressing missing values and creating handling strategies.
- Feature scaling and normalization.
- Feature engineering and selection.

## Exploratory Data Analysis 
Exploratory Data Analysis (EDA) was conducted in the eda.ipynb script and includes:
- Visualizing the distribution of different variables.
- Investigating correlations between chemical composition and mechanical properties.
- Basic statistical analysis, including mean, median, and standard deviation calculations for various features.

## Machine Learning Models

Machine learning models are implemented in the main.ipynb script.
- The supervised learning models employed include:
    -    SVR
    -   Random Forest

These models are used to predict the nine last columns (features).
- R² Score
- Root Mean Squared Error (MSE)


- The supervised learning models employed include:
    - XGboost

These models are used to predict xxxxxxxxxxxxxxx. The evaluation metrics used include:
- R² Score
- Root Mean Squared Error (MSE)


- The semi-supervised learning models employed include:
    - self-trainig random forest
    - self-trainig XGBoost

These semi-supervised learning models are mainly used to predict hardness. The evaluation metrics used include:
- R² Score
- Adjusted R² Score
- Root Mean Squared Error (RMSE)

The semi-supervised learning process is thoroughly detailed in the file `ML_PROJECT_ssl.ipynb`. 
The file `data_cleaning_for_ssl.ipynb` is used to generate the cleaned database `welddb/welddb_ssl.csv` for semi-supervised learning.
The final predictions of hardness have been saved in the file `welddb/hardness_predictions.csv`.


## Conclusion

This project demonstrates how machine learning models can be used to predict important weld properties based on chemical composition and welding parameters. The models can help optimize welding processes by revealing how various factors influence mechanical strength. Future improvements could focus on:
- Fine-tuning hyperparameters.
- Exploring advanced models like XGBoost or Neural Networks.

## References
- [1]
- [2]