# Linear Regressions

This topic matters as it relates to learning about Linear Regressions and how to implement them to analyze data in Python.

---

## How to Run Linear Regression in Python

One of the ways we can use to do linear regression in python is with `scikit learn`.  It is a powerful Python module for machine learning. It contains functions for regression, classification, clustering, model selection and dimensionality reduction. 

* We need to import the library:

```python
import skylearn
```

* To import linear regression we use:

```python
from sklearn.linear_model import LinearRegression
```

Important functions while fitting a linear regression model:

* `lm.fit()` - Fits a linear model 
* `lm.predict()` - Predict Y using the linear model with estimated coefficients 
* `lm.score()` - Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model.
* `.coef_` Gives the coefficients 
* `.intercept_` Gives the estimated intercepts

In practice, we won't implement linear regression on the entire data set, we will have to split the data sets into training and test data sets. So that you train your model on training data and see how well it performed on test data. Scikit learn provides a function called `train_test_split` to do this:

```python
from sklearn.model_selection import train_test_split
```

> Residual Plots 

Residual plots are a good way to visualize errors in our data. If we have done a good job the data should be randomly scattered around line zero. If we see structure in our data, that means our model is not capturing something, we should go back to our model and check our parameters.

[*source*](https://www.crayondata.com/how-to-run-linear-regression-in-python-scikit-learn/) 

---

### Introduction to Simple Linear Regressions

Regression analysis explores the relationship between a quantitative response variable and one or more explanatory variables.

* **Simple linear regression** - It there is only one explanatory variable.
* **Multiple linear regression** - It there is more than one explanatory variable.

When we use a variable to predict another, we call the one we are predicting `y`, and `x` the one we use to predict it. 

[*source*](https://www.youtube.com/watch?v=KsVBBJRb9TE)

---

### Things I want to know more about

* I would like to know more about how to implement linear regression efficiently to analyze data in Python. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
