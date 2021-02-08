## [Project 1: Western Health WIES prediction modelling](https://github.com/qaziadnan393/Western-Health-Machine-learning)
Western Health Australia is a Public hospital which serves a population of approximately 800,000 people in western region of Melbourne.

- Developed a Machine Learning model (99% accuracy) to predict Weighted Inlier Equivalent Separation.
- Maintained large databases and used various professional statistical techniques to collect, analyse, and interpret data from customers and partners.
- Identified and reported any data issues, conducted detailed weekly reports, and pro-actively participated in team meetings with managers.
- Conducted interviews with key business users to collect information on business processes and user requirements.
- Contributing to the organisation’s efforts for optimisation through predictive & prescriptive analytics, effectively reducing the current manual process and hence the turnaround time of 20 days.
- Assisted Western health with a blueprint model for a WIES prediction which is considered and implemented by their organization.
- Tech Stack: Jupyter Notebook, Python, Machine learning, Prediction Modelling, Tableau, Power BI.

**Predicting WIES**

**1. Random Forest**

![](/Images/RF.jpg)

Random Forest came out to be the best of the three with an accuracy score of 76%. 

**2. Bayesian Regression**

![](/Images/BR.jpg)

Accuracy score 74%

**3.Neural Network**

![](/Images/Neural.jpg)

Accuracy score 73%

## Project 2: Revnue metric predictions for advertising session data

**Introduction**
The objective of this research project is to explore the real-world data of the advertising and build a predictive model for predicting a revenue-related metric defined for various online advertisement campaigns. In the previous phase of the report, we covered the aspects of data retrieving, exploration and analysis. This next part of the report covers the modeling of the data to predict the revenue generated for each user session on online ads by services. This report includes optimizations performed on the machine learning models and metrics considered for judging the accuracy of the model and its stability to design a sustainable predictive model. The predicted results of the current reports are finally submitted to a Kaggle competition which currently ranks us 2nd in the leaderboard.

The report is divided into 5 sections:

Overview : outlines our methodology

Data Preparation: summarizes the data preparation process and our model evaluation strategy.

Hyperparameter Tuning: describes the hyperparameter tuning process for each classification algorithm.

Performance Comparison: presents model performance comparison results.

Limitations :discusses a limitations of our approach and possible solutions.

Summary: provides a brief summary of our work in this project.

References: provides a brief summary of our work in this project.

Each section includes description and python code to support the description. All python codes are compiled in Jupyter notebook with python version of 3.6.18.

**Evaluate Grid search**
Grid serach has given the best parameters for these models as bootstrap =True, max_depth = 12,max_features = 12, min_samples_leaf = 5, n_estimators = 300 . Using these parameters we execute the final model and compare the accuracy increase from the baseline model using same evaluate function defined earlier.

```markdown
#best_grid = grid_search.best_estimator_
#Choosing best grid parameters selected

best_grid = RandomForestRegressor(bootstrap =True, min_samples_leaf = 5,  \
max_depth = 12,max_features = 12,  n_estimators = 300, random_state = 42)
best_grid.fit(train_features, train_labels)
grid_accuracy = \
evaluate(best_grid, test_features, test_labels)
# results_RFR = get_search_results(grid_search)
    RFFoutGrid_csv ='RFFoutGrid.csv'
results_RFR = pd.read_csv(RFFoutGrid_csv,sep=',', decimal='.')
results_RFR.head()
#best_grid = grid_search.best_estimator_
#Choosing best grid parameters selected
​
best_grid = RandomForestRegressor(bootstrap =True, min_samples_leaf = 5,  \
max_depth = 12,max_features = 12,  n_estimators = 300, random_state = 42)
best_grid.fit(train_features, train_labels)
grid_accuracy = \
evaluate(best_grid, test_features, test_labels)
# results_RFR = get_search_results(grid_search)
    RFFoutGrid_csv ='RFFoutGrid.csv'
results_RFR = pd.read_csv(RFFoutGrid_csv,sep=',', decimal='.')
results_RFR.head()
```
Model Performance
Average Error: 0.4241 degrees.
Accuracy = -161.23%.

Final model by Random forest regression
As best grid search provides satisfactory results for the model. We continue with these parameters and establish final model by using actual train and test datasets and submit these predictions to Kaggle leaderboard. The final score achieved by the best model is 0.81190, which is considerably good improvement over polynomial model.
