# In memory storage

We are almost finished with the City Explorer project for this module. Last lab we focused on refactoring the code base of both our front-end and back-end. This topic matters as it relates to understanding how in memory storage work so we can implement it in our app.

---

## Understanding the JavaScript Call Stack

**What is a ‘call’?**

It is a function invocation.

**How many ‘calls’ can happen at once?**

One at a time, from top to bottom.

**What does LIFO mean?**

Last In, First Out (LIFO). Which is a principle to temporarily store and manage function invocation.

**Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.**

```JavaScript
function firstFunction(){
  console.log("Hello from firstFunction");
}

function secondFunction(){
  firstFunction();
  console.log("The end from secondFunction");
}

secondFunction();
```

**What causes a Stack Overflow?**

It happens when there is a recursive function, which is a function that calls itself without an exit point. The browser has a maximum stack call that it can accommodate before throwing a stack error. (e.g.)

```JavaScript
function callMyself(){
  callMyself();
}

callMyself();
```

---

## JavaScript error messages

**What is a ‘reference error’?**

When we try to use a variables that are not yet declared.

**What is a ‘syntax error’?**

When we have something that cannot be parsed in terms of syntax

**What is a ‘range error’?**

When we try to manipulate an object with some kind of length and we give it an invalid length.

**What is a ‘type error’?**

When the types we are trying to use or access are incompatible.

**What is a breakpoint?**

It is a feature in our developer tools that we use to pause our JavaScript code at certain regions for debugging purposes.

**What does the word ‘debugger’ do in your code?**

It stops the execution of JavaScript. Sets a breakpoint in the debugger.

---

### Things I want to know more about

* I would like to know more about how to debug efficiently. Would like to learn and practice debugging techniques in VS code and using our browser's developer tools.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
