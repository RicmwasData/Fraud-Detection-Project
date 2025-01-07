# Fraud Detection Project

## Overview
This project aims to build a robust fraud detection system using machine learning techniques. The dataset is highly imbalanced, with fraudulent transactions being significantly rarer than legitimate ones. By leveraging various preprocessing steps, neural networks, and evaluation metrics, this project demonstrates a comprehensive approach to solving the fraud detection problem.

---

## Project Steps

### 1. **Data Preparation**
- **Shuffle the Data:** The dataset is shuffled to remove any ordering bias and ensure fair data splitting.
- **One-Hot Encoding:** The categorical `Class` column is transformed into two binary columns (`Class_0` and `Class_1`) to make it suitable for machine learning algorithms.
- **Normalize the Data:** Features are scaled to fall within the range [0, 1] using Min-Max scaling for consistency across features.
- **Split Features and Labels:** The dataset is split into independent variables (`X`) and target variables (`y`).
- **Convert to NumPy Arrays:** Data is converted to NumPy arrays for efficient numerical computations.
- **Split into Training and Testing Sets:** Data is divided into training and testing subsets to evaluate the model's performance on unseen data.

---

### 2. **Handling Class Imbalance**
- The dataset is heavily imbalanced. To address this:
  - **Logit Weighting:** A weight is calculated based on the fraud ratio, ensuring the model pays more attention to fraudulent transactions.
  - The weight is applied to the target values dynamically during training.

---

### 3. **Neural Network Model**
- A neural network function processes input tensors through three layers.
  - Each layer employs a distinct activation function to model relationships within the data.
  - The output tensor predicts whether a transaction is fraudulent or legitimate.

---

### 4. **Prediction Function**
- The prediction function evaluates the model's performance using training or testing data.
- Placeholders are dynamically replaced with actual values at runtime.

---

### 5. **Evaluation Metrics**
- To assess the model's effectiveness, the following metrics are calculated:
  - **Accuracy:** Measures the percentage of correctly predicted transactions.
  - **Precision:** Evaluates how many of the predicted fraudulent transactions are actually fraudulent.
  - **Recall:** Measures the model's ability to identify fraudulent transactions.
  - **F1 Score:** Provides a harmonic mean of precision and recall to balance both metrics.

#### Functions for Metrics
```python
# Accuracy
calculate_accuracy(actual, predicted)

# Precision
calculate_precision(actual, predicted)

# Recall
calculate_recall(actual, predicted)

# F1 Score
calculate_f1_score(actual, predicted)
```

---

## Usage
1. Prepare the dataset and ensure it is loaded as a pandas DataFrame.
2. Follow the data preprocessing steps to shuffle, encode, normalize, and split the data.
3. Train the neural network model using the training dataset.
4. Use the evaluation functions to assess the model's performance.

---

## Example
```python
# Example for calculating metrics
accuracy = calculate_accuracy(y_true, y_pred)
precision = calculate_precision(y_true, y_pred)
recall = calculate_recall(y_true, y_pred)
f1_score = calculate_f1_score(y_true, y_pred)

print(f"Accuracy: {accuracy:.2f}%")
print(f"Precision: {precision:.2f}")
print(f"Recall: {recall:.2f}")
print(f"F1 Score: {f1_score:.2f}")
```

---

## Notes
- The dataset is imbalanced; always validate model performance using metrics like precision, recall, and F1 score.
- For large datasets, consider using libraries like `scikit-learn` for optimized implementations.
- The neural network function and evaluation functions are designed to be modular for easy integration.

---

## Dependencies
- `numpy`
- `pandas`
- `scikit-learn` (optional for additional evaluation)

---

## Future Improvements
- Implement cross-validation for robust model evaluation.
- Experiment with different architectures and activation functions for the neural network.
- Incorporate additional techniques like SMOTE for handling class imbalance.

---

## License
This project is open-source and available for use under the MIT License.

