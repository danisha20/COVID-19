# COVID19 Latin America Prediction and Analysis

## Authors

Project by 

Daniela A. Gomez-Cravioto and

Ramon E. Diaz-Ramos

## Introduction

This study presents the use of machine learning techniques for projecting COVID-19 infections and deaths in Mexico. The methods compared are linear, polynomial, and generalized logistic regression models to describe the growth of COVID-19 incidents in Mexico. Additionally, we use machine learning and time-series techniques to identify features importance and perform forecasting for daily cases and fatalities.The data analysis and modeling conducted in this research is based on the publicly available data sets from the Resource Center at John Hopkins University of Medicine. Additional features were added to this dataset as an effort to understand its effects in the number of daily cases: this includes mobility rates obtained from Google's Mobility Reports and climate variables obtained from weather online.

## Background

As referenced by the World Health Organization, the first case of COVID-19 (also known as 2019 Novel Coronavirus) was confirmed in Wuhan, China on December 31, 2019. Even though the disease is now successfully contained in China, it has spread all over the world. On May 21th there had been over 5,102,424 confirmed cases which resulted in more than 332,924 fatalities around the world. The pandemic is severe and it continues to affect billions of people.

## Motivation

The motivation of this study is to contribute to the knowledge necessary to fight the disease and characterize its course in Mexico, with the attempt to display more preparedness and promote more logical actions by the policy makers and the population in general.

## Objectives

1. To identify which function adjusts the best to the infected population growth (COVID-19 cases).
2. To determine the feature importance of climate and mobility.
3. To compare the results of a traditional time series statistical model with a modern approach in machine learning.

In this project we will be using the number of confirmed cases and the number of deaths as target variables.

## Evaluation Metrics

To measure the performance of each of the models, the following metrics were computed: 
- The Root Mean Squared Error (RMSE) is obtained in order to measure how close the fitted values are to the real values and 
- The Akaike information criterion (AIC) is used to obtain the estimated likelihood to predict a model, and to test how well the model fits the data without overfitting it.

Root Mean Squared Error (RMSE):
\begin{equation}
     \sqrt{\frac{1}{n}\sum_{i=1}^n (Prediction_i - Truth_i)^2}
\end{equation}


$$ AIC= N*log(MSE) + 2*(n), $$

where,

N = number of observations,\
MSE = Mean Squared Error, and\
n = Number of independently adjusted parameters within the model.

### Cross-Validation

When dealing with time series data, traditional cross-validation (like k-fold) should not be used for two reasons:

- Temporal Dependencies

- Arbitrary Choice of Test Set

https://towardsdatascience.com/time-series-nested-cross-validation-76adba623eb9


In this study, we utilized the hold-out cross-validation by splitting the dataset into a train and validate set. 
We used 80% for testing and the last 20% of the time-series dates for validating.
