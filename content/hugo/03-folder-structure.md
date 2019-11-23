---
title: "Folder Structure"
draft: false
arguments: []
weight: 3
---

## Archetypes

Set the _front matter_ for different content types.

-   _archetypes/default.md_ &rarr; **default front matter** for new content

```yaml
---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
---
```

* * *

## Config

-   Used to store various different configurations.
-   If the number of configuration is limited, one can just use a single `config.toml` file. Also `.json` and `.yaml` can be used.
-   To see more about configurations and configure each site properly, visit [this page](https://gohugo.io/getting-started/configuration/#all-variables-yaml)

* * *

## Content

-   Directory used to store all the text file for all the contents. E.g., one can create a subdirectory for posts, articles,…
-   Hugo uses sections to assign default [content types](https://gohugo.io/content-management/types/)
    -   A **section** is a portion of the site that holds subcontinent, such as a blog section and a work section. The blog section contains individual blog posts, and the work section is a portfolio of individual projects.
    -   A **static page** is simply a page that renders content and nothing else. It doesn’t need to index a list of subcontinent for the user to peruse. You can’t go down any further.

### Content Types

-   All markdown files inside `content/`, have a **type** associated to them. Hugo infers a markdown file’s type in one of two ways:
    1.  The name of the subdirectory that the file resides in: the file `a-blog-post.md` located at `content/blog/a-blog-post.md` will have the type `blog`
    2.  The type variable defined in that file’s front matter (optional): assigned using the `type` variable in front matter. In this cased, the type assigned by the previous method is overwritten
-   Pages can be **single pages** or **list pages**. Those last ones are represented by `_index.md` files and are used to list all the posts of that _section_ (not type!)

* * *

## Layouts

-   Used to store templates that will overrides the ones from the used theme.
-   Templates include [list pages](https://gohugo.io/templates/list/) , your [homepage](https://gohugo.io/templates/homepage/) , [taxonomy templates](https://gohugo.io/templates/taxonomy-templates/) , [partials](https://gohugo.io/templates/partials/) , [single page templates](https://gohugo.io/templates/single-page-templates/) , and more.

-   `layouts/index.html` &rarr; homepage template
-   `layouts/_default/single.html` &rarr; [single page](https://gohugo.io/templates/single-page-templates/#readout) template (blog posts)
-   `layouts/_default/list.html` &rarr; template for [list pages](https://gohugo.io/templates/lists/#readout). Range over a parameter using

```golang
{{ range .Pages.ByPublishDate.Reverse }}
{{ end }}
```

-   `layouts/_default/baseof.html` &rarr; contains common code to **all** other layouts. **Must** contain the line `{{ block "main" . }}{{ end }}` which tells where to place the unique code of each other layout. After this file is created, all other layouts should be contained inside the following block `{{ define "main" }}{{ end }}`. [Doc](https://gohugo.io/templates/base/)
-   `layout/partials/` &rarr; components of the website that can be extrapolated and "described" in a proper file (e.g. header, footer,...). Each partial can be called in another layout template using `{{ partial fileName.hmtl}}`. They can (should) be called also in `basof.html` to make the page structure clear. [Doc](https://gohugo.io/templates/partials/#readout)
-   `layout/partials/nav.html` &rarr; contains the menu of the website. It can be built using parameters defined under the `[menu]` keyword in the `config.toml` file of the website. [Doc](https://gohugo.io/templates/menu-templates/#readout)

* * *

## Static

Store all the static content, usually in the following subdirectories:

-   `img`
-   `css`
-   `js`

When Hugo builds the site, all assets inside the static directory are **copied over as-is.**

* * *

## Resources

1.  [Hugo’s Directory Structure Explained | Jake Wiesler](https://www.jakewiesler.com/blog/hugo-directory-structure/)
