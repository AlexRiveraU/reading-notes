# React 4

This topic matters as it relates to learning about implementing Next.js Dynamic Routes and Deployment.

---

### Next.js - Dynamic Routes

To create a dynamic route we add brackets to a page, for example (`[pid]`).

```javascript
<Link href="/post/abc/a-comment">
    Go to pages/post/[pid]/[comment].js
</Link>
```
Dynamic routes can be extended to catch all paths by adding three dots `(...)` inside the brackets.

#### How to Statically Generate Pages with Dynamic Routes

* Use a React component to render the page
* Implement `getStaticPaths` which returns an array of possible values for the dynamic route
* Implement `getStaticProps` which fetches the necessary data for the post with the dynamic route

#### Implement getStaticPaths

For example, we create a file called `[id].js`. The returned list must be an array of objects, and each object must have a `params` key and contain an object with the `id` key (because we’re using [id] in the file name). Otherwise, getStaticPaths will fail.

#### Implement getStaticProps

Now we need to fetch necessary data to render the post with the given `id`. We add a `getPostData` function that will return the post data based on `id`. Then the `getPostData` function will be used in `getStaticProps` to get the post data and return it as props.

#### Render Markdown

* Install:

```commandline
npm install remark remark-html
```

* Imports:

```javascript
import { remark } from 'remark';
import html from 'remark-html';
```

* Update the `getPostData()` function in the same file to use `remark`
* Add the `async` keyword to `getPostData` because we need to use `await` for `remark` to fetch data asynchronously
* Update `getStaticProps` to use `await` when calling `getPostData`
* Update to render `contentHtml` using `dangerouslySetInnerHTML`

#### Fetch External API or Query Database

* We use `getAllPostIds` to fetch data from an external API endpoint.

#### Development vs. Production
* In development, `getStaticPaths` runs on every request
* In production, `getStaticPaths` runs at build time

[source](https://nextjs.org/learn/basics/dynamic-routes)

---

### Next.js - Deployment

#### Deploy to Vercel

Vercel is a serverless platform developed by the creators of Next.js for static and hybrid applications built to integrate with headless content, commerce, or database.

* Need to create a Vercel Account
* Import project's repository to Vercel

#### Develop, Preview, Ship

* **Develop -** Write code in Next.js and use the Next.js development server running to take advantage of its hot reloading feature
* **Preview -** Push changes to a branch on GitHub. Vercel creates a preview deployment available via a URL
* **Ship -** Merged the pull request to main to ship to production

[source](https://nextjs.org/learn/basics/deploying-nextjs-app)

---

### Things I want to know more about

- I would like to know more about how to implement Dynamic Routes efficiently.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
