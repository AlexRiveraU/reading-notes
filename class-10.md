# CLASS-10

## JAVASCRIPT

### ERROR HANDLING & DEBUGGING

JavaScript can be hard to learn and we all make mistakes. In order to find and correct errors is important to understand the **Execution Contexts** and **Variable Scope.**

* **Global Context:** Refers to code that in the script but not in a function.
* **Function Context:** Refers to code that is being run within a function.
* **Global Scope:** When a variable is declared outside a function.
* **Function-Level Scope:** When a variable is declared within a function.

The **Execution Context** has two phases:

1. **Prepare:** Here the new scope is created. Variables, functions and arguments.
2. **Execute:** Here is when it assigns values to variables, references functions, run their code and execute statements.

* **The Stack:** JavaScript processes one line of code a the time. When a statement needs data from another function, it stacks the new function on top of the current task.

>TYPES OF ERRORS

1. **SyntaxError:** Incorrect use of rules of the language.
2. **ReferenceError:** Variable that is not declared or is out of scope.
3. **URIError:** When `/` `?` `&` `#` `:` `;` are not escaped in URIs.
4. **TypeError:** When trying to use an object or method that does not exist.
5. **Error:** Generic template from which all other errors are created.
6. **RangeError:** When we call a function using numbers outside of its accepted range.
7. **NaN:** When performing a math operation using a value that is not a number.

* **Debugging:** It is the process of finding errors. A process of deduction to figure out what the problem is, where is it, the cause of it and how to fix it. We can use **Dev Tools & JavaScript Console** to do this.

* **try, catch, finally:** We can use these statements in advance if we know we may get an error.

***

### Things I want to know more about

* Dev Tools and JavaScript Console.

***

[-back](https://alexriverau.github.io/reading-notes/)
