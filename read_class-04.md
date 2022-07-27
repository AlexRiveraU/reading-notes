# React and Forms

We have been working on the "Gallery of Horns" project. Last lab we started using modals and passing functions as props between child and parent components. This topic matters as it relates to implementing forms to continue building on our app.

---

## React Docs - Forms

**What is a ‘Controlled Component’?**

Controlled Components are those in which form’s data is handled by the component’s state. We use a technique to have a javascript function handling the submission of a form having access to the data entered by the user. The input form element value is controlled by the component.

**Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why?**

We should make React state the "single source of truth" which means that since the `value` attribute is set on the form element, the displayed value will always be `this.state.value`. The event handler runs on every key stroke to update the state and the displayed value will update as the user types. This is good because we can now pass the value to other UI elements too, or reset it from other event handlers.

**How do we target what the user is entering if we have an event handler on an input field?**

We add a `name` attribute to each element and let the handler function choose what to do based on the value of `event.target.name`.

---

## The Conditional (Ternary) Operator Explained

**Why would we use a ternary operator?**

Because the Ternary operator shortens an ‘if’ statement into a one line of code. It is more convenient it terms of syntax for a clean code.

**Rewrite the following statement using a ternary statement:**

```javascript
if(x===y){
  console.log(true);
} else {
  console.log(false);
}
```

**Ternary statement:**

```javascript
(x===y) ? console.log(true) : console.log(false)
```

---

### Things I want to know more about

* I would like to know more about how to use forms in React.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
