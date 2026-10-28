# OIBSIP Task 2: Wine Quality Prediction

## Project Overview
This project uses machine learning classification algorithms to predict wine quality categories based on physicochemical properties of red wine.

## Objective
To analyze wine characteristics, build classification models, compare their performance, and identify the most useful chemical features for predicting wine quality.

## Dataset
- **Dataset:** Wine Quality — Red Wine
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/186/wine+quality)
- **Samples:** 1,599
- **Input features:** 11 physicochemical properties

## Technologies Used
- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow
1. Load and inspect the dataset.
2. Perform exploratory data analysis and visualize quality distributions.
3. Convert numerical quality scores into three categories:
   - Low: score ≤ 5
   - Medium: score = 6
   - High: score ≥ 7
4. Split the data into training and testing sets using stratified sampling.
5. Train Random Forest, SGD Classifier, and Support Vector Classifier (SVC).
6. Evaluate models using accuracy, classification reports, F1-scores, and confusion matrices.
7. Visualize Random Forest feature importance.
8. Compare models and select the strongest candidate.

## Model Results

| Model | Accuracy | Macro F1-score |
|---|---:|---:|
| Random Forest | 74.38% | 0.710 |
| Support Vector Classifier | 60.94% | 0.576 |
| SGD Classifier | 55.31% | 0.482 |

Random Forest achieved the best accuracy and macro F1-score among the three models in this experiment.

## Conclusion
Random Forest was the strongest model on the test set. However, some quality categories were harder to predict because the dataset is imbalanced. Further improvements could include hyperparameter tuning, cross-validation, and additional examples of underrepresented categories.

## Project File
- `SaatvikaR_Task2.ipynb` — notebook containing the data analysis, model training, evaluation, and visualizations.

## Author
Saatvika R

*This project was completed as part of the Oasis Infobyte Internship (OIBSIP).*
