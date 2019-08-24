---
title: "Images"
draft: false
arguments: []
weight: 4
---

_Self-closing tag_

```html
<img src="https://www.example.com/picture.jpg" alt="A field of yellow sunflowers"/>
```

-   `src` → attribute with the url of the image
-   `alt` → description of what one can see
    -   _if an image fails to load on a web page, a user can mouse over the area originally intended for the image and read a brief description of the image._
    -   _visually impaired users often browse the web with the aid of of screen reading software._
    -   _if the image on the web page is not one that conveys any meaningful information to a user (visually impaired or otherwise), the alt attribute should not be used._

* * *

### Turn a figure into a link

```html
<a href="https://en.wikipedia.org/wiki/Opuntia" target="_blank">
	<img src="#" alt="A red prickly pear fruit" />
</a>
```
