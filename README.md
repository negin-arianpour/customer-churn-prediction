Customer Churn Prediction — Project Summary

📌 What This Project Is About
A machine learning project that predicts whether a telecom customer will leave (churn) or stay based on their account information. This is a real business problem — companies lose significant revenue from churning customers, so predicting churn early allows them to take action and retain customers.
Dataset: Telco Customer Churn (IBM/Kaggle) — 7,043 customers, 21 features including contract type, monthly charges, tenure, and internet service type.

📚 Libraries Used
LibraryPurposeTensorFlow / KerasBuilding and training the neural networkPandasLoading, cleaning, and exploring the dataNumPyNumerical operations and array handlingScikit-LearnData splitting, scaling, encoding, evaluationMatplotlibPlotting accuracy and loss graphs

🏗️ Model Architecture
A Sequential Neural Network with:

Input layer → 64 neurons, ReLU activation
Dropout layer (30%) — prevents overfitting
Hidden layer → 32 neurons, ReLU activation
Dropout layer (30%)
Output layer → 1 neuron, Sigmoid activation (binary output)
Optimizer: Adam | Loss: Binary Crossentropy


🔧 Modifications Made to Improve Results
1. Data Cleaning

Fixed TotalCharges column which had blank spaces instead of numbers
Removed 11 corrupted rows
Dropped customerID as it has no predictive value

2. Feature Engineering

Encoded all categorical columns (e.g. gender, contract type) using LabelEncoder
Applied StandardScaler to normalise numerical features — critical for neural network performance

3. Class Weight Balancing

Dataset was imbalanced: 5,163 stayed vs 1,869 churned
Applied compute_class_weight('balanced') to tell the model to pay more attention to churned customers
This was the key improvement that boosted churn detection


📈 Results
MetricBefore ImprovementAfter ImprovementOverall Accuracy78.82%79.32%Churn Recall45%51%Churn F1-Score0.530.57

💡 Business Insight
The model successfully identifies customers likely to churn with 79% overall accuracy. The class weight modification specifically improved detection of churning customers — the most valuable prediction for a business trying to reduce customer loss.
