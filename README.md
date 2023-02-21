# Multivariate time series classification with deep learning techniques

## Introduction

This repo contains our work regarding the [2nd challenge](https://codalab.lisn.upsaclay.fr/competitions/9056#learn_the_details) of the Artificial Neural Networks and Deep Learning course at Politecnico di Milano. The goal of this challenge is to model a neural network able to classify time series characterized by sequences of 36 samples, 6 features and 12 possible labels.

Final team rank position: 13th out of 200 teams.

The detailed report of our work can be found [here](deliveries/report.pdf).

## Data preprocessing

The source of the dataset is unknown, thus no domain knowledge could be applied. 
We employed different techniques to improve our result by exploiting at most our data:
- **Data Standardization**: we used RobustSCaler, a scaler robust to outliers, to improve stability and performance of our model

- **Time Series Augmentation**: we used the library [tsaug](https://tsaug.readthedocs.io/en/stable/) and experimented with various types of augmentation

- **Oversampling and Undersampling**: Our dataset was imbalanced with a class having 777 samples and another one only 34. To make up for this imbalance we applied oversampling and undersampling techniques, with oversampling giving the best result.

- **Sliding Windows**: Under the assumption that the training dataset contained chronologically ordered samples, as a form of further augmentation, we developed an algorithm to build sliding window with random sampling of validation and test set

## Models

We experimented with various models, including LSTM, ResNet, Transformer, BiLSTM and 1D Convolution.

Among these, the model that performed best was the following 1D Convolution model.

<img src="https://user-images.githubusercontent.com/79714834/220335195-a4cbdcd2-abb2-4c8e-82d2-f25c0ebd9a89.png" width="400">


## Results

Our best model reached an accuracy of 0.7494 and we were able to improve the F1 score on the most problematic classes, scoring 5th best in class 5, 6th in class 0, 9th in class 4 and 10th in class 3.
