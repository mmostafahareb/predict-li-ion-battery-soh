# Lithium-Ion Battery State of Health (SoH) Prediction
The goal for this project is to try predicting the State of Health of LiNiMnCo/Graphite cells for the ELE522 course.
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

### Model Comparison

The following table summarizes the performance of the five models on the SoH prediction task:

| Model             | Best Hyperparameters                                        | Best Score        | MSE on Test Set   |
|-------------------|-------------------------------------------------------------|-------------------|-------------------|
| Ridge Regression  | {'alpha': 1}                                                | 7.010986702753861e-07 | 5.61465748160752e-07 |
| Deep Learning     | -                                                           | -                 | 0.3512989889333423 |
| Random Forest     | {'max_depth': None, 'min_samples_leaf': 2, 'min_samples_split': 2, 'n_estimators': 100} | 1.5780307468199424e-05 | 3.7850288454312208e-06 |
| Gaussian          | {'alpha': 0.1, 'kernel__length_scale': 0.01}                | 0.00014711829093236537 | 0.00016082866805543846 |
| Lasso Regression  | {'alpha': 0.01}                                             | 3.4181754323117102e-06 | 3.5052655927481366e-06 |

The models are ranked in order of best to worst based on their performance on the test set.

### Fitting

Looking at the results of the Ridge Regression model, we can see that the model is not overfitting. The learning and validation curves are included below:

![Ridge Regression Learning Curve](/img/learning_curve.png)

![Ridge Regression Validation Curve](/img/validation_curve.png)

### Feature Engineering

By examining the coefficients of the Lasso Regression model, we can see that the two most important features for predicting SoH are `Discharge_Q` (major predictor) and `Capacity dV CCCT` (minor predictor). 

`Discharge_Q` represents the discharge capacity of the battery, or the amount of charge that can be extracted from the battery under certain conditions. As the battery ages, its capacity decreases, leading to a decrease in SoH. Therefore, it makes sense that this feature would be a major predictor of SoH.

`Capacity dV CCCT` represents the change in voltage during a discharge cycle, and is used as a measure of capacity fade. As the battery ages, its capacity decreases, leading to a decrease in voltage during discharge. Therefore, it also makes sense that this feature would be a predictor of SoH.

The comparison chart between the features is included below:

![Feature Comparison Chart](/img/features.png)

The high importance of these features may be due to the fact that they are directly related to the capacity and performance of the battery. The discharge capacity is a direct measure of the battery's energy storage capacity, while the voltage change during cycling is related to the electrochemical reactions occurring in the battery. Understanding the relationship between these features and SoH can help in the development of better battery management systems and predictive maintenance strategies.
