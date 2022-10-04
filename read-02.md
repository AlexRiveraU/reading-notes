# Testing and Modules

This topic matters as it relates to learning proper testing practices, modules and recursion in python.

---

## In Tests We Trust - TDD with Python

Test-Driven Development (TDD) is a strategy to think and write tests first. More than any checking, it's about crafting our software design first.

Unit tests are some pieces of code to exercise the input, the output and the behavior of your code. (e.g)
```python
def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run('Ana')
    assert expected_gender == 'female'
```
* The *test name* should be descriptive about its purpose.
* The *test file* name should follow the same name of module name.

>Structure

**Arrange, Act and Assert (AAA)**
* **Arrange:** Organize the data needed to execute that piece of code.
* **Act:** Execute the code being tested.
* **Assert:** Check if the result is what we expected.

>The Cycle

1. Write a unit test and make it fail.
2. Write the feature and make the test pass.
3. Refactor the code.

[*source*](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)

---

## If name equals main

```python
if __name__ == '__main__':
```
The Python interpreter reads the source file and define few special variables/global variables. 
* If the interpreter is running that module (the source file) as the main program, it sets the special `__name__` variable to have a value `'__main__'`. 
* If the file is being imported from another module, `__name__` will be set to the module’s name. Module’s name is available as value to `__name__` global variable. 

**Module:** File containing Python definitions and statements. The file name is the module name with the suffix `.py` appended. To execute we use the command: `python script.py`

[*source*](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)

---

## Recursion

Recursion is the process in which a function calls itself directly or indirectly. The corresponding function is called a recursive function. It solves a particular problem by calling a copy of itself and solving smaller sub-problems of the original problem. We must provide a certain case in order to terminate this recursion process.

**Properties:**
1. Performing the same operations multiple times with different inputs.
2. In every step, we try smaller inputs to make the problem smaller.
3. Base condition is needed to stop the recursion otherwise infinite loop will occur.

**Memory:**

Recursion uses more memory because it adds to the stack with each recursive call, and keeps the values there until the call is finished. It uses LIFO (LAST IN FIRST OUT) Structure just like the stack data structure.

**Base case:**

If the base case is not reached or not defined, then the stack overflow problem may arise. (e.g)

```python
int fact(int n)
{
    // wrong base case (it may cause
    // stack overflow).
    if (n == 100) 
        return 1;

    else
        return n*fact(n-1);
}
```
* **Direct Recursion:** It calls the same function.
* **Indirect Recursion:** It calls another function.

>Recursion vs Iteration

**Recursion**
1. Terminates when the base case becomes true. 
2. Used with functions.
3. Every recursive call needs extra space in the stack memory.
4. Smaller code size.

**Iteration**
1. Terminates when the condition becomes false.
2. Used with loops.
3. Every iteration does not require any extra space.
4. Larger code size.

[*source*](https://www.geeksforgeeks.org/introduction-to-recursion-data-structure-and-algorithm-tutorials/)

In order for recursion to work properly each operation gets stacked in memory. It's also important to know that each operation holds a different value of the variable each time. Professor Brailsford explained it using factorials and `n` emphasizing this aspect.

[*source*](https://www.youtube.com/watch?v=Mv9NEXX1VHc)

---

### Things I want to know more about

* I would like to know more about recursion in practice and how to implement TDD strategies efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
