# React Lifecycle / State and Props

We have been learning about React, class components and how to use them. This topic matters as it relates to next logical steps to continue building on the subject.

---

## Lifecycle

**What happens first, the `render` or the `componentDidMount`?**

Based off the diagram `render` happens first.

**What is the very first thing to happen in the lifecycle of React?**

The `constructor()` is the very first method called as the component is brought to life. There are three phases of the component lifecycle:

* Mounting
* Updating
* Unmounting

**Putting things in the order that they happen:**

1. `constructor`
2. `React Updates`
3. `render`
4. `componentDidMount`
5. `componentWillUnmount`

**What does `componentDidMount` do?**

We use the `componentDidMount()` method to grab a DOM node from the component tree immediately after it is mounted. This is also a perfect place to make network requests and set up subscriptions. We have to make sure to cancel the subscriptions when the component unmounts.

---

## React State vs Props

**What types of things can you pass in the props?**

Props are like arguments to a function. When can pass things we would like our component to render, like the initial count of a counter, or a title of something we would like to display. If the props change the app re-renders the component with the updated data.

**What is the big difference between props and state?**

The main difference is that in Props with pass into a component and is handled and updated **outside** of it. State is handled and updated **inside** of the component

**When do we re-render our application?**

When we change the State inside of our application. We `re-render` that section of the app.

**What are some examples of things that we could store in state?**

For example a counter app, we use Props for the initial count and State for the operations that we are going to be updating inside of it. Another example would be a form, we use State to store the values input by the user.

---

### Things I want to know more about

* I would like to know more about React updates, `re-render` and when to use State vs Props.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
