# React 3

This topic matters as it relates to continue learning about implementing React and Next.js.

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

[source](https://nextjs.org/learn/basics/create-nextjs-app)

---

### React Context for Beginners

#### What is React context?

React context allows us to pass down and use data in whatever component we need without using props. It allows us to share data (state) across our components more easily. Data that does not need to be updated often should be placed on React context.

#### What problems does React context solve?

React context helps us avoid the problem of props drilling.

* **Props drilling -** Term used to describe when we pass props down multiple levels to a nested component, through components that don't need it.

#### How do I use React context?

Context is an API that is built into React. We can create and use context directly by importing React in any React project.

* **Steps to using React context:**

  * Create context using the `createContext` method.
  * Take our created context and wrap the context provider around our component tree.
  * Put any value we like on our context provider using the value prop.
  * Read that value within any component by using the context consumer.

Let's take a look at a very basic example. In our App, let's pass down our own name using Context and read it in a nested component: User.

#### What is the useContext hook?

We can now consume context with the `useContext` hook. Instead of using render props, we can pass the entire context object to `React.useContext()` to consume context at the top of our component.

[source](https://www.freecodecamp.org/news/react-context-for-beginners/)

---

### Things I want to know more about

- I would like to know more about how to implement React context and React hooks efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
