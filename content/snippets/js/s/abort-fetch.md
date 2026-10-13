---
title: Abort a fetch request in JavaScript
shortTitle: Abort a fetch request
language: javascript
tags: [function]
cover: cancel-typographer
excerpt: Aborting a fetch request in JavaScript is a common task. Here's how to handle it correctly.
listed: true
dateModified: 2022-05-15
---

The Fetch API is nowadays the de facto way to send asynchronous requests in JavaScript. This is largely due to the fact that the `fetch()` method accepts a multitude of useful options. One of these is the `signal` option, which can be used to abort a request. To create a valid value for this option, you can use `AbortController.signal` after creating a new instance of `AbortController`. Then, you can use `AbortController.abort()` to cancel the request at any time.

```js
// Create the AbortController
const controller = new AbortController();
const { signal } = controller;

// Perform the request
fetch('[https://my.site.com/data](https://my.site.com/data)', { signal }).then(res => console.log(res));

// Abort the request
controller.abort();
