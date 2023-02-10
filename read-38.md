# React 2

This topic matters as it relates to continue learning about React and its implementation.

---

### Conditional Rendering

We can create components that encapsulate the behavior we need and render only some of them. Conditional rendering uses conditional operators the same way as conditions in JavaScript.

```JavaScript
function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;
  if (isLoggedIn) {
    return <UserGreeting />;
  }
  return <GuestGreeting />;
}
```

#### Element Variables

We can use variables to store elements to help us conditionally render a part of the component while the rest of the output doesn’t change. Declaring a variable and using an `if` statement is a fine way to conditionally render a component.

```JavaScript
ender() {
    const isLoggedIn = this.state.isLoggedIn;
    let button;
    if (isLoggedIn) {
      button = <LogoutButton onClick={this.handleLogoutClick} />;
    } else {
      button = <LoginButton onClick={this.handleLoginClick} />;
    }
```

#### Inline If with Logical && Operator

We can embed expressions in JSX by wrapping them in curly braces. JavaScript logical `&&` operator comes in handy for conditionally including an element. JavaScript, `true && expression` always evaluates to expression, and `false && expression` always evaluates to false. If the condition is true, the element right after `&&` will appear in the output. If it is false, React will ignore and skip it.

```JavaScript
<div>
  <h1>Hello!</h1>
  {unreadMessages.length > 0 &&
    <h2>
      You have {unreadMessages.length} unread messages.
    </h2>
  }
</div>
```

#### Inline If-Else with Conditional Operator

We can also use the JavaScript conditional operator `condition ? true : false`. Whenever conditions become too complex, it might be a good time to extract a component.

```JavaScript
<div>
  {isLoggedIn
    ? <LogoutButton onClick={this.handleLogoutClick} />
    : <LoginButton onClick={this.handleLoginClick} />
  }
</div>
```

#### Preventing Component from Rendering

We can also hide components and prevent them from rendering. We just need to return `null` instead of its render output. It does not affect the firing of the component’s lifecycle methods.

[_source_](https://reactjs.org/docs/conditional-rendering.html)

---

### Lists and Keys

#### Rendering Multiple Components

We can build collections of elements and include them in JSX using curly braces `{}`. We loop through an array using the JavaScript `map()` function and return a `<li>` element for each item, assign the resulting array to a variable, and include it inside a `<ul>` element.

#### Basic List Component

We usually render lists inside a component. We must use a `key`, which is a special string attribute we need to include when creating lists of elements.

```JavaScript
function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li key={number.toString()}>
      {number}
    </li>
  );
  return (
    <ul>{listItems}</ul>
  );
}
```

#### Keys

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity. We should use a string that uniquely identifies a list item among its siblings. We often use `IDs` from our data as keys. When we don’t have stable IDs for rendered items, we may use the item index as a key, but it is not recommended if the order of items may change. It can negatively impact performance and may cause issues with component state.

```JavaScript
const todoItems = todos.map((todo) =>
  <li key={todo.id}>
    {todo.text}
  </li>
);
```

- Rule of thumb. Elements inside the `map()` call need keys.
- Keys Must Only Be Unique Among Siblings.
- They don’t need to be globally unique.
- Keys serve as a hint to React but they don’t get passed to your components.
- We can pass them explicitly as a `prop` with a different name.

#### Embedding map() in JSX

JSX allows embedding any expression in curly braces so we could inline the `map()` result. It helps for a clearer code. If the `map()` body is too nested, it might be a good time to extract a component.

[_source_](https://reactjs.org/docs/lists-and-keys.html)

---

### Forms

Form elements naturally keep some internal state. It is convenient to have a JavaScript function that handles the submission of the form and has access to the data that the user entered into the form. The standard way to achieve this is with a technique called “controlled components”.

#### Controlled Components

In HTML, form elements typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with `setState()`. React state is the “single source of truth”. The component that renders a form also controls what happens in that form on subsequent user input. An input form element whose value is controlled by React in this way is called a “controlled component”. With a controlled component, the input’s value is always driven by the React state.

The tags `<input type="text">`, `<textarea>`, and `<select>` all work very similarly, they all accept a value attribute that we can use to implement a controlled component.

The `<input type="file">` lets the user choose one or more files from their device storage to be uploaded to a server or manipulated by JavaScript via the File API. Because its value is read-only, it is considered an uncontrolled component in React.

#### Handling Multiple Inputs

We can add a name attribute to each element and let the handler function choose what to do based on the value of `event.target.name`. Since `setState()` automatically merges a partial state into the current state, we only needed to call it with the changed parts.

[_source_](https://reactjs.org/docs/forms.html)

---

#### Lifting State Up

Often, components need to reflect the same changing data. It's recommend lifting the shared state up. Sharing state is accomplished by moving it up to the closest common ancestor of the components that need it. This is called “lifting state up”. There should be a single “source of truth” for any data that changes in a React application. Usually, the state is first added to the component that needs it for rendering. Then, if other components also need it, we can lift it up to their closest common ancestor. We should rely on the top-down data flow. If something can be derived from either `props` or `state`, it probably shouldn’t be in the `state`.

[_source_](https://reactjs.org/docs/lifting-state-up.html)

---

### Composition vs Inheritance

#### Containment

Some components don’t know their children ahead of time. It this case it's recommended that such components use the special children prop to pass children elements directly into their output. This lets other components pass arbitrary children to them by nesting the JSX.

```JavaScript
function WelcomeDialog() {
  return (
    <FancyBorder color="blue">
      <h1 className="Dialog-title">
        Welcome
      </h1>
      <p className="Dialog-message">
        Thank you for visiting our spacecraft!
      </p>
    </FancyBorder>
  );
}
```

#### Specialization

Sometimes we think about components as being “special cases” of other components. This is also achieved by composition, where a more “specific” component renders a more “generic” one and configures it with props. Composition works equally well for components defined as classes.

#### What About Inheritance?

Props and composition give us all the flexibility we need to customize a component’s look and behavior in an explicit and safe way. Components may accept arbitrary props, including primitive values, React elements, or functions. If we want to reuse non-UI functionality between components, we could extract it into a separate JavaScript module. The components may import it and use that function, object, or class, without extending it.

[_source_](https://reactjs.org/docs/composition-vs-inheritance.html)

---

### Thinking in React

#### Step 1: Break The UI Into A Component Hierarchy

- Create a mock and draw boxes around every component and name them. Use the single responsibility principle, each component should only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.
- Arrange components into a hierarchy. Components that appear within another component in the mock should appear as a child in the hierarchy.

#### Step 2: Build A Static Version in React

A static version is version of our app that takes our data model and renders the UI but has no interactivity. To build one we need to build components that reuse other components and pass data using props (way of passing data from parent to child). We don’t need to use state at to build a static version. State is reserved only for interactivity (data that changes over time). React’s one-way data flow (one-way binding) will keep everything modular and fast.

#### Step 3: Identify The Minimal (but complete) Representation Of UI State

To make our UI interactive, we need to be able to trigger changes to our underlying data model. We achieve this with state. We need to think of the minimal set of mutable state that the app needs. The key here is DRY: Don’t Repeat Yourself. Figure out the absolute minimal representation of the state our application needs and compute everything else we need on-demand. Ask three questions about each piece of data:

- Is it passed in from a parent via props? If so, it probably isn’t state.
- Does it remain unchanged over time? If so, it probably isn’t state.
- Can you compute it based on any other state or props in your component? If so, it isn’t state.

#### Step 4: Identify Where Your State Should Live

Now, we need to identify which component mutates, or owns, state. For each piece of state in your application:

- Identify every component that renders something based on that state.
- Find a common owner component (a single component above all the components that need the state in the hierarchy).
- Either the common owner or another component higher up in the hierarchy should own the state.
- If we can’t find a component where it makes sense to own the state, we should create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

#### Step 5: Add Inverse Data Flow

At this point the app renders correctly as a function of props and state flowing down the hierarchy, now we need to support data flowing the other way. The idea is to make sure that whenever the user changes a form or something else within the app, we update the state to reflect the user input.

[_source_](https://reactjs.org/docs/thinking-in-react.html)

---

### Things I want to know more about

- I would like to know more about different approaches to implement React efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
