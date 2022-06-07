# CLASS-13

## LOCAL STORAGE

**Local storage in native client applications advantages:**

* The operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state.
* These values may be stored in the registry, INI files, XML files, or some other place according to platform convention.
* If it needs more local storage beyond key/value pairs, you can embed your own database, invent your own file format, and many other solutions.

**Cookies in web applications:**

They can be used for persistent local storage of small amounts of data but have downsides:

* Included with every HTTP request, slowing down your web app.
* Included with every HTTP request, sending data unencrypted over the internet.
* Limited to about 4 KB of data.

### HTML5 Storage

It is a way for web pages to store named key/value pairs locally within the client web browser. Data persists even after you navigate away from the web site, close your browser tab or exit your browser. This data is never transmitted to the remote web server, it is implemented natively in web browsers, so it is available even when third-party browser plugins are not.

>JavaScript

You can access html5 storage through the `localStorage` object, or `Modernizr` to detect support for html5 storage. The data is stored as a string. We can use use functions like `parseInt()` or `parseFloat()` to coerce your retrieved data into the expected JavaScript datatype.

**HTML5 Storage Limitations:** The amount of data we can store is 5 megabytes. Keep in mind that we are storing strings. If we are storing a lot of integers or floats, the difference in representation can really add up.

***

### Things I want to know more about

* Understanding SQL and new storage visions.

***

[-back](https://alexriverau.github.io/reading-notes/)
