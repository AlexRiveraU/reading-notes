# Ten Thousand Game 1

This topic matters as it relates to learning the use of the Random Module in Python, how to perform risk analysis in software testing, test coverage and Big O Notation.

---

## How to use Random Module

The random module provides access to functions that support many operations and allows us to generate random numbers. It contains some very useful functions:

* **Randint:** Generates a random integer. Takes in two parameters (lowest and highest number). (e.g.)
```python
import random
print random.randint(0, 5)
# output either 1, 2, 3, 4 or 5.
```

* **Random:** Multiplies to get a larger number. (e.g.)
```python
import random
random.random() * 100
```

* **Choice:** Generates a random value from a sequence. Like a list. (e.g.)
```python
import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)
```

* **Shuffle:** Shuffles the elements in list in place, so they are in a random order. (e.g.)
```python
from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)
# Output:
# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
# of course your results will vary
```

* **Randrange:** Generates a randomly selected element from range (start, stop, step).
```python
random.randrange(start, stop[, step])
import random
for i in range(3):
    print random.randrange(0, 101, 5)
```

[*source*](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)

---

## What is Risk Analysis

In software testing risk analysis is the process of identifying the risks in applications we build prioritizing them to test. Using risk analysis at the beginning of a project highlights the potential problem areas helping us to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to our software along with solutions.

>Possible risks

* Use of new hardware
* Use of new technology
* Use of new automation tool
* The sequence of code
* Availability of test resources for the application

>Unavoidable risks

* Time allocated for testing 
* A defect leakage due to the complexity or size of the application 
* Urgency from the clients to deliver the project 
* Incomplete requirements

### Risk Identification

* **Business Risks:** It is the risk that may come from our company or our customer, not from your project.
* **Testing Risks:** We should be well acquainted with the platform we are working on, along with the software testing tools being used.
* **Premature Release Risk:** Risk associated with releasing unsatisfactory or untested software.
* **Software Risks:** We should be well versed with the risks associated with the software development process.

### Risk Assessment

In the risk analysis process. The most important one. It has to be dealt programmatically.

>Perspective of Risk Assessment

* **Effect** When we identify a condition, event or action and try to determine its impact.
* **Cause** Initialize scanning the problem and reach to the point that could be the most probable reason behind that.
* **Likelihood** When we say that there is a probability that a requirement won’t be satisfied.

>Perform Risk Analysis 

* Searching the risk.
* Analyzing the impact of each individual risk.
* Measures for the risk identified.

[*source*](https://www.edureka.co/blog/risk-analysis-in-software-testing/)

---

## Test Coverage

Test coverage (aka code coverage) is a useful tool for finding untested parts of a codebase. Testing requires thoughtfulness. TDD is a very useful tool to help us get good tests, but sometimes we need to do more. If we are testing correctly we would expect a coverage percentage in the upper 80s or 90s. Anything like 100% would be suspicious, like if someone is writing tests to make the coverage numbers look good, but not thinking about what they are doing. Doing enough testing means:

* We rarely get bugs that escape into production.
* We're rarely hesitant to change some code for fear it will cause production bugs.

[*source*](https://martinfowler.com/bliki/TestCoverage.html)

---

## Big O Notation

Big O notation is used in Computer Science to describe the performance or complexity of an algorithm. It specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used by an algorithm.

* **O(1)** Describes an algorithm that will always execute in the same time or space regardless of the size of the input data set.
* **O(N)** Describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set.
* **O(N²)** Represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N³), O(N⁴) etc.
* **O(2^N)** Denotes an algorithm whose growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential.
 
[*source*](https://www.youtube.com/watch?v=v4cd1O4zkGw)

---

### Things I want to know more about

* I would like to know more about Big O Notation and how to use the Random Module in Python

---

[-back](https://alexriverau.github.io/reading-notes/code401)
