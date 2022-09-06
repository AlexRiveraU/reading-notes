# Authentication

We have been working on our Can of Books project for this module. We've added functionality for the user to create, read, update and delete books. This topic matters as it relates to learning how to implement authentication and authorization to finalize our app.

---

## What is OAuth

**What is OAuth?**

OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential.

**Give an example of what using OAuth would look like.**

When you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you, and the website you were originally connecting to logs you on itself afterward using permission gained from the second website.

**How does OAuth work? What are the steps that it takes to authenticate the user?**

1. The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.
2. The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.
3. The first site gives this token and secret to the initiating user’s client software.
4. The client’s software presents the request token and secret to their authorization provider.
5. If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.
6. The user approves a particular transaction type at the first website.
7. The user is given an approved access token.
8. The user gives the approved access token to the first website.
9. The first website gives the access token to the second website as proof of authentication on behalf of the user.
10. The second website lets the first website access their site on behalf of the user.
11. The user sees a successfully completed transaction occurring.

**What is OpenID?**

OpenID is about authentication not authorization.

*"OpenID is for humans logging into machines, OAuth is for machines logging into machines on behalf of humans."* - [StackOverflow](https://stackoverflow.com/questions/4230821/if-openid-is-dead-what-is-out-there-to-take-its-place/4230970#4230970)

---

## Authorization and Authentication flows

**What is the difference between authorization and authentication?**

Authentication is the process of verifying who a user is. Authorization is the process of verifying what they have access to.

**What is Authorization Code Flow?**

It is the process of exchanging an Authorization Code for a token. Your app must be server-side because during this exchange, you must also pass along your application's Client Secret.

**What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?**

It is a version of the Authorization Code Flow which for additional security makes use of a Proof Key for Code Exchange (PKCE). It introduces a secret created by the calling application that can be verified by the authorization server; this secret is called the Code Verifier. The calling app creates a transform value of the Code Verifier called the Code Challenge and sends this value over HTTPS to retrieve an Authorization Code. This way, a malicious attacker can only intercept the Authorization Code, and they cannot exchange it for a token without the Code Verifier.

**What is Implicit Flow with Form Post?**

It is an alternative to the Authorization Code Flow intended for Public Clients or applications which are unable to securely store Client Secrets. The web app requests and obtains tokens through the front channel, without the need for secrets or extra backend calls. With this method, you don’t need to obtain, maintain, use, and protect a secret in your application.

**What is Client Credentials Flow?**

It is when the system authenticates and authorizes the app rather than a user. Machine-to-machine (M2M) apps pass along their Client ID and Client Secret to authenticate themselves and get a token.

**What is Device Authorization Flow?**

It is when the device asks the user to go to a link on their computer or smartphone and authorize the device itself rather than authenticating the user directly.

**What is Resource Owner Password Flow?**

It is when the application requests that users provide credentials (username and password), typically using an interactive form. It is not recommend and it should only be used in highly-trusted applications when redirect-based flows (like the Authorization Code Flow) cannot be used.

---

### Things I want to know more about

* I would like to learn more about how to implement `OAuth`, `Auth0` and the different types of flows.

---

[-back](https://alexriverau.github.io/reading-notes/code301)
