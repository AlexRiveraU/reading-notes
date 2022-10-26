# Ten Thousand 3

This topic matters as it relates to learning how to implement list comprehensions in python to keep our code more compact and readable. 

---

## List Comprehensions

List comprehension is a powerful and concise method for creating lists in Python. It's an elegant and more compact way to create and manage lists, more flexible than for loops and faster than other methods. **Syntax:**

1. `expression` inside the square brackets.
2. `item` inside the square brackets.
3. `list` inside the square brackets.

### Code examples

>Create a List

```python
squares = [x**2 for x in range(10)]
print(squares)
# output
# [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

>Multiplying Parts of a List

```python
multiples_of_three = [ x*3 for x in range(10) ]
print(multiples_of_three)
# output
# [0, 3, 6, 9, 12, 15, 18, 21, 24, 27]
```

>Show the first letter of each word

```python
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

letters = [ name[0] for name in authors ]
print(letters)
# output
# ['E', 'L', 'F', 'T', 'E', 'S']
```

>Lower/Upper case converter

```python
lower_case = [ letter.lower() for letter in ['A','B','C'] ]
upper_case = [ letter.upper() for letter in ['a','b','c'] ]
print(lower_case, upper_case)
# output
# ['a', 'b', 'c'] ['A', 'B', 'C']
```

>Using functions

```python
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)
# output
# [2, 4, 6, 8, 10, 12, 14, 16, 18]
```

[*source*](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

---

### Things I want to know more about

* I would like to know more about features like list comprehension in python to be able to write more compact and readable code.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
