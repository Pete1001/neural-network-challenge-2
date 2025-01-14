# neural-network-challenge-2

# Neural Network Challenge: Predicting Employee Attrition and Department Suitability

## Overview
This project implements a branched neural network to help HR predict:
1. Whether employees are likely to leave the company (`Attrition`).
2. The department that best suits an employee (`Department`).

The model uses TensorFlow/Keras, leveraging shared layers and separate output branches for these two predictions. This README provides an overview of the methodology, implementation details, and potential improvements.

---

## Features
- **Dataset**: The project uses an employee attrition dataset containing 27 columns with employee demographic, performance, and satisfaction metrics.
- **Neural Network**: A branched neural network architecture is implemented to predict:
  - `Attrition`: Binary classification (Yes/No).
  - `Department`: Multi-class classification (e.g., Sales, Research & Development).
- **Preprocessing**: Data is encoded and scaled appropriately for the neural network.
- **Metrics**: Accuracy is the primary metric for evaluating predictions, though suggestions for alternative metrics are explored.

---

## File Structure
- `attrition.ipynb`: Jupyter Notebook containing the complete implementation.
- `README.md`: This file, explaining the project setup and methodology.

---

## Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/Pete1001/neural-network-challenge-2.git
cd neural-network-challenge-2
```

### 2. Environment Setup
Install the required Python libraries:
```bash
pip install pandas numpy tensorflow scikit-learn matplotlib
```

### 3. Run the Notebook
Upload `attrition.ipynb` to Google Colab or run it locally:
```bash
jupyter notebook attrition.ipynb
```

### 4. Evaluate the Model
The notebook outputs:
- Model architecture summary.
- Accuracy scores for both predictions (Attrition and Department).
- Suggestions for further improvement.

---

## Methodology

### Data Preprocessing
1. **Data Cleaning**:
   - Verified no missing values.
   - Checked for outliers using IQR.

2. **Feature Selection**:
   - Selected 10 key columns (e.g., Age, JobInvolvement, DistanceFromHome).

3. **Encoding**:
   - Categorical data converted to numeric using `OneHotEncoder`.
   - Target variables (`Attrition` and `Department`) encoded.

4. **Scaling**:
   - Applied `StandardScaler` to normalize numerical features.

5. **Train-Test Split**:
   - Data split into training (75%) and testing (25%).

### Neural Network Architecture
- **Input Layer**: Number of features selected (10).
- **Shared Layers**: Two dense layers with ReLU activation.
- **Branch 1 (Department)**:
  - One dense hidden layer with ReLU.
  - Output layer with softmax activation.
- **Branch 2 (Attrition)**:
  - One dense hidden layer with ReLU.
  - Output layer with sigmoid activation.

### Model Compilation
- Loss:
  - `categorical_crossentropy` for Department.
  - `binary_crossentropy` for Attrition.
- Optimizer: Adam.
- Metrics: Accuracy.

### Training
- **Epochs**: 100
- **Batch Size**: 32
- Validation data used to monitor performance during training.

---

## Results
- **Accuracy**:
  - `Attrition`: 51%
  - `Department`: 85%
- **Insights**:
  - Accuracy is a good starting metric but can be complemented with others like F1-score for imbalanced data.

---

## Potential Improvements
1. Implement **early stopping** to prevent overfitting and reduce training time.
2. Use additional metrics (e.g., precision, recall) to evaluate imbalanced classes.
3. Hyperparameter tuning (e.g., learning rate, batch size).
4. Add dropout layers to reduce overfitting.
5. Explore feature engineering to include interaction terms.

---

## License
This project is open-source under the MIT License.
