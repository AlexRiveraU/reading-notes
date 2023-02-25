# Pythonisms

This topic matters as it relates to learning about Pythonisms and how to implement them.

---

### Dunder Methods

Dunder methods aka 'special methods' or 'magic methods', are a set of predefined methods we can use to enrich classes. Start and end with double underscores. They let us emulate the behavior of built-in types. For example:

 * Object Representation: `__str__`, `__repr__`
 * Iteration: `__len__`, `__getitem__`, `__reversed__`
 * Operator Overloading for Comparing Objects: `__eq__`, `__lt__`
 * Operator Overloading for Merging Objects: `__add__`
 * Callable Python Objects: `__call__`
 
```python
class Account:
    
    def __init__(self, owner, amount=0):
        self.owner = owner
        self.amount = amount
        self._transactions = [] 

    def __len__(self):
        return len(self._transactions)

    def __getitem__(self, position):
        return self._transactions[position]

    def __eq__(self, other):
        return self.balance == other.balance

    def __lt__(self, other):
        return self.balance < other.balance
```

[source](https://dbader.org/blog/python-dunder-methods)

---

### Iterators

Class-based iterators are only one way to write iterable objects in Python, they provide a sequence interface to objects that’s memory efficient and considered Pythonic. The object needs to implement the iterator protocol by providing the `__iter__` and `__next__` dunder methods. For example:

```python
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return RepeaterIterator(self)
```

* The `RepeaterIterator` object is a helper class we also need to define:

```python
class RepeaterIterator:
    def __init__(self, source):
        self.source = source

    def __next__(self):
        return self.source.value
```

[source](https://dbader.org/blog/python-iterators)

---

### Generators

Generators are a more convenient way to write python iterators. They have a shorter and easier syntax thant class-based iterators. Instead of using `return` they use `yield` to pass data back to the caller. For example:

```python
class Repeater:
    def __init__(self, value):
        self.value = value

    def __iter__(self):
        return self

    def __next__(self):
        return self.value
```

The Repeater class can be refactored as a class generator like this:

```python
def repeater(value):
    while True:
        yield value
```

* `return` disposes of a function’s local state 
* `yield` suspends the function and retains its local state
* `StopIteration` exception is raised after control flow leaves the generator function by any means other than a `yield` statement.

[source](https://dbader.org/blog/python-generators)

---

### Things I want to know more about

- I would like to know more about how to implement iterators and generators efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
