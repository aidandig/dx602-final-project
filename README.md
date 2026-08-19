# Retail Customer Segmentation Analysis

# Project Overview

This project focuses on understanding machine learning model development, testing, and evaluating performance on the UCI Body Fat data set.

## Python Packages Used

- **Data Manipulation & Statistical Analysis:** pandas, scipy.stats, math
- **Data Visualization:** matplotlib
- **Machine Learning:** scikit-learn

# Data

This project utilizes UC Irvine Machine Learning Repository's [Body Fat](https://www.openml.org/search?type=data&status=active&id=560&sort=runs) data set. It lists estimates of the percentage of body fat determined by underwater weighing and various body circumference measurements for 252 men.

## Exploratory Data Analysis

Identified 5 key correlations with the target, body fat percentage:
  - Body Density
  - Abdomen Circumference
  - Chest Circumference
  - Hip Circumference
  - Hip Circumference
  - Weight

Identified highest correlated features:
  - Hip Circumference & Weight
  - Chest Circumference & Abdomen Circumference
  - Thigh Circumference & Hip Circumference
  - Knee Circumference & Weight
  - Neck Circumference & Weight

## Model Development

Developed Random Forest Regression, Elastic Net, and Support Vector Regression models with a 80/20 train-test split.
  - Random Forest Regression had the lowest L1 and L2 losses out of the 3 models, making it the most accurate model with a test R-squared score of 0.86.
  - Elastic Net had the second lowest L1 and L2 losses out of the 3 models, making it the second most accurate model with a test R-squared score of 0.84.
  - Support Vector Regressor had the highest L1 and L2 losses out of the 3 models, making it the third most accurate model with a test R-squared score of 0.80.

The overall intention behind the different models were to test out which algorithms perform the best for this dataset and further build model development and analysis skills.

## Exploring Overfitting

Utilizing 5-fold cross validations on all of the models, the Support Vector Regressor experienced the most overfitting with an L2 loss of 11.22 body fat percentage.

## Comparing Models

Applied StandardScaler to data before model training to examine the differences in machine learning model algorithm accuracy.

Comparing all models:
  - Ridge Regression: Performed better on the test data. This model has the second lowest L2 loss on the test data.
  - Linear Regression: Performed better on the test data. Out of all of the models, Linear Regression has the lowest L2 loss on the test data.
  - Lasso: Performed better on the test data. This model has the third lowest L2 loss on the test data.
  - Random Forest Regressor: Performed worse on the test data. This model has a significantly higher L2 loss than the first 3 models (Ridge, Linear Regression, Lasso). Overall, it had the fourth highest L2 loss for both the train and test data.
  - Elastic Net: Performed worse on the test data. This model has a significantly higher L2 loss than the first 3 models (Ridge, Linear Regression, Lasso). Overall, it had the fifth highest L2 loss for both the train and test data.
  - Support Vector Regressor: Performed worse on the test data. This model has a significantly higher L2 loss than the first 3 models (Ridge, Linear Regression, Lasso). Overall, it had the highest L2 loss for both the train and test data.
# Results and evaluation

Ultimately, the linear regression (ordinary least squares) model which was preprocessed by standardizing the data and created through a pipeline was the best model out of all the models I built for the body fat data set. The model had the lowest L2 loss in both the training and testing data which means that there were smaller errors with the predictions overall. The big difference that separates the the six models into two distinct groupings is that the linear regression, ridge regression, and lasso models used standardized data rather than the raw data. By standardizing the data first, you ensure that the mean is 0 and the standard deviation is 1 which ensures that there is no major dominating feature for the predictions. After standardization, it reduced the overall losses (L1 and L2) significantly compared to the models that did not used the standardized version of the body fat dataset. The underlying relationships with the target (body fat percentage) is best captured by a simpler model, the linear regression model. Finally, using the R2 score to measure the model's fit was another factor I considered when determining the best model. The linear regression model explained the highest proportion of the variance, fitting the data the best. The combination of a high R2 score and low loss scores means that the model has highly accurate predictions while generalizing well for the unseen data (test data split).

# Citation
Johnson, Roger W. (2014). Body Fat [Dataset]. UCI Machine Learning Repository. [https://www.openml.org/search?type=data&status=active&id=560&sort=runs](https://www.openml.org/search?type=data&status=active&id=560&sort=runs).

# License

The data set from this project is licensed under a [Creative Commons Attribution 4.0 International (CC BY 4.0) license](https://creativecommons.org/licenses/by/4.0/legalcode). It allows for the sharing and adaptation of the datasets for any purpose, provided that the appropriate credit is given.
