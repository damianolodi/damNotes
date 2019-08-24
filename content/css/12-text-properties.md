---
title: "Text Properties"
draft: false
arguments: []
weight: 12
---

### Typography

<img src="/img/content/css/typography.png" class="img-fluid figure-img img-custom">

* * *

### Import Fonts

-   _Import in html_ using

```html
<link href="https://fonts.googleapis.com/css?family=Cabin" rel="stylesheet">
```

-   _Import in css_ file using

```css
@import url(//fonts.googleapis.com/css?family=Cabin);
```

-   Last term is called font-families and can be:
    	_ cursive
    	_ fantasy
    	_ monospace
    	_ sans-serif
    	\* serif
    #### Font Assets

1.  List of  [Web safe fonts](https://www.cssfontstack.com/)
2.  [Google Fonts](https://fonts.google.com/)

* * *

### Properties

#### Font Properties

1.  `font-family: Garamond , Times , serif;` -> fonts after the first are called **fallback fonts**

2.  `font-size: 30px;` -> measured in `px`, `em` or `%`

3.  `size: xx-small;` -> also `x-small, small, medium, large, x-large, xx-large`
    -   smaller and larger set based on the parent font size, as using `%`

#### Font Decoration

4.  `font-weight: normal;` -> also `bold` (preferred) or a value `100:100:900`

5.  `font-style: normal;` -> default, also `italic`

6.  `text-decoration: normal` -> also `none, underline, line-through`

7.  `color: rgb(255, 0, 0);` -> see [Colors](bear://x-callback-url/open-note?id=E4640479-39BD-4F5E-8A55-AAFD9B18C005-1311-000006200E5BBA80)  for more options

8.  `text-transform: uppercase;` -> also `lowercase, capitalize, initial, inherit`

9.  `text-shadow: 4px 0px 1px #fff;` -> add coloured shadow
    -   x-offset   y-offset   blur   color

#### Font Justification

10. `text-align: center` -> also `left, right, justify`

11. `word-spacing: 0.25em;`

12. `letter-spacing: 0.3em;`

13. `line-height: 1em;` -> manipulate the _leading_ (pronounced “ledding”)

<img src="/img/content/css/lineHeigthAnatomy.png" class="img-fluid figure-img img-custom">

* * *

### List properties

-   Remove dots from lists

```css
	ul {
	    list-style-type: none;
	}
```
