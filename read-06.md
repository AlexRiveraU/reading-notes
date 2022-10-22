# Ten Thousand 2

This topic matters as it relates to learning about modifying the behavior of a Python scope using the `global` and `nonlocal` keywords.

---

## Python Scope

The concept of scope rules how variables and names are looked up in our code. It determines the visibility of a variable within the code. The Python scope concept is generally presented using a rule known as the LEGB (Local, Enclosing, Global, and Built-in) rule.

* **Global scope:** The names defined in this scope are available to all our code.
* **Local scope:** The names defined in this scope are only available or visible to the code within the scope. 

The moment we start a Python program, we’re in the global scope. Internally, Python turns our program’s main script into a module called __main__ to hold the main program’s execution. The namespace of this module is the main global scope of our program.

`dir()` When we call it we get the list of names available in your main global scope. (e.g.)

```python
dir()
['__annotations__', '__builtins__',..., '__package__', '__spec__']
```

### Modifying the Behavior of a Python Scope

Python provides two keywords that allows us to modify the content of global and nonlocal names:

1. global
2. nonlocal

>The global Statement

To assign a value to a global name inside a function, we create a new local name in the function scope. To modify this behavior, we can use a global statement. We use the `global` keyword followed by one or more names separated by commas. (e.g.)

```python
counter = 0  # A global name
def update_counter():
    global counter  # Declare counter as global
    counter = counter + 1  # Successfully update the counter
```

***Note:** The use of global is considered bad practice in general.*

>The nonlocal Statement

Nonlocal names can be accessed from inner functions, but not assigned or updated. To modify this behavior, we can use a nonlocal statement. With a nonlocal statement, we can define a list of names that are going to be treated as nonlocal.

[*source*](https://realpython.com/python-scope-legb-rule/)



---

### Things I want to know more about

* I would like to know more about Big O Notation and how to use the Random Module in Python

---

[-back](https://alexriverau.github.io/reading-notes/code401)
