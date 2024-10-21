# Radial-Basis-Function-RBF-Neural-Network

## Overview

This project implements a **Radial Basis Function (RBF) Neural Network** using **Gaussian kernel functions**. The primary goal is to compare the performance of the RBF network as we vary the **spread parameter** and use different methods for selecting centers. The project consists of two main parts: using all training points as centers and using only 150 centers, selected randomly and via **K-Means** clustering.

## Problem Statement

Designing an RBF Neural Network with the following steps:

### Part 1: 
To design the RBF network using **all training points** as the centers of the Gaussian kernel functions. The **spread parameter** is kept constant for all kernel functions. The performance of the model is evaluated using **mean square error (MSE)**, and the **spread parameter** is varied to observe its effect on the network’s performance.

### Part 2:
To design the RBF network using **150 centers** and compare two approaches to select these centers:
  - **Random selection** of centers from the input data.
  - **K-Means algorithm** to find the optimal centers.
  
The spread parameter is kept constant for both methods, and the performance is again evaluated using **MSE**. The results of these designs are compared to the network designed in **Part 1**.

## Methodology

### RBF Network with All Training Points as Centers
- **Gaussian Kernel Function**: Implemented using a Gaussian basis function with a constant spread for all points.
- **Centers**: All points from the training data are used as the centers.
- **Spread Parameter**: Varied across different experiments to assess its effect on performance.
- **Performance Metric**: Mean square error (MSE) is calculated to evaluate the performance.

### RBF Network with 150 Centers
- **Random Centers**: 150 centers are randomly chosen from the training data.
- **K-Means Centers**: The **K-Means clustering algorithm** (from `sklearn.cluster.KMeans`) is used to select 150 centers.
- **Spread Parameter**: Fixed across all kernel functions.
- **Comparison**: MSE for both approaches (random centers and K-Means) is compared to the network with all training points as centers.

## Implementation Details

- **Gaussian Kernel Function**: The basis function used in the RBF network is a Gaussian function with the form:
  \[
  \phi(x) = \exp\left(-\frac{||x - c||^2}{2\sigma^2}\right)
  \]
  where \(c\) is the center, and \(\sigma\) is the spread parameter.
  
- **Spread Parameter**: Varying the spread parameter \(\sigma\) alters the width of the Gaussian functions and is critical to network performance. 

- **K-Means Clustering**: Centers are determined using the K-Means algorithm to ensure the centers are well-representative of the data distribution.

- **Mean Square Error (MSE)**: Used as the performance metric for comparing the networks. MSE is calculated as:
  \[
  MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
  \]
  where \(y_i\) is the actual value and \(\hat{y}_i\) is the predicted value.
