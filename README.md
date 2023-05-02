# Lithium-Ion Battery State of Health (SoH) Prediction

This repository contains notebooks demonstrating the implementation of five different machine learning models for predicting the SoH of LiNiMnCo/Graphite cells based on various features. The notebooks are as follows:

- `lasso_regression.ipynb`: lasso regression model
- `random_forest.ipynb`: random forest model
- `ridge_regression.ipynb`: ridge regression model
- `gaussian_regression.ipynb`: gaussian regression model
- `deep_learning.ipynb`: deep learning model using Keras

## Battery Description

The LiNiMnCo/Graphite cells used in this project are cylindrical INR 18650-20R batteries with a capacity rating of 2000 mAh, and a cell chemistry of LiNiMnCo/Graphite. The batteries have a weight of 45 g, diameter of 18.33 mm ± 0.07 mm, and length of 64.85 mm ± 0.15 mm. Tab length is not included in the dimensions.

## Data Description

The dataset used in this project is sourced from the following paper:

B. Thacker et al., "Machine learning for predictive maintenance of battery systems: A review," Nature Machine Intelligence, vol. 3, pp. 23-35, 2021. DOI: 10.1038/s42256-021-00312-3.

The `soh_lithium_ion.csv` file in the root directory contains the dataset used in this project. It includes features such as voltage, current, temperature, and discharge capacity, as well as the corresponding SoH values.

## Model Performance

Each notebook includes the following performance metrics for its respective model:

- Best hyperparameters
- Best score
- Mean squared error (MSE)

## Importance

Lithium-ion batteries are widely used in various applications, including portable electronic devices, electric vehicles, and renewable energy systems. Understanding the state of health of batteries is crucial for ensuring their safe and reliable operation, as well as for improving their performance and longevity.

The specific LiNiMnCo/Graphite cells studied in this project are commonly used in portable electronic devices and electric vehicles, making accurate SoH prediction essential for maintaining their performance and reliability. Accurately predicting the SoH of batteries using machine learning models can enable proactive maintenance and avoid catastrophic failure.

## Battery Specifications

| Battery (Parameters) | Specifications (Value) |
| -------------------- | ---------------------- |
| Capacity Rating      | 2000 mAh                |
| Cell Chemistry       | LiNiMnCo/Graphite       |
| Weight               | 45 g                    |
| Diameter             | 18.33 mm ± 0.07 mm      |
| Length               | 64.85 mm ± 0.15 mm      |

## Results and Conclusion

TBD
