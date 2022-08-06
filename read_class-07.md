# REST

We already starting working on the City Explorer project for this module. We just finished the first Lab implementing the Axios library to make user-initiated requests for data from a third-party API. This topic matters as it relates to understanding Rest to continue building on our app.

---

## Understanding Rest

**Who is Roy Fielding?**

He is computer scientist that helped write the first web servers that sent documents across the internet. He is one of the principal authors of the HTTP specification and the originator of the Representational State Transfer (REST) architectural style. He also did extensive research explaining why the web works the way it does. His name is on the specification for the protocol that is used to get pages from servers to your browser.

**Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?**

Because they were not designed to be used like that. When Fielding and his colleagues started building the web, being able to talk to any machine anywhere in the world was a primary concern. But most of the techniques developers later used to get computers to talk to each other didn't have those requirements.

**What is the HTTP protocol that Fielding and his friends created?**

It is a protocol based on applying verbs to nouns. For example, when we go to a web page the browser does an HTTP GET on the URL we typed in and returns a web page. Web page images are separate resources. The web page specifies the URLs to the images and the browser GETs them using the HTTP protocol until all the resources are obtained and the web page is displayed. The important thing here is that very different kinds of nouns can be treated the same. Whether the noun is an image, text, video, an mp3, a slideshow, etc. We can GET all of those things the same way given a URL.

**What does a `GET` do?**

Requests data from a specified resource. Retrieves information between systems.

**What does a `POST` do?**

Sends data to the server. Adds something from one system to another.

**What does `PUT` do?**

Creates a new resource or replaces a representation of the target resource.

**What does `PATCH` do?**

Applies partial modifications to a resource.

---

### Things I want to know more about

* I would like to know more about the origins of the World Wide Web and the HTTP protocols.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
