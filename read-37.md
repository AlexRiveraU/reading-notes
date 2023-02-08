# React 1

This topic matters as it relates to learning about ES6, React, Tailwind CSS, and Next.js.

---

### ES6 Overview

#### ES6 Syntax and Feature Overview

##### Variables and constant feature comparison
* `let` keyword allows for block-scoped variables which cannot be hoisted or redeclared.
* `const` keyword cannot be redeclared or reassigned, but is not immutable.
* **Arrow functions -** shorter way of creating a function expression. don't have their own `this`, don't have prototypes, cannot be used for constructors, and should not be used as object methods.

##### Template literals
* **Concatenation/string interpolation -** expressions can be embedded in template literal strings.
```javascript
let str = `Release Date: ${date}`
```
* **Multi-line strings -** strings can span multiple lines without the need for concatenation.
* **Implicit returns -** `return` keyword is implied and can be omitted if using arrow functions without a block body.
* **Key/property shorthand -** shorter notation for assigning properties to variables of the same name.
* **Method definition shorthand -** the `function` keyword can be omitted when assigning methods on an object.
* **Destructuring (object matching) -** use curly brackets to assign properties of an object to their own variable.
* **Array iteration (looping) -** concise syntax for iteration through arrays and other iterable objects.
* **Default parameters -** functions can be initialized with default parameters, which will be used only if an argument is not invoked through the function.
* **Spread syntax -** can be used to expand an array.

```javascript
let arr1 = [1, 2, 3]
let arr2 = ['a', 'b', 'c']
let arr3 = [...arr1, ...arr2]

console.log(arr3) // [1, 2, 3, "a", "b", "c"]
```

* **Classes/constructor functions -** `class` syntax on top of the prototype-based constructor function.
* **Inheritance -** `extends` keyword creates a subclass.
* **Modules - export/import -** modules can be created to export and import code between files.
* **Promises/Callbacks -** promises represent the completion of an asynchronous function. They can be used as an alternative to chaining functions.

[*source*](https://www.taniarascia.com/es6-syntax-and-feature-overview/)

---

### React

##### JSX

JSX is a syntax extension to JavaScript. React does not require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code.

##### Embedding Expressions in JSX

```javascript
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;
```

##### Rendering an Element into the DOM

To render a React element, first pass the DOM element to `ReactDOM.createRoot()`, then pass the React element to `root.render():`

```javascript
const root = ReactDOM.createRoot(
  document.getElementById('root')
);
const element = <h1>Hello, world</h1>;
root.render(element);
```

##### Updating the Rendered Element

React elements are immutable. Once we create an element, we can’t change its children or attributes. The only way to update the UI is to create a new element, and pass it to `root.render()`.

##### Function and Class Components

The simplest way to define a component is to write a JavaScript function. It has to accept a single `props` (which stands for properties and are `Read-Only`) object argument with data and return a React element, in order to be a valid React component.

We can also use ES6 class to define a component:

```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
Components can also be **rendered**, **composed**, and **extracted**. 

#### State and Lifecycle

##### Converting a Function to a Class
* Create an ES6 class, with the same name, that extends `React.Component`.
* Add a single empty method to it called `render()`.
* Move the body of the function into the `render()` method.
* Replace `props` with `this.props` in the `render()` body.
* Delete the remaining empty function declaration.

##### Adding Local State to a Class
* Replace `this.props.` with `this.state.` in the `render()` method:
* Add a class constructor that assigns the initial `this.state`.

##### Using State Correctly

Three things to know about `setState()`.

* Do Not Modify State Directly
* State Updates May Be Asynchronous
* State Updates are Merged

It's also important to keep in mind that in React the **Data Flows Down**.

##### Handling Events

* React events are named using camelCase, rather than lowercase.
* With JSX you pass a function as the event handler, rather than a string.

##### Passing Arguments to Event Handlers

Inside a loop, it is common to want to pass an extra parameter to an event handler:

```javascript
<button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
<button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
```

[*source*](https://reactjs.org/)

---

### Tailwind CSS

##### Utility-First Fundamentals

Traditionally, whenever we need to style something on the web, we write CSS. With Tailwind, we style elements by applying pre-existing classes directly in our HTML.

```html
<div>
    <div class="text-xl font-medium text-black">ChitChat</div>
    <p class="text-slate-500">You have a new message!</p>
</div>
```

##### Utility classes advantages over inline styles:

* **Designing with constraints.** Using inline styles, every value is a magic number. With utilities, we’re choosing styles from a predefined design system, which makes it much easier to build visually consistent UIs.
* **Responsive design.** We can’t use media queries in inline styles. We can use Tailwind’s responsive utilities to build fully responsive interfaces easily.
* **Hover, focus, and other states.** Inline styles can’t target states like hover or focus. Tailwind’s state variants make it easy to style those states with utility classes.

##### Maintainability concerns

The biggest maintainability concern when using a utility-first approach is managing commonly repeated utility combinations. This can be solved by extracting components and partials, and using editor and language features like multi-cursor editing and simple loops.

[*source*](https://tailwindcss.com/docs/utility-first)

---

### Next.js

##### Next.js: The React Framework

Next.js, is a React Framework with many built-in features:

* An intuitive page-based routing system (with support for dynamic routes)
* Pre-rendering, both static generation (SSG) and server-side rendering (SSR) are supported on a per-page basis
* Automatic code splitting for faster page loads
* Client-side routing with optimized prefetching
* Built-in CSS and Sass support, and support for any CSS-in-JS library
* Development environment with Fast Refresh support
* API routes to build API endpoints with Serverless Functions
* Fully extendable

##### Setup

```commandline
npx create-next-app nextjs-blog
```
* `cd` into `nextjs-blog` directory
* run:

```commandline
npm run dev
```

* Go to [http://localhost:3000](http://localhost:3000) Starter template should be displayed.

##### Editing the Page

* Make sure the Next.js development server is still running.
* Open the file with want to update with our text editor.
* Find what we want edit, and update it.
* Save the file.

Next.js has a **Fast Refresh** feature. When we make changes to files, it automatically applies the changes in the browser almost instantly. No need to refresh.

[*source*](https://nextjs.org/learn/basics/create-nextjs-app)

---

### Things I want to know more about

* I would like to know more about implementing React and Next.js.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
