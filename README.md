# Bearing-Fault-Detection-using-Machine-Learning
This repository contains the implementation for an Industrial Data Analytics mini-project focused on early fault detection in bearings using machine learning. The goal is to classify the health status of bearings (healthy or faulty) based on sensor data, enhancing equipment reliability and enabling predictive maintenance.

 **Project Overview**
Course: ME 217 — Industrial Data Analytics

Team:

Rucha Jatin Prabhu (230003060)

Koyna Pandit (230003034)

Sri Varsha (230003074)

Project: CWRU Bearing Fault Detection — Team 3.1

 **Objectives**
 Accurately classify bearing conditions (Healthy, Ball Fault, Inner Fault, Outer Fault)
 Minimize false negatives (especially faults misclassified as “Healthy”)
 Achieve a weighted F1-score > 0.9 on the test dataset
 Provide feature insights and visualizations for interpretability

 **Dataset**
Source: Acceleration data from sensors near motor bearings

Samples: ~12,000

Collected with: HP motor at various loads and speeds

**Fault Types:**

Healthy

Ball Fault

Inner Fault

Outer Fault

Note: Original data provided in .xlsx files, combined and preprocessed into .csv format for analysis.

 **Methodology**
 Data Preprocessing
Label encoding using LabelEncoder

Feature extraction:

Time-domain: mean, variance, kurtosis, peak amplitude

Frequency-domain: FFT total energy, entropy, dominant frequency

Feature scaling using StandardScaler

 Feature Selection
Select top 7 features using SelectKBest with ANOVA F-value (f_classif)

 Model
Random Forest Classifier

Hyperparameter tuning using RandomizedSearchCV:

n_estimators: [100, 150]

max_depth: [5, 10]

min_samples_split: [2, 5]

 Evaluation
Train/test split (80%-20%)

Classification report with precision, recall, F1-score

**Weighted F1-score achieved: ~0.92**

Confusion matrix heatmap

 **Outputs**
 Classification Report: Precision, Recall, F1 per class

 Weighted F1-score: ~0.92

 Confusion Matrix: Visualized with heatmap

 Feature Importance: 
 Identify most impactful features
 
 Total Energy (FFT) — overall power in the frequency domain
 Signal Entropy (FFT) — randomness or unpredictability of the signal
 Dominant Frequency (FFT) — peak frequency component
 Kurtosis (time-domain) — sharpness or “peakedness” of the signal
 Peak Amplitude (time-domain) — maximum vibration level
 Variance (time-domain) — how spread out the signal is
 Mean (time-domain) — average signal level
