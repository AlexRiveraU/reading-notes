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

Nonlocal names can be accessed from inner functions, but not assigned or updated. To modify this behavior, we can use a nonlocal statement. We use the `nonlocal` keyword followed by one or more names separated by commas. (e.g.)

```python
def func():
    var = 100  # A nonlocal variable
    def nested():
        nonlocal var  # Declare var as nonlocal
        var += 100

    nested()
    print(var)

func()
```

* `globals()`: built-in function that returns a reference to the current global scope or namespace dictionary. We get a dictionary containing all the names that we’ve defined in the module, right before the call to globals(). (e.g.)

```python
globals()
{'__name__': '__main__',..., '__builtins__': <module 'builtins' (built-in)>}
```

* `locals()`: built-in function that updates and returns a dictionary that holds a copy of the current state of the local Python scope or namespace. We get all the names assigned in the local or function scope up to the point where you call locals(). (e.g.)

```python
def func(arg):
    var = 100
    print(locals())
    another = 200

func(300)
# {'var': 100, 'arg': 300}
```

[*source*](https://realpython.com/python-scope-legb-rule/)



---

### Things I want to know more about

* I would like to know more about the LEGB rule and how to implement it correctly in Python.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
