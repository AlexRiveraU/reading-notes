# Classes and Objects / Thinking Recursively

This topic matters as it relates to learning how to implement classes and objects, as well as thinking recursively in Python.

---

## Classes and Objects

* **Objects:** 

They are an encapsulation of variables and functions into a single entity. They get their variables and functions from classes. 

* **Classes:** 

They are essentially a template to create your objects. (e.g.)

```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")
```

To assign a class to an object we basically assign it to a variable. (e.g)

```python
myobjectx = MyClass()
```

>Accessing Object Variables

To access the variable inside an object we use dot notation. (e.g)

```python
myobjectx.variable
```
We can also create a different object of the same class and change its variable. (e.g.)

```python
myobjecty = MyClass()

myobjecty.variable = "yackity"
```

>Accessing Object Functions

To access a function inside an object we also use dot notation. (e.g.)

```python
myobjectx.function()
```

* **init()**

The `__init__()` function, is a special function that is called when the class is being initiated. It's used for assigning values in a class. (e.g.)

```python
class NumberHolder:

   def __init__(self, number):
       self.number = number
```

[*source*](https://www.learnpython.org/en/Classes_and_Objects)

---

## Thinking Recursively

* **Iterative algorithm:** An iterative algorithm will use looping statements such as for loop or while loop to repeat the same steps. (e.g.)

* **Recursive algorithm:** In a recursive algorithm a module (function) calls itself again and again until the base condition is satisfied. (e.g.)

### Recursive Functions in Python

A recursive function is a function defined in terms of itself via self-referential expressions. The function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts: **base case** and **recursive case.** (e.g.)

```python
def factorial_recursive(n):
    # Base case: 1! = 1
    if n == 1:
        return 1

    # Recursive case: n! = n * (n-1)!
    else:
        return n * factorial_recursive(n-1)
```

### Maintaining State

When dealing with recursive functions, each recursive call has its own execution context, to maintain state during recursion we have to either:

- Thread the state through each recursive call so that the current state is part of the current call’s execution context. We do this by passing the updated current state to each recursive call as arguments. (e.g.)

```python
def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)
```

- Keep the state in global scope. (e.g.)

```python
# Global mutable state
current_number = 1
accumulated_sum = 0


def sum_recursive():
    global current_number
    global accumulated_sum
    # Base case
    if current_number == 11:
        return accumulated_sum
    # Recursive case
    else:
        accumulated_sum = accumulated_sum + current_number
        current_number = current_number + 1
        return sum_recursive()
```

### Recursive Data Structures in Python

A data structure is recursive if it can be defined in terms of a smaller version of itself. For example a list, set, tree, dictionary, etc. (e.g.)

```python
# Return a new list that is the result of
# adding element to the head (i.e. front) of input_list
def attach_head(element, input_list):
    return [element] + input_list
```

1. Starting with an empty list, you can generate any list by recursively applying the `attach_head` function.
2. Recursion can also be seen as self-referential function composition. We apply a function to an argument, then pass that result on as an argument to a second application of the same function, and so on. Repeatedly composing `attach_head` with itself is the same as `attach_head` calling itself repeatedly.

### Naive Recursion is Naive

`lru_cache` is a `decorator` that caches the results to avoid re-computation by explicitly checking for the value before trying to compute it. The positional and keyword arguments to the function must be hashable. (e.g)

```python
from functools import lru_cache

@lru_cache(maxsize=None)
def fibonacci_recursive(n):
    print("Calculating F", "(", n, ")", sep="", end=", ")

    # Base case
    if n == 0:
        return 0
    elif n == 1:
        return 1

    # Recursive case
    else:
        return fibonacci_recursive(n-1) + fibonacci_recursive(n-2)
```

[*source*](https://realpython.com/python-thinking-recursively/)

---

## Pytest Fixtures and Coverage

* **Fixtures:** This is when we have objects available to all of ours tests and those objects might contain data we want to share across tests, or they might involve the network or filesystem. We use the `pytest.fixture` decorator along with a function.

* **Coverage:** Checks that our tests have run all the code.

---

### Things I want to know more about

* I would like to know more about maintaining state in recursive functions and implementing recursive data structures in python.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
