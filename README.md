# kaggle-competition

## Introduction

We had the challenge of participating in a Kaggle competition https://www.kaggle.com/c/diamonds-datamad0921/overview

## The goal 

The goal of this competition is the prediction of the price of diamonds based on their characteristics 
(weight, color, quality of cut, etc.), putting into practice all the machine learning techniques we know

## Preprocesing
We had some categorical features, and after a quick research on google we check they had a natural order so we decided
to do a manual sort of them using dictionaries:  

color_dic = {
    "D": 1,
    "E": 2,
    "F": 3,
    "G": 4,
    "H": 5,
    "I": 6,
    "J": 7,}  
    
clarity_dic = {
    "IF":   1,
    "VVS1": 2,
    "VVS2": 3,
    "VS1":  4,
    "VS2":  5,
    "SI1":  6,
    "SI2":  7,
    "I1":   8,}  

cut_dic = {
    "Premium":   1,
    "Ideal": 2,
    "Very Good": 3,
    "Fair":  4,
    "Good":  5,}

We created some new columns trying to get better results and we did with the next new columns:
```python df["clar_color"] =(df.clarity*df.color)
df["table_color"] =(df.table*df.cut)
df["table_clarity"] =(df.table*df.clarity)
df["table_/_clarity"] =(df.table/df.clarity)
df["table_clarity_cut"] =(df.table*df.clarity*df.cut)
df["x*y*z"] = (df.x*df.y*df.z)
df["x_/_y"] = (df.x/df.y)
df["x_/_z"] = (df.y/df.z)
df ["all"] = df.carat*df.cut*df.color*df.depth*df.table*df.x*df.y*df.z/7
```

Because we have divisions here we had to check if there were zero on the divisors

## Machine learning alghoritms used

I was a regression problem, but we know the linear regression it is a very simple alghoritm so we went directly 
to choose the tree algorithms that machine learning provides us.
We used it directly a DecisionTreeRegressor, then a RandomForestRegressor and finally we used Grid and Random search.

We executed several time those Grid and Random search Alghoritms, and changing, modifying and creating different columns 
until I found good result.

## Libraries used
pandas[https://pypi.org/project/pandas/] (pip install pandas)  

seaborn https://pypi.org/project/seaborn/]   (pip install seaborn)  

sklearn [https://pypi.org/project/sklearn2/] (pip install sklearn2)  





