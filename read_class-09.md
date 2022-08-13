# Functional Programming

We have been working on the City Explorer project for this module. Last lab we called third-party APIs to render live weather and movie data in response to city searches on our front-end App. This topic matters as it relates to understanding functional programming to refactor our code.

---

## Functional Programming Concepts

**What is functional programming?**

Functional programming is a programming paradigm. A style of building the structure and elements of computer programs. Treats computation as the evaluation of mathematical functions and avoids changing state and mutable data.

[Wikipedia](https://en.wikipedia.org/wiki/Functional_programming)

**What is a pure function and how do we know if something is a pure function?**

It is a function that returns the same result if given the same arguments (also referred as `deterministic`). It does not cause any observable side effects. If it reads external files, it’s not a pure function.

**What are the benefits of a pure function?**

The code is easier to test. We don’t need to mock anything. We can unit test pure functions with different contexts:

* Given a parameter `A` → expect the function to return value `B`
* Given a parameter `C` → expect the function to return value `D`

**What is immutability?**

Unchanging over time or unable to be changed. When data is immutable, its state cannot change after it is created. To change an immutable object we create a new object with the new value instead.

**What is Referential transparency?**

It is when a function consistently yields the same result for the same input.

`pure functions + immutable data = referential transparency`

---

## Node JS - Modules and require()

**What is a module?**

A module is just another JS file.

**What does the word ‘require’ do?**

It is a function on the global object that we can use when we want to bring the same functionality from one JS file into a different file within our app.

**How do we bring another module into the file the we are working in?**

We use the `require()` function in the file that we are working in.

**What do we have to do to make a module available?**

We use the `module.exports` property in the JS file where the original function was created.

---

### Things I want to know more about

* I would like to know more about how to implement functional programming to refactor my code and to practice more with modules and require().

---

[-back](https://alexriverau.github.io/reading-notes/code301)
