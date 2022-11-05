# Data Analysis

This topic matters as it relates to learning about NumPy data analysis package for python, and how to use Jupyter.

---

## What is Jupyter Lab

JupyterLab enables us to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner. It allows us to arrange multiple documents and activities side by side in the work area using tabs and splitters. Documents and activities integrate with each other, enabling new workflows for interactive computing. It supports many formats, and we can also add extensions or libraries.

>Jupyter Features
 
* Text Editor  
* Code Console 
* Terminals

>Common Formats
 
* Supports `.pdf` `.html` `.tex` and all popular image formats as stand-alone files in notebooks.
* We can also edit `.json` files. 


>Jupyter Notebooks

New way to work easily with data and code together. It has two modes:

* **command:**  

Navigates and changes the framework of our notebook. The framework is composed of cells. Keeps the data in little containers. There are a variety of shortcuts we can use for easier navigation. 

* **edit:** 

We use it to edit the active cell with Markdown. We can also run code on each cell using Kernels (programming languages) and the output is put right back under the cell.

[*source*](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)

---

## Numpy Tutorial

NumPy is a commonly used Python data analysis package. It allows us to speed up our workflow, and interface with other packages in the Python ecosystem.

#### Numpy 2-Dimensional Arrays

With NumPy, we work with multidimensional arrays. A 2-dimensional array is also known as a matrix, and is something you should be familiar with. In fact, it’s just a different way of thinking about a list of lists. A matrix has rows and columns. By specifying a row number and a column number, we’re able to extract an element from a matrix.

In a NumPy array, the number of dimensions is called the `rank`, and each dimension is called an `axis`. So the rows are the first axis, and the columns are the second axis.

#### Creating A NumPy Array

We can create a NumPy array using the `numpy.array` function. If we pass in a list of lists, it will automatically create a NumPy array with the same number of rows and columns. All the elements in an array have to be of the same type be floats. (e.g.)

```python
import csv
with open("winequality-red.csv", 'r') as f:
    wines = list(csv.reader(f, delimiter=";"))
import numpy as np
wines = np.array(wines[1:], dtype=np.float)
```

We can use the `numpy.genfromtxt` function to read csv or other files into arrays. (e.g.)

```python
wines = np.genfromtxt("winequality-red.csv", delimiter=";", skip_header=1)
```

We can use array indexing to select individual elements, groups of elements, or entire rows and columns.

**Slice:** We use colon `(:)` to indicate we want to select all the elements from the starting index up to but not including the ending index.

#### Dimensional NumPy Arrays

NumPy is a package for working with multidimensional arrays and one of the most common types of multidimensional arrays is the 1-dimensional array, or vector.

#### NumPy Data Types

NumPy stores values using its own data types. NumPy is written in C, which stores data differently than the Python data types. NumPy data types map between Python and C, allowing us to use NumPy arrays without any conversion hitches.  We use `dtype` to find the data type of a NumPy array.

**A few important NumPy data types:** 

* `float` — numeric floating point data.
* `int` — integer data.
* `string` — character data.
* `object` — Python objects.

#### NumPy Array Operations

NumPy makes it simple to perform mathematical operations on arrays. Using basic mathematical operations `(/, *, -, +, ^)` with an array and a value, applies the operation to each of the elements in the array. We can also do mathematical operations between arrays.

We use the `numpy.ndarray.astype` method to convert an array to a different type. The method will actually copy the array, and return a new array with the specified data type.

#### Broadcasting

Broadcasting to try to match up elements. Involves a few steps:

* The last dimension of each array is compared.
  * If the dimension lengths are equal, or one of the dimensions is of length 1, then we keep going.
  * If the dimension lengths aren’t equal, and none of the dimensions have length 1, then there’s an error.
* Continue checking dimensions until the shortest array is out of dimensions.

#### NumPy Array Methods

* `numpy.zeros` - creates an array where every element is zero.
* `numpy.random.rand` - creates an array where each element is a random number.
*  `numpy.ndarray.sum` - finds the sum of all the elements in an array by default.

#### NumPy Array Comparisons

NumPy makes it possible to test to see if rows match certain values using mathematical comparison operations like `<`, `>`, `>=`, `<=`, and `==`. 

We can use `numpy.transpose` to reshape NumPy arrays by flipping the axes, so rows become columns, and vice versa. We can use `numpy.vstack` to vertically stack multiple arrays.

[*source*](https://www.dataquest.io/blog/numpy-tutorial-python/)

---

### Things I want to know more about

* I would like to know more about how to use Jupyter efficiently and how to implement NumPy in python. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
