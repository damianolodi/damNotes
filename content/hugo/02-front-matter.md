---
title: "Front Matter"
draft: false
arguments: []
weight: 2
---

Informations between the two `---` is called **front matter**.

* * *

-   `draft: true` &rarr; mark post as draft

-   `image: "static/path-to-image.jpeg"` &rarr; set the **default post image** (usuallly placed in the `static` directory)

-   `tags: ['tag1', 'tag2']` &rarr; post tags

-   `categories: ['category1', ...]` &rarr; post categories

-   `publishdate:` &rarr; set a publishing date for the post (if the build date is previous the one indicated, the post will not be published)

-   `expirydate` &rarr; if the build date is previous the one indicated, the post will not be compiled

* * *

## Resources

1.  [Documentation](https://gohugo.io/content-management/front-matter/)
