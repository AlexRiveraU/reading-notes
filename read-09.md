# Ten Thousand 4

This topic matters as it relates to learning about statistics, probability and how to implement dunder methods in python.

---

## Dunder Methods

Dunder methods (aka magic or special methods) are a set of predefined methods we can use to enrich our classes. They start and end with double underscores. (e.g.) `__init__` or `__str__`.

They let us emulate the behavior of built-in types. For example, to get the length of a string we can call `len('string')`. But an empty class definition doesn’t support this behavior out of the box, so we can add a `__len__` dunder method to the class. (e.g.)

```python
class LenSupport:
    def __len__(self):
        return 42

    obj = LenSupport()
    len(obj)
# 42
```
This design is known as the **Python data model** and allows us to tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

### A few examples:

* `__init__` object constructor
* `__repr__` string representation of an object
* `__str__` string representation of an object nicely printable
* `__len__` returns length of an object
* `__getitem__` gets the value of an item
* `__reversed__` returns a sequence object in reverse order
* `__add__` adds attributes of an object

[*source*](https://dbader.org/blog/python-dunder-methods)

---

## Statistics - Probability

Probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. For example a coin toss, only two events can happen, it can either be heads or tails.

* **Sample space -** The set of all possible events that can happen.

To calculate the probability of an event occurring, we count how many times are event of interest can occur and dividing it by the sample space. To avoid making assumptions we gather data. We use statistics to calculate probabilities based on observations from the real world and check how it compares to the ideal.

* **Three Sigma Rule** 

The Three Sigma rule, aka as the empirical rule or 68-95-99.7 rule, is an expression of how many of our observations fall within a certain distance of the mean.

* **Z-score**

The Z-score is a simple calculation that answers the question, “Given a data point, how many standard deviations is it away from the mean?”

[*source*](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)

---

## Intro to Statistics

Statistics is a collections of procedures and principles for gaining information in order to make decisions when faced with uncertainty.

> Three major concepts

* **Statistical Features** 

Probably the most used statistic concept in data science. Help us explore dataset to gain valuable insights. Like bias, variance and many others. 

* **Probability Distributions**

Define the percent chance that some event will occur, and we can use them to understand the spread of data.

* **Bayesian Statistics**

Expresses probability as a degree of belief in an event which can change as new information is gathered rather than a fixed value based on frequency.


[*source*](https://www.youtube.com/watch?v=MdHtK7CWpCQ)

### AI Guru makes $238,800 with misleading paid course. doesn’t credit developers

Seems like Siraj Raval is yet another public figure that has been corrupted by greed and the twisted obsession of social media status and popularity. It is very unfortunate because he is a talented educator, and could have used his platform in an honest and ethical way to impact a larger number of people in a positive manner.  

[*source*](https://www.youtube.com/watch?v=7jmBE4yPrOs)

---

### Things I want to know more about

* I would like to know more about implementing dunder methods in python and understanding better probability and the three major concepts in statistics. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
