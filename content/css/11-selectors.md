---
title: "Selectors"
draft: false
arguments: []
weight: 11
---

### General Technique

BEM technique (Block Element Modifiers)
Use only on classes

```css
.block__element--modifier {
	property: value;
}
```

-   Specificity is the order by which the browser decides which CSS styles will be displayed. A best practice in CSS is to style elements while using the lowest degree of specificity, so that if an element needs a new style, it is easy to override. **IDs are the most specific selector in CSS, followed by classes, and finally, tags.**

* * *

### Selectors

<img src="/img/content/css/css_anatomy.png" class="img-fluid figure-img img-custom">

-   Select all tags

```css
* {
}
```

-   Tag selector

```css
p {
}
```

-   Class selector

```css
.class-name {
}
```

-   Id selector (_IDs override the styles of tags and classes_)

```css
#id-name {
}
```

-   Attribute selector -> berfore `=` can use `~ | ^ $ *`

```css
[Attribute="value"] {
}
```

It can be the class, but also whichever other attribute in an html element.

-   Pseudo-class selector - class applied from the browser

```css
:visited {
}
```

-   Pseudo-elements selector

```css
::after {
}
```

* * *

### Combinations

-   All `h1` with class `class-name`

```css
h1.class-name {
}
```

-   Apply to everything, **logical OR**

```css
p, h1, .class-name {
}
```

-   Apply to all `p` inside `header` - descendant

```css
header p {
}
```

-   All `p` whose **immediate parent** is `header`

```css
header>p {
}
```

-   Select the second element when it follows the first element

```css
p~header {
}
```

* * *

### Reminders

Make sure the non-content elements are hidden. The browser default style sheet will set these anyway.

```css
head, title, meta, script, link, style, base {
    display: none;
}
```
