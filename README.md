# Titanic-Survival-A-Machine-Learning-Approach
The Titanic Survival Prediction Project is a machine learning-based analysis aimed at
 predicting the likelihood of a passenger's survival during the Titanic disaster. The
 problem is derived from the famous Kaggle competition: "Titanic- Machine Learning
 from Disaster." The primary objective of this project is to apply classification algorithms
 to predict survival (Survived) based on various passenger attributes such as age, gender,
 ticket class, and fare.
 This project provides an excellent opportunity to explore key concepts in data
 preprocessing, feature engineering, and model evaluation. By leveraging machine
 learning, we aim to solve a classification problem while learning practical data science
 skills. The motivation stems from the need to understand survival patterns in historical
 datasets, enabling better decision-making in similar scenarios.
Dataset description
 Source
 ● Link:Kaggle Titanic Dataset
 ● Reference: Cukierski, W. (2012). Titanic- Machine Learning from Disaster.
 Kaggle.
 Dataset Description
 ● NumberofFeatures: 10 (after preprocessing).
 ● ProblemType: Classification. The target variable Survived is binary, where 0
 indicates the passenger did not survive, and 1 indicates survival.
 ● NumberofDataPoints: 891 rows in the dataset and 12 features
 ● Feature Types:
 Categorical Variables:
 1. Survived (int): Binary (0 = No, 1 = Yes).
 2. Pclass (int): Passenger class (1, 2, 3).
 3. Name(object): Passenger name.
 3
4. Sex (object): Gender (male, female).
 5. Ticket (object): Ticket identifier.
 6. Cabin (object): Cabin identifier (many missing values).
 7. Embarked (object): Port of embarkation (C, Q, S).
 Quantitative Variables:
 1. PassengerId (int): Identifier for passengers.
 2. Age (float): Passenger age (many missing values).
 3. SibSp (int): Number of siblings/spouses aboard.
 4. Parch (int): Number of parents/children aboard.
 5. Fare (float): Fare price.
 Correlation of Features:
 Aheatmap is generated using the Seaborn library to visualize correlations
 between features and the target variable. This helps identify relationships
 and potential redundancies in the dataset.
 4
Imbalanced Dataset:
 The output feature, Survived, is imbalanced, as shown below:
 ● Survived (1): 342 passengers.
 ● DidNotSurvive (0): 549 passengers.
 Dataset Preprocessing
 Issues Identified and Solutions:
 1. Null Values:
 ○ ColumnsAffected: Cabin,Age and Embarked
 5
○ Solutions:
 ■ Dropped the Cabin column due to excessive missing values.
 ■ Imputed missing values in Age with the mean
 ■ Imputed missing values in Embarked with the mode.
 6
2. Categorical Values:
 ○ ColumnsAffected: Sex, Embarked, Name
 ○ Solutions:
 ■ Encoded Sex as binary (0: Male, 1: Female).
 ■ Encoded Embarked as numerical categories (0: S, 1: C, 2: Q).
 ■ Extracted Title from Name and mapped 'Mr': , 'Mrs': , 'Miss': ,
 'Master': , 'Rare': titles into a common category .
 3. Feature Simplification and Creation:
 ○ Dropped columns like Ticket and PassengerId that lacked predictive value.
 ○ Created new features based on age groups (Child, Young, Old).
 ○ Scaled Fare using MinMaxScaler and categorized it into Fare_Low,
 Fare_Medium, and Fare_High.
 Feature Scaling
 Feature scaling was applied to numerical data to ensure uniformity across
 features. MinMaxScaler was specifically used for Fare, which was later
 categorized into three distinct groups (Fare_Low, Fare_Medium,
 Fare_High) to capture socioeconomic information in a structured way.
 Dataset Splitting
 The dataset was split into training and testing sets as follows:
 ● TrainSet: 70% of the dataset (used for model training).
 ● TestSet: 30% of the dataset (used for model evaluation).
 Arandom split was applied using train_test_split from Scikit-learn with a
 fixed random_state for reproducibility.
 Models Applied:
 1. K-Nearest Neighbors (KNN)
 7
● Training Details:
 ○ Themodelwas trained with k=8, meaning it consider the 8 nearest
 neighbors to classify each instance.
 ● Performance Highlights:
 ○ Achieved 0.84 accuracy on the test set.
 ○ Suitable for datasets with well-defined clusters but sensitive to
 scaling and noise.
 2. Decision Tree Classifier
 ● Training Details:
 ○ Adecision tree was used to capture nonlinear relationships between
 the features and the target variable.
 ● Performance Highlights:
 ○ Effectively modeled complex patterns in the data
 ○ Achived 0.85accuracy on the test set.
 ○ Provided insights into feature importance, helping to understand
 which features contributed most to predicting survival.
 ○ Riskof overfitting, but pruning techniques can address this.
 3. Logistic Regression
 ● Training Details:
 ○ Abenchmark linear classifier applied to predict survival based on
 the weighted sum of input features.
 ○ Regularization parameters ensured stability in training.
 ● Performance Highlights:
 ○ Achieved competitive performance despite being a simple linear
 model.
 ○ Achieved 0.81accuracy on the test set
 ○ Worksbest when relationships between features and the target
 variable are approximately linear.
 8
9
Model selection/Comparison analysis
 10
11
Conclusion
 The Titanic survival prediction project successfully utilized machine learning techniques
 to analyze and model the dataset. The following insights and outcomes were observed:
 1. Dataset Insights:
 ○ Thedataset was imbalanced, with more passengers labeled as not surviving
 than surviving.
 2. Preprocessing:
 ○ Missing values were handled through imputation (e.g., filling missing Age
 with the mean).
 12
○ Categorical variables were encoded into numerical formats for
 compatibility with machine learning models.
 ○ Scaling and feature engineering (e.g., categorizing Fare and Age) enhanced
 the dataset's quality.
 3. Model Performance:
 ○ K-Nearest Neighbors (KNN): Performed moderately well, leveraging
 localized patterns but sensitive to feature scaling.
 ○ Decision Tree Classifier: Captured complex, nonlinear relationships and
 provided interpretable insights into feature importance.
 ○ Logistic Regression: Achieved competitive results as a baseline model,
 demonstrating its effectiveness in handling linear relationships.
 4. Model Comparison:
 ○ Allmodels were evaluated using accuracy, precision, recall, F1-score, and
 confusion matrices.
 ○ Eachmodel exhibited distinct strengths, with no single model universally
 outperforming others.
 5. Future Directions:
 ○ Explore advanced models like Random Forest, Gradient Boosting, or
 Neural Networks for improved performance.
 ○ Address class imbalance using techniques such as oversampling,
 undersampling, or SMOTE (Synthetic Minority Oversampling Technique).
 ○ Investigate additional feature engineering opportunities to capture hidden
 patterns.
 This project demonstrates the value of preprocessing, feature engineering, and careful
 model selection in solving real-world classification problems. By combining insights
 from machine learning models and data analysis, we can gain a deeper understanding of
 the factors influencing survival.
