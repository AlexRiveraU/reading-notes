# CLASS-04

## HTML LINKS

Links are created using the `<a>` element and the `href` attribute. (e.g.)

`<a href="https://www.imdb.com/">IMDB</a>`

In that example [IMDB]("https://www.imdb.com/") becomes the link.

* **Absolute URLS:** A Uniform Resource Locator (URL) is the web address we type on a browser to visit a site. We need to specify the domain name.
* **Relative URLS:** A shorthand version of absolute urls. We don't need to type the domain name. We use them to link pages within the same site.

**EMAIL LINKS:** We use `mailto` inside the `<a>` tag. (e.g)

`<a href="mailto:jon@example.org">Email Jon</a>`

**NEW WINDOW LINKS:** We use `target` when we want the link to open in a new window. (e.g)

`<a href="https://www.imdb.com/" target="_blank">IMDB</a>`

**LINK TO A SECTION OF SAME PAGE:** We use the `ID attribute` to specify the point in the page we want to link to and we use `#` inside the `<a>`tag. (e.g)

`<a href=#"top">`

---

## CSS LAYOUT

CSS treats each HTML element as its own box, block-Level or inline-Level. It has the following positioning schemes to control the layout:

* **Normal Flow:** Every block-level element appears in a new line.
* **Relative Positioning:** Moves the element from where it would have been in normal flow.
* **Absolute Positioning:** Positions the element in relation to its containing element. It moves as the user scrolls up or down.
* **Fixed Positioning:** Similar to absolute positioning but positions the element in relation to the browser window instead. It does not move when the user scrolls up or down.
* **Floating Elements:** Takes element out of normal flow and position it to the far left or right of the a containing box.

---

## JAVASCRIPT FUNCTIONS

Functions are a series of statements grouped together to perform a specific task. They can be reused in different parts of the script.

>DECLARING A FUNCTION:

We have to name it and write the statements needed as a code block for it to perform its task.

`function sayHello() {
  document.write('Hello!')
}`

* **Calling:** When we ask the function to perform its task. We use its name, parentheses & semicolon at the end. (e.g)

  * `sayHello();`

* **Parameters:** Pieces of information that some functions need to perform a task. We added like a variable after function's name (e.g.)

  * `function getArea(width, height) {
      return width * height;
    }`

* **Arguments:** The specific values we can assign to the parameters. (e.g.)

  * `getArea(3, 5);`

* **Return Value:** The answer expected from a functions after performing its tasks. The response is returned to the code that called it. We can create variables inside a function to achieve this:

  * `function calculateArea (width, height) {
      var are = width * height
      response area;
    }`

* **Variable Scope:** The locations where a variable is declared:

  * Local Variable: Variables created inside the function.
  * Global Variable: Variables created outside the function.

**ANONYMOUS FUNCTIONS:** Functions can work withoUt naming them. If we put the function where the interpreter would expect to see an expression, it is treated as an expression.

**IMMEDIATELY INVOKED FUNCTION EXPRESSIONS (IIFE):** This is when functions without a name are executed the moment the moment the interpreter comes across them.

---

### PAIR PGROGRAMMING

Pair programming is the practice of two developers sharing a single workstation to interactively work on a coding task together. It involves two roles:

* **Driver:** Programmer that types.
* **Navigator:** Programmer that guides the driver. Using only their words.

### Things I want to know more about

* Understanding functions better.

---

[-back](https://alexriverau.github.io/reading-notes/)
