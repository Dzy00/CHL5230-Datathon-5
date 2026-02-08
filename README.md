# CHL5230 Datathon 5: Predicting human motion using deep learning models
Authors: Yi Qiao (Penny) Liu, Zhaoyu Ding, Kitty Chen

## Introduction
- This project investigates whether recurrent neural network (RNN) and long short-term memory (LSTM) models can recognize human activities using wearable sensor data, and examines which types of motion signals (sedentary vs dynamic) contribute more to activity recognition.

## Methods
- Data: 
  - Multi-dimensional time-series data collected from wearable sensors placed on ankles and arms, capturing sedentary and dynamic movements. 
  - 9 subjects with 200 sequences of 2-second activity inputs for each of 12 activities, and over 6000 sequences of idle activity. 
  - Train/Test split: 7 subjects for training, 2 subjects for testing.
  - 2 datasets were evaluated: a full dataset with all activities, and a reduced dataset excluding the idle activity.
- Models & Architecture: 
  - Recurrent Neural Network (RNN): 1 recurrent layer, 1 dropout layer, 2 fully connected linear layers. Activation function: ReLU. Loss function: cross-entropy. Optimizer: Adam.
  - Long Short-Term Memory (LSTM): 1 LSTM layer, 1 dropout layer, 2 fully connected linear layers. Activation function: ReLU. Loss function: cross-entropy. Optimizer: Adam.

## Results
- EDA:
  - Idle activity dominates the dataset, resulting in a strong class imbalance. Non-idle activities are relatively balanced.
  - Subject-level variability was observed, with some subjects contributing only a limited range of activities.
- Results:
  - RNN: training accuracy plateaued at 72%-76%, and validation accuracy plateaued at 69%-71%. Both training and validation accuracy decreased significantly after removing the Idle class.
  - LSTM: training accuracy ranged from 72-78%, and validation accuracy ranged from 68-72%. Performance dropped significantly after removing the Idle class.
- Key takeaways: LSTM outperformed RNN with modest improvements. Both models primarily learned to predict the idle class driven by class imbalance. Regularization had limited performance improvements for our models. Train accuracy was consistently higher than validation accuracy, indicating imperfect generalization. 
 
## Limitations
- small sample size, imbalanced data with more idle class than movements.

## Resources
- presentation slides: https://docs.google.com/presentation/d/1KArewyloyra6Q1EsnX8B8NO7uyiE6LOu0Vzedt7eZlE/edit?usp=sharing
