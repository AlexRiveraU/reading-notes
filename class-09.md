# CLASS-09

## HTML FORMS

Forms allows us to collect information from visitors to our site.

>FORM CONTROLS

* **Adding Text:**
  1. Text input (single-line)
  2. Password input
  3. Text area (multi-line)
* **Making Choices:**
  1. Radio Buttons
  2. Checkboxes
  3. Drop-down boxes
* **Submitting Forms:**
  1. Submit Buttons
  2. Image buttons
  3. File upload
  
*Forms send the informaction to the servers in **name/value** pairs.*

**We use the following elements:**

* `<form>` Controls live inside.
* `<action>` Its value is the URL for the page on the server that will receive the information.
* `<method>` It should be `get` or `post.`
* `<input>` It creates several controls. (needs `type` `name` and their values.)
* `<textarea>` Creates multi-line text.
* `<select>` Creates drop down list box.
* `<option>` Specifies the options in the drop down list.
* `<button>` Creates a button.
* `<label>` Makes the form accessible to vision-impaired users.
* `<fieldset>` Groups related form controls together.
* `<legend>` Used after `<fieldset>` and contains a caption to identify the purpose of that group.

***

## CSS LISTS, TABLES AND FORMS

* **Bullet Point Styles:** We use the `list-style` property.
* **Image For Bullets:** We use the `list-style-image` property and the value starts with a `url.`
* **Positioning The Marker:** We use the `list-style-position` property.
* **Table Properties:** width, padding, text-transform, letter-spacing, font-size, border-top, border-bottom, text-align, background-color, :hover.
* **Border Empty Cells:** We use the `empty-cells` property.
* **Cursor Styles:** We use the `cursor` property.

***

## JAVASCRIPT EVENTS

Browsers register different types of events that make the script respond by updating the page via DOM:

1. User interactions create events.
2. Events trigger code.
3. Code respond to users.

*When events occur is described as being **fired** or **raised.***
*Events **trigger** a function or script.

>TYPES OF EVENTS

* **UI Events:** When users interact with the browser.
* **Keyboard Events:** When users interact with the keyboard.
* **Mouse Events:** When users interact with the mouse.
* **Focus Events:** When an element gains or loses focus.
* **Form Events:** When users interact with a form element.
* **Mutation Events:** When the DOM structure has been changed by a script.

**EVENT HANDLING:** Refers to the user interaction with the html of a page involving three steps that trigger the code:

1. Select the **element** node(s) we want the script to respond to.
2. Indicate which **event** on the selected node(s) will trigger the response. Also known as **binding.**
3. State the **code** we want to run.

### WAYS TO BIND AN EVENT TO AN ELEMENT

* **HTML Event Handlers:** *It is bad practice now days. May find it in older code.*
* **Event Handlers:** Triggers a single function.
* **Event Listeners:** Triggers multiple functions.

>EVENT FLOW

HTML Elements nest inside other elements. If you click on a link you will also be clicking on its parents elements.

* **Event Bubbling:** The event starts at the most specific node and flows outwards to the least specific.
* **Event Capturing:** The event starts at the least specific node and flows inwards to the most specific.

**DELEGATION:** It can be used to monitor for events that happen on all of the children of an element.

***

### Things I want to know more about

* The complexities of Event Handling.

***

[-back](https://alexriverau.github.io/reading-notes/)