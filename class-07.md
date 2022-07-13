# CLASS-07

## DOMAIN MODELING

Domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the several entities, values, their attributes and behaviors. A well articulated domain model can verify and validate our your understanding of the problem.

* **Object oriented model:** Refers to an entity that stores data properties and encapsulates behaviors on methods.

> Tips when building domain models

1. When modeling a single entity that'll have many instances, build self-contained objects with the same attributes and behaviors.
2. Model its attributes with a constructor function that defines and initializes properties.
3. Model its behaviors with small methods that focus on doing one job well.
4. Create instances using the new keyword followed by a call to a constructor function.
5. Store the newly created object in a variable so you can access its properties and methods from outside.
6. Use the `this` variable within methods so you can access the properties of objects and methods from inside.

## HTML TABLES

Tables are various types of information that need to be displayed in a grid format. Like a spreadsheet.

>KEY ELEMENTS FOR CREATING TABLES

* `<table>` Adds tables to the page.
* `<tr>` Creates each row on the table.
* `<td>` Creates the cell inside a row.
* `<th>` Creates a heading cell inside a row.

We cab also use `<thead>`, `<tbody>` and `<tfoot>` to create long tables.

***

## JAVASCRIPT

### OBJECT CONSTRUCTOR NOTATION

We use a combination of `new` keyword and the `Object()` constructors function (e.g)

`let hotel = new Object();`

To update the value of properties we use dot notation. (e.g)

`hotel.name = 'Park';`

>KEYWORD *THIS*

It is commonly used inside functions and objects. Where the functions is declared alters what it means. It refers to one object, usually the one where in which the functions operates.

* **Functions in global scope:** When they are created at the top level of the script. Not inside an object. It's also called **global context.**
* **Global variables:** Can also become properties of the window object. When a function is the global context you can access global variables.

## STORING DATA

Data is represented using name/value pairs. We use **Arrays** or **Objects** to group a set of related values.

* **Variables:** Have just one key and one value. (e.g)

`let hotel = 'Park'`

* **Arrays:** Can store multiple pieces of information (e.g)

`Let hotels = ['Quay' 'Park' 'Beach']`

***

### Things I want to know more about

* Objects Literal and Constructor.

***

[-back](https://alexriverau.github.io/reading-notes/code201)
