---
title: "Content Organization"
draft: false
arguments: []
weight: 4
---

## General Concepts

-   Content should be organised in such a way to reflect the rendered site.
-   Contents in the `content` directory can be nested at any level
-   The **top levels** (i.e. `content/<DIRECTORIES>`) are considered the **content type** used to determine layouts etc.

<img src="/img/content/hugo/concept-site-structure.png" class="img-fluid figure-img img-custom">

-   Here, `baseurl = "https://example.com"` is assumed in the `config.toml` file
-   One can keep one `_index.md` for the homepage and one in each content sections, taxonomies, and taxonomy terms. Considering the previous example, this means:
    -   1 for the homepage
    -   1 for about
    -   1 for posts -> _this will be the page with the list of all posts_
    -   1 for quotes  -> _this will be the page with the list of all quotes_

* * *

## Content Variables

-   Defining `slug` in the front matter will replace the name of the file in the actual slug of the page when the site is rendered.
-   `section` is determined by a content’s location on disk and **cannot** be specified in the front matter.
-   A content’s `types` also determined by its location on disk but, unlike `section`, it _can_ be specified in the front matter. This can come in especially handy when you want a piece of content to render using a different layout. For an example, see [here](https://gohugo.io/content-management/organization/#type)
-   Setting `url` in the front matter, a complete URL can be provided.

* * *

## Page Bundles

A Page Bundle is a group of page in the `content` directory.

### Leaf Bundle

-   A [Leaf Bundle](https://gohugo.io/content-management/page-bundles/#leaf-bundles) is a directory at any hierarchy within the `content/directory`, that contains an `index.md` file. It is a collection of content and attachments for single pages.

<img src="/img/content/hugo/leaf-bundle-example.png" class="img-fluid figure-img img-custom">

-   It does not allow nesting of more bundles under it.

### Branch Budle

-   A Branch Bundle is any directory at any hierarchy within the `content/directory`, that contains at least an `_index.md` file.
-   This `_index.md` can also be directly under the `content/` directory.

<img src="/img/content/hugo/branch-bundle-example.png" class="img-fluid figure-img img-custom">

* * *

## Supported Contents

-   Content can be written in markdown
-   Also HTML can be used, in particular when a particular layout is needed. In that case, **a front matter is needed**, eve if it is empty.

* * *

## Taxonomies

Taxonomies are user-defined grouping of contents and are used to organize relationship between content. [Doc](https://gohugo.io/content-management/taxonomies/)

Default taxonomies are:

```toml
+++
[taxonomies]
    category = "categories"
    tag = "tags"
+++
```
