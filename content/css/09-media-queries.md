---
title: "Media Queries"
draft: false
arguments: []
weight: 9
---

### Application

<img src="/img/content/css/breakpoints.png" class="img-fluid figure-img img-custom">

-   Apply when width is less than 600px

```css
    @media (max-width:600px) {
        h1 {
            font-size: 12px;
        }
    }
```

See p.172 pro HTML5... for every query.

-   `max-width`
-   `min-width`
-   `max-height`
-   `min-height`

* * *

### Breakpoints

-   Magari usa 600, 900, 1200 e se vuoi 1800

```css
/* Extra small devices (phones, 600px and down) */
@media only screen and (max-width: 600px) {}

/* Small devices (portrait tablets and large phones, 600px and up) */
@media only screen and (min-width: 600px) {}

/* Medium devices (landscape tablets, 768px and up) */
@media only screen and (min-width: 768px) {}

/* Large devices (laptops/desktops, 992px and up) */
@media only screen and (min-width: 992px) {}

/* Extra large devices (large laptops and desktops, 1200px and up) */
@media only screen and (min-width: 1200px) {}
```

* * *

### Measurements

```css
* {
    height: 100vh; /* viewport height - like %, but based on the viewport and not on the parent element measure*/
    width: 100vw; /*viewport width*/
    width: 100vmin; /*minimum between viewport height or width*/
    width: 100vmax; /*maximum between viewport height or width*/
    height: 2em; /*em is the font size of the browser*/
}
```
