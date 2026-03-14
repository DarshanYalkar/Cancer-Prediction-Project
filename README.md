# Cancer-Prediction-Project


**📋 Project Overview**

This project aims to build a machine learning model that can accurately predict whether a tumor is malignant or benign based on various medical measurements. Using the Wisconsin Diagnostic Breast Cancer dataset, I performed exploratory data analysis, preprocessing, and implemented multiple classification algorithms to achieve reliable predictions.


**🎯 Key Objectives**

Analyze and preprocess medical data for machine learning

Visualize feature relationships using correlation analysis

Build classification models to predict cancer diagnosis

Compare model performance and select the best approach

**📊 Dataset**

The dataset contains 569 samples with 32 features each, including:

ID number

Diagnosis: M = malignant, B = benign

30 real-valued features computed from digitized images of fine needle aspirates (FNA) of breast masses

radius_mean, texture_mean, perimeter_mean, area_mean, smoothness_mean, etc.

Standard error features and "worst" features


**📈 Project Workflow**

**1. Data Loading & Exploration**
   
Loaded the dataset using pandas

Examined data shape, types, and distribution

Checked for missing values (none found ✅)

**2. Data Preprocessing**
   
Converted target variable diagnosis from categorical ('M'/'B') to numerical (1/0)

Separated features (X) and target (y)

Dropped unnecessary columns like id

**3. Exploratory Data Analysis (EDA)**

# Target distribution

diagnosis

B    357

M    212

Benign: 357 samples

Malignant: 212 samples

**4. Feature Correlation Analysis**
   
Generated correlation matrix for all 30 features

Created a comprehensive heatmap to visualize relationships

Identified strong correlations between certain features (e.g., radius_mean, perimeter_mean, area_mean).

**5. Model Implementation**

The following machine learning algorithms were implemented:

Random Forest Classifier

Support Vector Machine (SVM)

XGBoost Classifier

**6. Model Evaluation**
   
Used train-test split for validation

Implemented K-Fold Cross-Validation

Evaluated using:

Accuracy Score

Confusion Matrix

Classification Report (Precision, Recall, F1-Score)



**💡 Key Insights**

The dataset is well-balanced with no missing values

Strong correlations exist between certain features (e.g., radius, perimeter, and area measurements)

Feature correlation analysis helps understand data relationships before model building

Multiple algorithms were compared to find the best performer



**🔮 Future Work**

Hyperparameter tuning using GridSearchCV

Feature selection to reduce dimensionality

Implement additional algorithms (Logistic Regression, Neural Networks)

Deploy the model as a web application

Add more visualization for model performance comparison



**🤝 Connect with Me**

LinkedIn: [www.linkedin.com/in/darshan-yalkar-97653b333]

GitHub: [https://github.com/DarshanYalkar]

Email: [jainyalkard@gmail.com]


⭐ If you found this project interesting, feel free to star the repository!
