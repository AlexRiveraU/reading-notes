# CRUD

We just started working on our Can of Books project for this module. Last lab we created an app that connects frontend to backend. Our express server connects to a MongoDB. We implemented "schema" and "seed". This topic matters as it relates to learning the next CRUD steps to continue building on our app.

---

## Status Codes Based On REST Methods

**In your own words, describe what each group of status code represents:**

* **100’s =** Informational status codes. The header part of the request has been received and the server will try to fulfill the request.
* **200’s =** Success codes. The request was accepted. It doesn't mean it was processed.
* **300’s =** Redirection codes.The requested resource is not available at the expected location anymore.
**400’s =** Client error codes. Invalid requests from client to server.
**500’s =** Server error codes. Problems with overwhelmed servers or unreachable servers behind proxies. Sometimes can related to client requests.

**What is a status code 202?**

Accepted - The request was valid but still processing. The response should include an URL to the finished resource or to some monitoring endpoint that tells the client when the resource will be available.

**What is a status code 308?**

Permanent Redirect - Tells the client to use another URL to access the resource and not the current URL anymore.

**What code would you use if an update didn’t return data to a client?**

204 No Content.

**What code would you use if a resource used to exist but no longer does?**

410 Gone.

**What is the ‘Forbidden’ status code?**

403 Forbidden.

---

## Build A REST API With Node.js, Express, & MongoDB - Quick

**Why do we need to pull our MongoDB database string out of our server and put it into our .env?**

Because when we deploy our app we want to use something that is not our localhost.

**What is middleware?**

It is code that the server gets to request before it gets pass to our routes.

**What does** `app.use(express.json())` **do?**

It lets our server accept json as our body instead of other elements.

**What does the** `/:id` **mean in a route?**

It means that it is parameter that we can access with dot notation. (e.g) `req.params.id`

**What is the difference between** `PUT` **and** `PATCH`**?**

PATCH only updates the information that gets passed. PUT updates all the information at once.

**How do you make a default value in a schema?**

Within the `new mongoose.Schema` object and inside of one of its `keys` we need to define a property named `default` and assign it an appropriate value. (e.g) `default: Date.now`.

**What does a** `500` **error status code mean?**

It means that there is an error on our server.

**What is the difference between a status** `200` **and a status** `201` **?**

200 means that everything was successful. 201 means that we successfully created an object, a more specific way of saying that we created something.

---

### Things I want to know more about

* I would like to know more about how to make full use of the HTTPs collection of codes to render accurate error messages.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
