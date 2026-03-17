# 🩺 Breast Cancer Prediction Project

A comprehensive machine learning project for predicting breast cancer diagnosis (Malignant/Benign) using various classification algorithms. The project includes data preprocessing, exploratory data analysis, model building with hyperparameter tuning, handling imbalanced data, feature selection, and model persistence.

## 📋 Project Overview

This project aims to build a robust classification model to predict whether a breast tumor is malignant (cancerous) or benign (non-cancerous) based on various features extracted from digitized images of fine needle aspirate (FNA) of breast masses.

## 📊 Dataset Information

The dataset contains features computed from digitized images of breast mass aspirates:

- **Source**: Wisconsin Diagnostic Breast Cancer (WDBC) dataset
- **Target Variable**: `diagnosis` (M = Malignant, B = Benign)
- **Features**: 30 real-valued features computed for each cell nucleus
- **Features Include**:
  - radius (mean of distances from center to points on the perimeter)
  - texture (standard deviation of gray-scale values)
  - perimeter
  - area
  - smoothness (local variation in radius lengths)
  - compactness (perimeter^2 / area - 1.0)
  - concavity (severity of concave portions of the contour)
  - concave points (number of concave portions of the contour)
  - symmetry
  - fractal dimension ("coastline approximation" - 1)

## 🚀 Features

### 1. **Data Preprocessing**
- Label encoding of categorical diagnosis (M/B → 1/0)
- Removal of unnecessary columns (ID)
- Data type conversion

### 2. **Exploratory Data Analysis (EDA)**
- **Correlation Heatmaps**: Visualize feature relationships
- **Box Plots**: Analyze feature distribution by diagnosis
- **Distribution Plots**: Compare feature distributions for malignant vs benign cases
- **Outlier Analysis**: Identify patterns without removing important medical data

### 3. **Machine Learning Models**

Three classification algorithms with hyperparameter tuning:

- **Random Forest Classifier** 🌲
- **Support Vector Machine (SVM)** 🔷
- **XGBoost Classifier** ⚡

### 4. **Model Optimization**
- **GridSearchCV**: Hyperparameter tuning with cross-validation
- **Cross-Validation**: 10-fold CV for robust model evaluation
- **SMOTE**: Handling imbalanced data through oversampling
- **Feature Selection**: Identifying top 15 most important features

### 5. **Model Persistence**
- Save trained models using Pickle
- Load models for prediction in separate notebooks

## 🛠️ Technologies Used

- **Python 3.x**
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computing
- **Scikit-learn**: Machine learning algorithms, preprocessing, model selection
- **XGBoost**: Gradient boosting framework
- **Matplotlib/Seaborn**: Data visualization
- **Imbalanced-learn (SMOTE)**: Handling class imbalance
- **Pickle**: Model serialization

## 📁 Project Structure

```
PRJ Cancer Prediction/
│
├── data.csv                          # Breast cancer dataset
├── Cancer Project.docx                # Project documentation
├── README.md                          # Project README file
│
├── Model Files (generated):
│   ├── Random Forest                  # Trained Random Forest model
│   ├── SVC                            # Trained SVM model
│   └── XGBoost                        # Trained XGBoost model
│
└── Visualizations (generated):
    ├── Correlation Heatmaps
    ├── Box Plots
    ├── Distribution Plots
    └── Feature Importance Chart
```

## 💻 Implementation Steps

### 1. **Import Libraries**
```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.ensemble import RandomForestClassifier
from sklearn.svm import SVC
from xgboost import XGBClassifier
from imblearn.over_sampling import SMOTE
# ... additional imports
```

### 2. **Load and Explore Data**
```python
data = pd.read_csv('data.csv')
print(data['diagnosis'].value_counts())  # Check class distribution
```

### 3. **Data Preprocessing**
```python
# Convert diagnosis to categorical and encode
df['diagnosis'] = df['diagnosis'].astype('category')
df['diagnosis'] = df['diagnosis'].cat.codes

# Create feature matrix (X) and target vector (y)
x = df.drop(['diagnosis', 'id'], axis=1)
y = df['diagnosis']
```

### 4. **Exploratory Data Analysis**
- Correlation analysis between features
- Box plots to visualize feature distribution by diagnosis
- Distribution plots for each feature

### 5. **Model Building with GridSearchCV**
```python
def FitModel(X, Y, algo_name, algorithm, gridSearchParams, cv):
    # Train-test split
    # GridSearchCV for hyperparameter tuning
    # Model evaluation with confusion matrix and classification report
    # Save model using pickle
```

### 6. **Handle Imbalanced Data with SMOTE**
```python
sm = SMOTE(random_state=42)
X_res, Y_res = sm.fit_resample(x, y)
```

### 7. **Feature Selection**
- Extract feature importances from Random Forest
- Select top 15 features for model optimization
- Visualize feature importance

### 8. **Model Evaluation**
- Accuracy Score
- Confusion Matrix
- Classification Report (Precision, Recall, F1-Score)
- Best Parameters from GridSearchCV

## 📈 Model Performance

The project evaluates three models under different conditions:

1. **Original Imbalanced Data**
   - Random Forest
   - SVM
   - XGBoost

2. **After SMOTE (Balanced Data)**
   - Random Forest
   - SVM
   - XGBoost

3. **After Feature Selection (Top 15 Features)**
   - Random Forest
   - SVM
   - XGBoost

## 💾 Model Persistence

Models are saved using Pickle for later use:

```python
# Save model
pickle.dump(grid_result, open(algo_name, 'wb'))

# Load model
load_model = pickle.load(open("XGBoost", "rb"))
predictions = load_model.predict(x_test)
```

## 🔧 How to Run

1. **Clone the repository**
2. **Install required packages**:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn xgboost imbalanced-learn
   ```
3. **Update file path** in the code to match your directory structure
4. **Run the Jupyter notebook** or Python script
5. **Use saved models** for predictions in other notebooks

## 📝 Key Observations

- **Outliers are preserved** due to medical data sensitivity
- **SMOTE improves** model performance on minority class
- **Feature selection** reduces dimensionality while maintaining accuracy
- **XGBoost** often provides the best balance of performance and accuracy

## 🎯 Use Cases

- **Medical Diagnosis Support**: Assist doctors in breast cancer diagnosis
- **Feature Analysis**: Identify most important predictors of malignancy
- **Model Comparison**: Evaluate different algorithms for medical classification

## 🤝 Contributing

Feel free to fork this project, submit issues, or suggest improvements. Contributions are always welcome!

## 📄 License

This project is for educational purposes as part of machine learning training.

---

**⭐ Early Detection Saves Lives! ⭐**
