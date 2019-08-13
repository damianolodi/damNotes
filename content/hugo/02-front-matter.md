---
title: "Front Matter"
date: 2019-08-05T21:19:34+02:00
summary: "Bo"
tags: ["hugo"]
draft: false
---

Informations between the two `---` is called **front matter**.

* * *

-   `draft: true` → mark post as draft

-   `image: "static/path-to-image.jpeg"` → set the **default post image** (usuallly placed in the `static` directory)

-   `tags: ['tag1', 'tag2']` → post tags

-   `categories: ['category1', ...]` → post categories

-   `publishdate:` → set a publishing date for the post (if the build date is previous the one indicated, the post will not be published)

-   `expirydate` → if the build date is previous the one indicated, the post will not be compiled

* * *

## Resources

1.  [Documentation](https://gohugo.io/content-management/front-matter/)
