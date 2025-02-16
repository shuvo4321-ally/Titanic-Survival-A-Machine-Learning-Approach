# 🚢 Titanic Survival Prediction

### 🏆 Kaggle Challenge: "Titanic - Machine Learning from Disaster"
This project aims to predict passenger survival using machine learning models, leveraging key data science concepts such as preprocessing, feature engineering, and model evaluation.

---
## 📂 Dataset Overview
- **Source:** [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic)
- **Reference:** Cukierski, W. (2012)
- **Total Records:** 891 rows
- **Number of Features (After Preprocessing):** 10
- **Problem Type:** Classification (Binary: `0` = Not Survived, `1` = Survived)

### 📌 Features
| Feature Name | Type | Description |
|-------------|------|-------------|
| Survived | Categorical (Binary) | Target Variable (0 = No, 1 = Yes) |
| Pclass | Categorical (Int) | Passenger class (1, 2, 3) |
| Name | Categorical (Object) | Passenger name (Extracted Titles) |
| Sex | Categorical (Object) | Gender (male, female) |
| Ticket | Categorical (Object) | Ticket identifier (Dropped) |
| Cabin | Categorical (Object) | Cabin identifier (Dropped due to missing values) |
| Embarked | Categorical (Object) | Port of embarkation (C, Q, S) |
| PassengerId | Quantitative (Int) | Identifier (Dropped) |
| Age | Quantitative (Float) | Passenger age (Imputed missing values) |
| SibSp | Quantitative (Int) | Number of siblings/spouses aboard |
| Parch | Quantitative (Int) | Number of parents/children aboard |
| Fare | Quantitative (Float) | Fare price (Scaled and categorized) |

### 🔍 Data Imbalance
- **Survived (1):** 342 passengers
- **Not Survived (0):** 549 passengers

---
## 🛠 Data Preprocessing
### 🔸 Handling Missing Values
- **Cabin:** Dropped due to excessive missing values.
- **Age:** Imputed using the mean.
- **Embarked:** Imputed using the mode.

### 🔸 Encoding Categorical Features
- **Sex:** Binary encoding (`0 = Male`, `1 = Female`)
- **Embarked:** Converted to numerical categories (`0 = S, 1 = C, 2 = Q`)
- **Name:** Extracted titles and mapped to common categories (`Mr, Mrs, Miss, Master, Rare`)

### 🔸 Feature Engineering
- **Dropped:** `Ticket`, `PassengerId` (Lacked predictive value)
- **Created New Features:**
  - **Age Groups:** Categorized into `Child, Young, Old`
  - **Fare Scaling:** Applied `MinMaxScaler` and categorized into `Fare_Low, Fare_Medium, Fare_High`

---
## 📊 Data Visualization
✅ **Feature Correlation Heatmap** using Seaborn to visualize relationships between features and survival.

✅ **Class Imbalance Analysis** to assess distribution of survived vs. non-survived passengers.

---
## 🏋️‍♂️ Model Training & Evaluation
### 🔹 Dataset Splitting
- **Train Set:** 70% (Used for training)
- **Test Set:** 30% (Used for evaluation)
- **Random Split:** `train_test_split` (Fixed `random_state` for reproducibility)

### 🤖 Models Implemented
| Model | Accuracy | Key Highlights |
|-------|----------|---------------|
| **K-Nearest Neighbors (KNN)** | 0.84 | Sensitive to scaling, best for well-defined clusters |
| **Decision Tree Classifier** | 0.85 | Captures complex patterns, interpretable but prone to overfitting |
| **Logistic Regression** | 0.81 | Strong baseline for linear relationships |

### 🔹 Model Comparison
- **Metrics Used:** Accuracy, Precision, Recall, F1-Score, Confusion Matrix
- **Observations:** Each model showed distinct strengths, with no single model universally outperforming others.

---
## 🚀 Future Enhancements
✅ **Try Advanced Models:**
- Random Forest
- Gradient Boosting
- Neural Networks

✅ **Handle Class Imbalance:**
- Oversampling, Undersampling
- SMOTE (Synthetic Minority Oversampling Technique)

✅ **More Feature Engineering:**
- Explore interaction terms and new derived features

---
## 💡 Conclusion
This project successfully applied machine learning to analyze survival patterns in the Titanic dataset. By leveraging preprocessing techniques, feature engineering, and multiple classification models, we gained valuable insights into factors affecting survival.

📌 **Key Takeaways:**
- Data preprocessing significantly impacts model performance.
- Feature engineering enhances predictive power.
- Model selection depends on dataset characteristics and problem requirements.

📢 *Stay tuned for more updates as we implement advanced models!* 🚀

