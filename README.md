# Deep-Learning-with-GRU-Based-Monthly-Retail-Sales-Forecasting-for-Business-Decision-Support
This study applies deep learning using Gated Recurrent Units (GRU) to forecast monthly retail sales. By capturing temporal dependencies and seasonal patterns, the model supports accurate demand prediction and provides actionable insights for inventory planning and strategic business decision making.

# Project Overview

Retail sectors face significant challenges in balancing product availability with dynamic market demands. This project implements a Deep Learning approach using Gated Recurrent Units (GRU) to predict monthly retail sales. By leveraging the Kaggle "Predict Future Sales" dataset, the model captures complex temporal dependencies and seasonal patterns to support effective business decision-making and inventory optimization.

# Model Architecture

The core of this system is a Gated Recurrent Unit (GRU) network, chosen for its computational efficiency and its ability to solve the vanishing gradient problem.
Key Components:
GRU Layer: 64 units were used to capture both short-term and long-term temporal dependencies in sales data.
Layer Normalization: Applied to stabilize activation distributions and accelerate training convergence.
Activation: ReLU was utilized in the dense layers for non-linear feature extraction.
Regularization Strategy: Systematically experimented with L2 (Weight Decay) and Dropout across multiple rates to find the optimal balance between bias and variance.

# Methodology

Preprocessing: Aggregated daily transaction data into monthly sales per shop and handled anomalies like returns.

Normalization: Applied Min-Max Scaling to map feature values into the $[0,1]$ range for numerical stability.

Sliding Window: Implemented a 12-month look-back period to capture annual seasonality in retail.

Data Split: Used a chronological split (80% Train / 20% Validation) to maintain temporal integrity and prevent data leakage.

Training: Utilized the Adam optimizer with Early Stopping (patience: 10) to prevent overfitting.


# Experimental Results & Regularization Analysis
Based on the systematic experiments, here are the performance metrics (normalized scale) for various configurations:


<img width="698" height="194" alt="image" src="https://github.com/user-attachments/assets/344991a7-d905-4e5e-b1ce-fa536d4abc56" />




# Key Scientific Findings:

1. L2 Superiority: The L2 (0.01) configuration proved optimal, achieving the lowest RMSE, which indicates better stability against large errors or outliers.

2. Dropout Impact: Increasing dropout rates from 0.2 to 0.7 resulted in a significant performance decline. High dropout caused the model to lose critical temporal information, leading to underfitting.

3. Visual Accuracy: The best model (L2 0.01) demonstrated high precision in following trends and seasonal spikes without significant lag.


# Business Strategic Recommendations

a. Inventory Optimization: Prioritize stock for high-volume stores like Shop 31 and Shop 25 to minimize lost sales.

b. Supply Chain Responsiveness: Use predicted demand spikes to trigger buffer stock protocols and fast-shipping schemes.

c. Operational Efficiency: For stores with lower predicted sales, reduce overhead costs and avoid overstocking to minimize storage waste.


# Tech Stack

Core: Python, TensorFlow, Keras. 

Data Processing: Pandas, NumPy, Scikit-Learn.

Visualization: Matplotlib.

Dataset: Competitive Data Science: Predict Future Sales (Kaggle).
