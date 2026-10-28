# Credit Card Fraud Detection



## Project Overview

This project focuses on detecting fraudulent credit card transactions using machine learning techniques. The dataset is highly imbalanced because fraudulent transactions represent only a small percentage of all transactions.

The objective is to build and evaluate classification models that can identify suspicious transactions while balancing fraud detection and false alarms.

## Objectives

- Analyze credit card transaction data and identify class imbalance.
- Perform exploratory data analysis (EDA).
- Apply SMOTE to address class imbalance in the training data.
- Build and compare Logistic Regression and Random Forest models.
- Evaluate performance using Precision, Recall, F1-score, and ROC-AUC.
- Visualize model performance using confusion matrices and evaluation curves.
- Analyze important features and discuss real-world scalability.

## Dataset

**Dataset:** Credit Card Fraud Detection

**Source:** Kaggle – Machine Learning Group (ULB)

Dataset link: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains 284,807 credit card transactions, including 492 fraudulent transactions.

### Dataset features

- `Time`: Seconds elapsed between a transaction and the first transaction in the dataset.
- `V1` to `V28`: Anonymized features obtained through Principal Component Analysis (PCA).
- `Amount`: Transaction amount.
- `Class`: Target variable, where `0` represents a legitimate transaction and `1` represents a fraudulent transaction.

The dataset is highly imbalanced, making fraud detection a challenging classification problem.

**Note:** Download `creditcard.csv` from Kaggle and place it in the same folder as the Jupyter Notebook before running the project. The dataset CSV is not included in this repository because of its large file size.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)

## Project Workflow

### 1. Data Loading and Exploration

- Loaded the credit card transaction dataset.
- Examined the dataset dimensions, data types, and missing values.
- Analyzed the distribution of legitimate and fraudulent transactions.

### 2. Exploratory Data Analysis

- Visualized transaction amount distributions for fraudulent and legitimate transactions.
- Explored fraud counts and rates by approximate transaction hour.
- Examined the severity of class imbalance.

### 3. Data Preparation

- Separated input features from the target variable.
- Split the dataset into training and testing sets using stratified sampling.
- Applied SMOTE only to the training data to generate synthetic minority-class examples.

### 4. Model Training

Two machine learning classifiers were trained:

**Logistic Regression**
- Used feature scaling.
- Used class weighting to help account for class imbalance.

**Random Forest**
- Used an ensemble of decision trees.
- Used class weighting to help account for class imbalance.

### 5. Model Evaluation

The models were evaluated using:

- **Precision:** Measures how many predicted fraud cases were actually fraudulent.
- **Recall:** Measures how many actual fraudulent transactions were detected.
- **F1-score:** Balances precision and recall.
- **ROC-AUC:** Measures the model's ability to distinguish between the two classes across classification thresholds.
- **Confusion Matrix:** Shows correctly and incorrectly classified transactions.

Accuracy was not used as the only performance measure because a model can achieve high accuracy while failing to detect fraudulent transactions.

### 6. Visualization and Feature Analysis

The project includes:

- Transaction amount distribution plots.
- Approximate time-of-day fraud analysis.
- Model performance comparison charts.
- Confusion matrices.
- ROC curves.
- Precision–Recall curves.
- Random Forest feature importance visualization.

### 7. Scalability Discussion

The project discusses strategies for extending fraud detection to a system processing one million transactions per hour, including streaming systems, efficient model inference, distributed processing, monitoring, and retraining.

The production throughput has not been benchmarked in this notebook.

## Results

The notebook compares Logistic Regression and Random Forest using Precision, Recall, F1-score, and ROC-AUC.

The preferred model should be selected based on the measured test-set results and the cost of missed fraud versus false alarms. Actual scores are available in the notebook's final results table.

For fraud detection, recall is particularly important because false negatives represent fraudulent transactions that the model fails to identify. Precision must also be considered to avoid excessive false alarms.

## How to Run the Project

1. Clone or download this repository.
2. Download `creditcard.csv` from the Kaggle dataset link above.
3. Place `creditcard.csv` in the same directory as `SaatvikaR_Task3.ipynb`.
4. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
   ```

5. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

6. Open `SaatvikaR_Task3.ipynb`.
7. Run the notebook cells in order.

## Limitations

- The dataset contains anonymized PCA features, limiting their direct business interpretation.
- The approximate time-of-day analysis is based on elapsed seconds, not actual transaction timestamps.
- SMOTE creates synthetic examples and does not guarantee improved real-world performance.
- The notebook uses a benchmark dataset and has not been tested in a live payment system.
- Production latency, throughput, and deployment reliability require separate testing.

## Future Improvements

- Tune hyperparameters and classification thresholds.
- Compare additional models such as XGBoost.
- Evaluate performance using additional datasets and newer transactions.
- Benchmark inference latency and throughput.
- Monitor data drift and retrain models as fraud patterns change.

## Conclusion

This project demonstrates how machine learning can support credit card fraud detection in highly imbalanced data. By combining data exploration, SMOTE, Logistic Regression, Random Forest, and suitable evaluation metrics, the project provides a foundation for identifying suspicious transactions.

Reliable real-world deployment would require further testing, threshold optimization, monitoring, and scalable infrastructure.

