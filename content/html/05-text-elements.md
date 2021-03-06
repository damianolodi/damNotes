---
title: "Text Elements"
draft: false
arguments: []
weight: 5
---

### Common Text

-   `<!-- -->` &rarr; comments in html5
-   `<h1> <h2> <h3> <h4> <h5> <h6>` &rarr; headings
-   `<p>` &rarr; paragraph
    		_ Spaces and returns don’t affect the appearance of the code.
    		_ To break the line in one paragraph (without changing paragraph) use the tag `<br />`
-   `<em>` &rarr; italics
-   `<strong>` &rarr; bold
-   `style=“color: blue”` &rarr; attribute to change color to apply CSS only to that tag

* * *

### Lists

```html
<ul>
	<il> item 1 </il>
	<il> item 2 </il>
	<il> item 3 </il>
</ul>
```

-   Use it outside the `<p>` tag.
-   Use the `<ol>` tag to do _ordered lists_

* * *

### Links

```html
<a href=“https://www.wikipedia.org/“> This Is A Link To Wikipedia </a>
```

**Attributes** provide even more information about an element’s content and they live directly inside of the opening tag of an element.

-   `target="_blank"` &rarr; link opens in a different tab
-   `<a href=“./index.html”>` &rarr; link to other pages of the same site
-   `<a href=“#id_value”>` &rarr; link to a tag with attribute `id="id_value"`
