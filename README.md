# My-ML-Project
Project: Air Quality Prediction using CNN

This project predicts PM2.5 air pollutant levels using a 1D Convolutional Neural Network (CNN). The model is trained on Beijing air quality data (2013–2017) that includes meteorological factors and pollutant concentrations.

Key Steps in the Workflow:

1.Data Preprocessing
Loaded the PRSA air quality dataset.
Handled missing values using mode (for categorical) and linear interpolation (for continuous).
Encoded categorical features (e.g., wind direction) and normalized all features using StandardScaler.
Created time-series windows so the model can learn from past trends.

2.Model Architecture (Sequential CNN)
Input Layer: Sliding window of previous time steps (e.g., 5 hours × 12 features).
Conv1D Layer (128 filters): Extracts temporal patterns from sequences.
Flatten Layer: Prepares data for dense layers.
Dense Layers: Several fully connected layers with ReLU activation to capture non-linear relationships.
Output Layer: Single neuron with linear activation to predict PM2.5 concentration.

3.Training & Evaluation
Trained using the Adam optimizer and Mean Squared Error (MSE) loss.
Evaluated using RMSE, MAE, and R² Score.
Visualized predicted vs. actual PM2.5 levels for performance assessment.

Why CNN?
CNNs can efficiently capture local temporal patterns in time-series data (like sudden pollution spikes) by sliding filters over the input window, making them well-suited for this type of prediction.
