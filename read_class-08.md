# APIs

We have been working on the City Explorer project for this module. Last Lab we built our own custom API server which provided 'dummy data' to our front-end App. This topic matters as it relates to implementing real APIs on our application.

---

## API Design Best Practices

**What does REST stand for?**

Representational State Transfer (REST).

**REST APIs are designed around a ____.**

Resource.

**What is an identifier of a resource? Give an example.**

A Uniform Resource Identifier (URI) that uniquely identifies that resource. (e.g.) `https://adventure-works.com/orders/1`

**What are the most common HTTP verbs?**

`GET`, `POST`, `PUT`, `PATCH` and `DELETE`.

**What should the URIs be based on?**

Nouns (the resource).

**Give an example of a good URI.**

`https://adventure-works.com/orders`

**What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?**

Web requests impose a load on the web server. The more requests, the bigger the load. Having a 'chatty' API means that such API may require a client application to send multiple requests to find all of the data that it requires. It is a bad thing.

**What status code does a successful `GET` request return?**

Code 200 (OK).

**What status code does an unsuccessful `GET` request return?**

Code 404 (Not Found).

**What status code does a successful `POST` request return?**

Code 201 (Created).

**What status code does a successful `DELETE` request return?**

Code 204 (No Content).

---

### Things I want to know more about

* I would like to know more about how to implement APIs efficiently. Their syntax and error handling.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
