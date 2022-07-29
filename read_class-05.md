# Putting it all together

We just finished our project "Gallery of Horns". We learned how to create components in React, how to use props and sate, array methods like, `.map()`, `.filter()`, `.find()`, using modals, passing functions as props between child and parent components and using forms with bootstrap. This topic matters as it relates to putting all this together for a better overall understanding.

---

## React Docs - Thinking in React

**What is the single responsibility principle and how does it apply to components?**

The single responsibility principle refers to the practice that a component should only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

**What does it mean to build a ‘static’ version of your application?**

It means to build a version of our app that takes our data model and renders the UI but has no interactivity. We do not use `state` to build a static version.

**Once you have a static application, what do you need to add?**

Interactivity. We achieve this with `state`.

**What are the three questions you can ask to determine if something is state?**

1. Is it passed in from a parent via props?
2. Does it remain unchanged over time?
3. Can you compute it based on any other state or props in your component?

**How can you identify where state needs to live?**

* Identify every component that renders something based on state.
* Find a common owner component, which is a single component above all the components that need the state in the hierarchy.
* Either the common owner or another component higher up in the hierarchy should own the state.
* If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

---

## Higher-Order Functions

**What is a “higher-order function”?**

It is a function that operates on other functions, either by taking them as arguments or by returning them. It allows us to abstract over actions, not just values.

**Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?**

```javascript
function greaterThan(n) {
  return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11));
// → true
```

Line 2 is returning a newly created function that takes in `m` as a new parameter and compares it with the original parameter `n` using the greater than operator `>`.

**Explain how either map or reduce operates, with regards to higher-order functions.**

The `.map()` method transforms an array by applying a function to all of its elements and building a new array from the returned values. The new array will have the same length as the input array, but its content will have been mapped to a new form by the function.

---

### Things I want to know more about

* I would like to learn how to write better more concise code and how to use higher-order functions.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
