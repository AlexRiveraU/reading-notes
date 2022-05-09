# CLASS-03

## HTML LISTS

There are three types of lists in html:

* **Ordered lists:** Where each item in the list is numbered.
  * \<ol> \<li>
* **Unordered lists:** Lists that begin with a bullet point or similar characters.
  * \<ul> \<li>
* **Definition lists:** Lists made of a set of terms with their definitions.
  * \<dl> \<dt> \<dd

Lists can be nested by putting a second list inside an \<li>

---

## CSS BOXES

There are several properties that change the appearance of html boxes using CSS:

* **Box Dimensions:** Can be adjusted using **width** & **height** specifying whether in pixels, percentages or ems.
* **Limiting width:** This is to make the page expand or shrink to fit the user's screen using:
  * min-width
  * max-width
* **Limiting height:** Same as limiting width but using:
  * min-height
  * max-height
* **Overflow:** Tells the browser what to do if the content within a box is larger than the box itself. There are two values for this:
  * hidden: Hides the extra content.
  * scroll: Adds a scroll bar to the box.
* **Border:** Separates the edge from one box to another. Width, color & style of a border can be changed.
* **Margin:** Creates a gap between the border of two boxes. Sits outside the edge of a border.
  * CENTERING CONTENT: Set left-margin and right-margin to auto.
* **Padding:** Space between the border and the contents of a box. *Margin and Padding together help with white space in a box.*
* **Display:** Turns an inline element into a block-level element or vice versa.
* **Visibility:** Hides boxes but leaves the space it would have been.
* **Border-image:** Applies an image to the border of any box. Slices the images into nine pieces.
* **Box-shadow:** Adds a drop shadow around the box.
* **Border-radius:** Creates rounded corners on any box.

---

## JAVASCRIPT

### IF ELSE STATEMENTS

If...else statements check a condition, if it resolves to true the first code block is executed. If it is false the second block runs instead.

if (score >= 50) {
  congratulate();
}
else {
  encourage();
}

### SWITCH STATEMENTS

Starts with the variable **switch value** and allows you to compare a value against possible outcomes and provides a default option.

switch (level) {
  case 'one':
  title = 'Level 1';
  break;

  case 'two':
  title = 'Level 2';
  break;

  case 'three':
  title = 'Level 3';
  break;

  default:
  title = 'Test';
  break;
}

**COERCION:** When data types are converted into another to complete an operation.

>DATA TYPES:

* **string:** Text
* **number:** Number
* **Boolean:** true or false
* **null:** Empty value
* **undefined:** Variable has been declared but not assigned a value.

**TRUTHY AND FALSY:** Due to coercion every value can be treated as true or false. (e.g) Falsy values can be treated as the number 0 and Truthy as 1.

### LOOPS

Loops check a condition, if it returns true, a code block will run. Then it checks if it still returns true, runs the code again, repeating until the conditions returns false. There are three types of loops:

* **For:** Used when you need to run the code a specific number of times.
* **While:** Used if you don't know how many times the code should run.
* **Do While:** Similar to the "while" statement but it runs the code at least once even if the condition evaluates to false.

if (var i = 0; i < 10; i++) {
  document.write(i);
}

---

### Things I want to know more about

* Switch Statements and Loops.

---

[-back](https://alexriverau.github.io/reading-notes/)