---
title: "Front Matter"
draft: false
arguments: []
weight: 2
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
