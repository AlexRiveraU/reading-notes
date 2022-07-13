# CLASS-06

## UNDERSTANDING PROBLEM DOMAIN

Problem domain is the hardest part of programming. Understanding the problem is the most critical part. It is very difficult to solve a problem before understanding it inside and out.

***

## JAVASCRIPT

### DIFFERENCE BETWEEN PRIMITIVE VALUES AND OBJECT REFERENCES

Data Types in JavaScript can be put in two categories:

* **Primitive Values:** They are **immutable.** When primitive values are assigned to a variable, the variable is set to that value directly. All data types are considered primitive values with the exception of Arrays, Functions and Dates.
  * *Immutable:* Can be changed.
* **Object References:** They are **mutable.** When the variable is assigned with an object, instead of containing the value directly, that variable contains a reference to it. Arrays, Functions and Dates are considered objects.
  * *Mutable:* Cannot be changed.

  *NOTE: const prevents you from reassigning values, but it does not prevent you from mutating existing values.*

### OBJECTS

Objects group together a set of variables and functions to create a model of something you would recognized in the real world. Variables and functions change names when used in objects.

* Variable = **Property**
* Function = **Method**

Example:

let hotel = {
  name: 'Quary',
  rooms: 40,
  booked: 25,
  checkAvailability: function() {
    return this.rooms - this.booked;
  }
}

**DOT NOTATION:** Is the way we use to can access the properties or methods in an object. (e.g.)

let hotelName = hotel.name;

Properties can also be accessed using square brackets `[]`

let hotelName = hotel['name'];

### DOM

The Document Object Model (DOM) specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser windows.

* **DOM Tree:** Model of the web page created once it is loaded by the browser. Is is stored in the browser's memory. Consists of four types of **NODES:**
  1. The Document Node.
  2. Elment Nodes.
  3. Attributes Nodes.
  4. Text Nodes.
* **Selecting Elements:** We use id or class attributes by tag name or CSS selectors syntax.
* **DOM Queries:** Methods that find elements in the DOM tree. DOM Queries my return a single element or a called a NodeList.
* **NodeList:** Collection of Nodes.

**SELECTING AN ELEMENT FROM A NODELIST:**

There are two ways to select an element from a NodeList:

* The item() METHOD
* Array Syntax (Preferred method since it is faster)

Content of element nodes can be accessed and updated using properties like `textContent` and `innerHTML` or using DOM manipulation techniques. Element Nodes can contain multiple text nodes and child elements that are siblings of each other.

***

### Things I want to know more about

* Objects and DOM.

***

[-back](https://alexriverau.github.io/reading-notes/code201)
