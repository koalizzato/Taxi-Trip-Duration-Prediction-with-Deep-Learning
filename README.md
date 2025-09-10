# Taxi-Trip-Duration-Prediction-with-Deep-Learning

The focus of this project is on predicting the duration of taxi trips in New York City using both Deep Learning and Machine Learning techniques, comparing neural network architectures with the XGBoost algorithm.

---

## Project Overview

### 1. Data Collection and Preprocessing
- Dataset of NYC taxi trips, including features such as pickup and drop-off coordinates, datetime, passenger count, and trip duration.  
- Data cleaning involved removing outliers and unrealistic trip times (e.g., trips shorter than 2 minutes or excessively long).  
- Feature engineering included:  
  - Calculation of trip distance using the haversine formula.  
  - Bearing angle (trip direction).  
  - Borough extraction for pickup and drop-off locations.  
  - Time-based features (year, month, day, weekday).  
- One-hot encoding was applied to categorical variables for compatibility with deep learning models.  

---

### 2. Model Design and Training
- **Neural Networks**:  
  - Multiple architectures with increasing depth and complexity, ranging from 5-layer dense networks (~51K parameters) to deeper architectures with over 4M parameters.  
  - Training strategies included *EarlyStopping* and *ReduceLROnPlateau* to prevent overfitting.  
  - Evaluation metrics: **Mean Absolute Error (MAE)** and **Root Mean Squared Logarithmic Error (RMSLE)**.  

- **XGBoost**:  
  - Several configurations tested with varying tree depth, learning rate, and subsampling strategies.  
  - Label encoding used for categorical variables to improve efficiency compared to one-hot encoding.  

---

### 3. Results and Evaluation
- **Neural Networks** achieved competitive accuracy but required significant computational resources and were less interpretable.  
- **XGBoost** consistently outperformed deep learning models, achieving lower MAE and RMSLE with more efficient training.  
- Feature importance analysis highlighted that **latitude, longitude, distance, and bearing** were the most influential predictors.  

---

### 4. Conclusions
- XGBoost proved to be more effective and interpretable than deep neural networks for this problem, providing higher accuracy and efficiency.  
- Neural networks, while powerful, showed limitations when applied to structured tabular data compared to gradient-boosted trees.  
- Future improvements could include adding external features such as **weather conditions, traffic patterns, and holidays** to enhance prediction accuracy.
