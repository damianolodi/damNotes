---
title: "Pseudo Class"
draft: false
arguments: []
weight: 10
---

-   Changing color of a link when hover on it

```css
    a:hover {
        color: red;
    }
```

-   Add something before or after a selected element

```css
    .class::before {
        content: "Phrase";
        /*here you can modify the properties of the added thing/shape*/
    }
```

The `content` property is used to add an image or a text as the element to be added. If you use it to do a shape, place an empty string.
