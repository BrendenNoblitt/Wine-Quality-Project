# Wine Quality Project: Project Overview
This project is based on the Kaggle dataset by UCI Machine Learning. This project lists many different variables that make up the "Vinho Verde" Portuguese wine, as well as the numeric quality of the wine on a scale from 1-10. The different data points are also ordered and not balanced, meaning there are more normal types of wine than anything else. I chose to put together a multiple linear regression analysis to find the relationship between the variables that most closely correlated to the quality of the wine.

# Prerequisites 
* Python 3.8 3 
* Jupyter Notebooks - Python Anaconda Suite 
* Red Wine Quality Dataset: https://www.kaggle.com/uciml/red-wine-quality-cortez-et-al-2009
* Optional: Knowledge of CRISP-DM Workflow

# CRISP-DM Stages 
## Understanding Business Objectives
In a real world scenario, I would be doing this project to figure out what manufacturers and wine-makers could do to increase the quality of their wine, and overall increase sales. The two main objectives for this project were to 
1. Find which variables correlate closely to quality of the wine 
2. Create a model that predicts the quality of wine based off of correlated variables 

## Data Understanding and Data Cleaning
After diving into the data, I found that the amount of outliers was causing the data to become unevenly distributed. I created an interquartile range (IQR) function that allowed me to eliminate the bottom 25% of the distribution and the top 25% of the distribution. This was the only cleaning that I really needed to do, as the data was in the right format and there was no missing or corrupt data.

## Construct Data 
After cleaning and understanding the data, I went into some basic statistical analysis. I found that there were 3 variables that had a correlation high enough to warrant further analysis:
1. Alcohol: 0.46 
2. Sulphates: 0.38 
3. Citric Acid: 0.23 
Alcohol and sulphates also had a correlation of 0.21. After finding these correlations, I started on my model.

## Modeling
For my model, I set x to variables that had a p-value of under 0.05. I removed "residual sugar", "free sulfur dioxide", and "pH", due to their high p-values. After I removed these variables, I set y to quality. I used a multiple linear regression to find the relationships between all variables to quality. 

<img width="400" alt="summary" src="https://user-images.githubusercontent.com/65836934/85968627-33456500-b98b-11ea-8d08-2b380207b1c8.png">

# Conclusion 
After modeling, I found that sulphates, alcohol, and fixed acidity all had positive regression coefficients. Sulphates, however, had a regression correlation of over 1, suggesting that as quality increases, so does the mean sulphate count. It is also noted that density had a -9.14 regression coefficient, meaning that as quality went up, density went down significantly. It can be seen in the following graphs that there is a larger amount of predicted quality 6 wines than there are in the current data. If this were a business situation, I would suggest that manufacturers and winemakers produce and sell wine that have a small density and a slightly larger amount of sulphates.

![pre-prediction](https://user-images.githubusercontent.com/65836934/85968628-33ddfb80-b98b-11ea-8899-18c24964400b.png)![post-prediction](https://user-images.githubusercontent.com/65836934/85968629-33ddfb80-b98b-11ea-971a-6007db50c51a.png)

