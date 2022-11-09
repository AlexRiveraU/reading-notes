# Pandas

This topic matters as it relates to learning about Pandas and how to implement them to analyze data in Python.

---

## What is pandas

Pandas is a python library with a set of tools to do data analysis. If it involves data we need to know how to use pandas. It uses fast, flexible, and expressive data structures designed to make working with relational or labeled data both easy and intuitive. It allows us to:

* Load data
* Prepare data
* Manipulate data
* Model data
* Analyze data

[*source*](https://www.youtube.com/watch?v=dcqPhpY7tWk&t=391s) 

## Working with pandas

First we need import the pandas package to be able to load it.
```python
In [1]: import pandas as pd
```
Using `pd` is the standard practice for all pandas documentation.

### Data Frame & Series

A `DataFrame` is a 2-dimensional data structure that can store data of different types (including characters, integers, floating point values, categorical data and more) in columns. It is similar to a spreadsheet, a SQL table or the `data.frame` in R. Represented as a table. Each column in a DataFrame is a `Series`. We can do things by applying a method to a `DataFrame` or `Series`.

### Reading and Exporting Data

The `read_csv()` function allows us to read data stored as a csv file into a pandas DataFrame. Pandas support many different file formats or data sources out of the box (csv, excel, sql, json, parquet, etc.), each of them with the prefix `read_*`. To export data out of pandas we use the different `to_*` methods.

There are other methods liek `head`, `tail`, `info` and `dtypes` attribute, that are very convenient for a first check.

### Selecting from a Data Frame

* We use square brackets []. Inside the brackets, we can use a single column / row label, a list of column / row labels, a slice of labels, a conditional expression or a colon. 
* We can select specific rows and / or columns using `loc` when using the row and column names, and `iloc` when using the positions in the table.
* We can assign new values to a selection based on `loc` / `iloc`.

### Creating plots in pandas

We need to import it:

```python
In [1]: import pandas as pd
In [2]: import matplotlib.pyplot as plt
```
The `.plot.*` methods are applicable on both `Series` and `DataFrames`. By default, each of the columns is plotted as a different element (line, boxplot, etc.). Any plot created by pandas is a Matplotlib object.


[*source*](https://pandas.pydata.org/pandas-docs/stable/getting_started/intro_tutorials/index.html)

---

### Things I want to know more about

* I would like to know more about how to implement pandas efficiently to analyze data in Python. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
