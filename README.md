# Hospital Readmission Prediction using Neural Networks

## Overview

This project focuses on predicting whether a patient will be readmitted within 30 days using a healthcare dataset. The workflow includes data cleaning, building a neural network from scratch using NumPy, and evaluating the model with cost-sensitive metrics.

This assignment follows a real-world scenario where data is messy and decisions have business impact.

---

## Dataset

Dataset used: hospital_records.csv

The dataset contains:
- Patient demographic details
- Medical information
- Target variable indicating readmission

---

## Project Workflow

### 1. Data Audit

We performed a complete data quality check:
- Checked missing values
- Inspected data types
- Identified inconsistent or invalid values
- Reviewed unique values per column

---

### 2. Data Cleaning

Cleaning steps applied:

- Numerical columns:
  - Missing values filled using median
  - Negative values corrected

- Categorical columns:
  - Missing values filled using mode

- Encoding:
  - Converted categorical variables using one-hot encoding

Result:
A clean dataset ready for modeling

---

### 3. Feature Preparation

- Split dataset into features (X) and target (y)
- Applied train-test split (80 percent training, 20 percent testing)
- Standardized features using StandardScaler

---

### 4. Neural Network Design

A simple 3-layer neural network was built from scratch using NumPy.

Architecture:
- Input layer: number of features
- Hidden layer: 16 neurons
- Output layer: 1 neuron

Activation function:
- Sigmoid

---

### 5. Training Process

Training includes:
- Forward propagation
- Binary cross entropy loss calculation
- Backpropagation
- Gradient descent weight updates

Loss is tracked across epochs and plotted.

---

### 6. Model Evaluation

Primary metric used:
- F1 Score

Reason:
- Dataset may be imbalanced
- F1 score balances precision and recall

Also evaluated:
- Confusion Matrix
- Classification Report

---

### 7. Baseline Comparison

Compared neural network with:
- Logistic Regression (sklearn)

Purpose:
- Validate whether custom model performs reasonably

---

### 8. Cost-Sensitive Optimization

Real-world scenario:
- Missing a high-risk patient is very costly

Cost assumptions:
- False Negative = 10
- False Positive = 1

We tested different thresholds and selected the one that minimizes total cost.

---

## Theory

### Neural Networks

Neural networks are models that learn patterns using layers of neurons. Each neuron applies a transformation to input data and passes it forward.

---

### Forward Propagation

Steps:
1. Input data enters the network
2. Multiply with weights
3. Add bias
4. Apply activation function
5. Pass to next layer

---

### Backpropagation

Backpropagation updates weights by:
- Calculating error
- Finding gradients
- Adjusting weights to reduce loss

---

### Sigmoid Activation Function

Formula:
1 / (1 + e^(-x))

Properties:
- Output between 0 and 1
- Suitable for probability prediction

---

### Binary Cross Entropy Loss

Used for classification problems.

It penalizes incorrect predictions and improves probability estimates.

---

### Vanishing Gradient Problem

Occurs when gradients become very small, slowing down learning in deep networks.

---

### Why F1 Score Instead of Accuracy

Accuracy can be misleading when classes are imbalanced.

F1 Score considers:
- Precision
- Recall

Better suited for healthcare predictions.

---

### Cost-Sensitive Learning

In real-world applications:
- Not all errors have equal importance

Healthcare example:
- Missing a risky patient is much worse than a false alarm

---

## Key Learnings

- Real-world data is often messy
- Data cleaning is critical before modeling
- Neural networks can be implemented from scratch
- Evaluation metrics must reflect real-world impact
- Cost-sensitive decisions improve practical usefulness

