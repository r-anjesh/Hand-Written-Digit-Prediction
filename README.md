<!-- Project Title -->
<h1 align="center">Handwritten Digit Recognition</h1>

<!-- Project Description -->
<p align="center">
  Recognizing handwritten digits using Random Forest Classifier in Python.
</p>

<!-- Badges -->
<p align="center">
  <img alt="GitHub repo size" src="https://img.shields.io/github/repo-size/r-anjesh/Python-Development">
  <img alt="GitHub issues" src="https://img.shields.io/github/issues/r-anjesh/Python-Development">
  <img alt="GitHub pull requests" src="https://img.shields.io/github/issues-pr/r-anjesh/Python-Development">
</p>

<!-- Table of Contents -->
## Table of Contents
- [Overview](#overview)
- [Code Explanation](#code-explanation)
- [Project Setup](#project-setup)
- [Usage](#usage)
- [Next Steps](#next-steps)
- [Credits](#credits)
- [License](#license)

<!-- Overview -->
## Overview
This project demonstrates handwritten digit recognition using the Random Forest Classifier from scikit-learn. It utilizes the MNIST-like digits dataset provided by scikit-learn (`load_digits`).

<!-- Code Explanation -->
## Code Explanation

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.datasets import load_digits
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import confusion_matrix

# Load the digits dataset
df = load_digits()

# Display sample images from the dataset
_, axes = plt.subplots(nrows=1, ncols=4, figsize=(10, 3))
for ax, image, label in zip(axes, df.images, df.target):
    ax.set_axis_off()
    ax.imshow(image, cmap=plt.cm.gray_r, interpolation='nearest')
    ax.set_title(f'Training: {label}')

# Reshape data for training
n_samples = len(df.images)
data = df.images.reshape((n_samples, -1))

# Normalize the data
data = data / 16.0

# Split data into training and testing sets
X_train, X_test, Y_train, Y_test = train_test_split(data, df.target, test_size=0.3)

# Train a Random Forest Classifier
rf = RandomForestClassifier()
rf.fit(X_train, Y_train)

# Predict using the trained model
y_pred = rf.predict(X_test)

# Evaluate the model
cm = confusion_matrix(Y_test, y_pred)
print("Confusion Matrix:")
print(cm)

