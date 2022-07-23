# Passing Functions as Props

We have been building our app "Gallery of Horns" on React using class components, props, state, among other things. This topic matters as it relates to expanding the usage of props.

---

## React Docs - lists and keys

**What does .map() return?**

It returns a new array with the results of a callback function.

**If I want to loop through an array and display each value in JSX, how do I do that in React?**

We loop through the array using `.map()` and we return the element using curly braces `{}`. (e.g.)

``` ES6
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
```

* Each list item needs a unique **key.**

**What is the purpose of a key?**

To help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable ID.

---

## The Spread Operator

**What is the spread operator?**

It is a syntax that uses `(...)` to expand an iterable object into the list of arguments.

**List 4 things that the spread operator can do.**

1. Copy an array
2. Concatenate or combine arrays
3. Use Math functions
4. Use an array as arguments

**Give an example of using the spread operator to combine two arrays.**

``` ES6
const myArray = [`🤪`,`🐻`,`🎌`]
const yourArray = [`🙂`,`🤗`,`🤩`]
const ourArray = [...myArray,...yourArray]
console.log(...ourArray) // 🤪 🐻 🎌 🙂 🤗 🤩

```

*example: [medium.com](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)*

**Give an example of using the spread operator to add a new item to an array.**

```ES6
const fewFruit = ['🍏','🍊','🍌']
const fewMoreFruit = ['🍉', '🍍', ...fewFruit]
console.log(fewMoreFruit) //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]
```

*example: [medium.com](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)*

**Give an example of using the spread operator to combine two objects into one.**

```ES6
const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
```

*example: [medium.com](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)*

---

## How to Pass Functions Between Components

**What is the first step that the developer does to pass functions between components?**

He creates a function call "increment" wherever the `state` he is going to change is located.

**In your own words, what does the increment function do?**

It loops through the array "people" using `.map()` looks for a match to the property "name" passed as an argument, creates a new array with "count" incremented by 1, returns the object and updates state.

**How can you pass a method from a parent component into a child component?**

We define a method in the parent component and we pass it as a prop to the child component.

**How does the child component invoke a method that was passed to it from a parent component?**

The method is passed like any other prop to the child component and we invoke it with `this.props.method-name()`.

---

### Things I want to know more about

* I would like to understand better how to pass methods as props.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
