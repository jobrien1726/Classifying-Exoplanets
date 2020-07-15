# Exoplanet Exploration: Classifying Exoplanets

## Project Overview

![](images/exoplanets.png)

The goal of this project was to compare/contrast the efficiency and accuracy of various Machine Learning Classification models. Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system. Four machine learning models were used to classify candidate exoplanets from the raw [dataset](data/exoplanet_data.csv) provided by telescope: a Deep Learning neural network, a K Nearest Neighbors model, a Support Vector Machine, and a Random Forest. 

## Technologies Used

- Python
- Pandas
- Matplotlib
- Scikit-learn
- Tensorflow

## Classification Models

- [Deep Learning](deep_learning.ipynb)
- [K Nearest Neighbors](knn.ipynb)
- [Support Vector Machine](svm.ipynb)
- [Random Forest](random_forest.ipynb)

## Method

- Feature Selection
- Train/Test Split
- Scale the data using MinMaxScaler
- Train the Model (using each of the Classification Models)
- GridSearchCV to tune Model parameters
- Confusion Matrix

## Model Performance/Analysis

It was anticipated that the Deep Learning model have the greatest percent accuracy in classifying exoplanets, but it turned out that the Support Vector Machine model was slightly more accurate, with an accuracy of .883 vs the Deep Learning model's .881.

The datset had a very large number of features. The Random Forest model was tested first, and the feature_importance function was used to narrow down the number of features. However, they all seemed to have very low numbers with regard to importance. It was difficult to decide which subset was significantly more relevant than the others. Those that had an importance > .05 were chosen, which were the top five most important features. The steps of creating a train test split and scaling the data were repeated after fine tuning the feature selection. Ultimately, it was the very first Random Forest model trained that had the highest accuracy (.87), before the hypertuning, which was surprising. By comparison, the model trained using the smaller subset of "most important" features had an accuracy of .85.

With the K Nearest Neighbors model, when plotting the test accuracy score with regard to number of nearest neighbors, it was estimated that 13 nearest neighbors would provide the best model for classifying the data. This returned an accuracy score of .816. However, after hypertuning the model,it was found that 9 was actually the most appopriate number of neighbors to use, yielding an accuracy of .841.

Each of the models used had a fairly high accuracy score, they were all greater than .80. With an accuracy score of .883 and .881, respectively, I think both the Support Vector Machine model and the Deep Learning model would be good enough to predict new exoplanets accurately most of the time. A better method for narrowing down the subset of features to only the most important ones would most likely yeild more accurate results and they would take far less time to train/hypertune. Training this amount of data and then running through all hypertune scenarios was certainly pretty time consuming. 
