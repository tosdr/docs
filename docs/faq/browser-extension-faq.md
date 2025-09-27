---
description: Commonly asked questions regarding the browser extension answered!
icon: comments-question-check
---

# Browser Extension FAQ

1. Why does the ToS;DR Browser Extension ask for so many permissions, like reading every visited website's data?

> ToS;DR requires the permission to read website's data to fetch the URL of the site you are currently on. All website content is not visible to us in any way. You can verify this behavior by browsing through our browser extensions [source code](https://github.com/tosdr/browser-extensions).

2. Does ToS;DR send a server request for every website I visit?

> No. The ToS;DR extension comes with a built-in database of all rated services and their URLs, so it can locally check the sites you visit without contacting our servers. A request is only made when you actively interact with the extension to view details. Even then, we don’t send the full URL—just the domain. For example, `drive.google.com/drive?...` would be reduced to `drive.google.com`.
