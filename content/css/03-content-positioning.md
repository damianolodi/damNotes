---
title: "Content Positioning"
draft: false
arguments: []
weight: 3
---

### Display

`display: block;` → the element occupies all the width of the parent element

`display: inline;` → the elements are arranged horizontally

`display: none;` → not rendered

* * *

### Dimensions

<img src="/img/content/css/box-model.png" class="img-fluid figure-img img-custom">

All elements on a web page are interpreted by the browser as “living” inside of a box.

`width: 150px;`

-   `min-width` and `max-width` also possible

`height: 70%;`

-   `min-heigth` and `max-height` also possible

### Content Based

`width: min-content;` → wrap the content and use the minimum space

-   _no support for Edge_

`width: max-content;` → don't wrap and use the minimum space

-   _no support for Edge_

#### Box Sizing

`box-sizing: content-box;`

`box-sizing: border-box;` → size attributes will apply after the padding and border have been added

* * *

### Alignment

`float: left;` → subsequent content in the container is wrapped around the floating content

`clear: both;` → delete the effect of a previous float container on the actual container

* * *

### Overflow

The overflow property is set on a parent element to instruct a web browser how to render child elements. For example, if a div’s overflow property is set to scroll, all children of this div will display overflowing content with a scroll bar.

`overflow: visible;` → default - overflow content should be displayed without affecting the container

`overflow: hidden;` → the content is clipped so any content outside of the container is not visible

`overflow: scroll;` → horizontal and vertical scroll bars are always created even if the content fits inside the container

`overflow: auto;` → scroll bars are created only when the content overflows the container

* * *

### Position

`position: static;` -> default - content is positioned based on its location in the document and the flow properties that are assigned

> from now on use top, bottom, rigth, left to assign the offset

**This elements set the position with respect to the first parent with a relative position**

`position: relative;` → element position is offset from where its normal flow position would be

-   After it add left, right, top or bottom to specify the offset
-   Other elements around it still behave as if that item were in its default position

`position: absolute;` → element is positioned at a specific location

-   This removes the element from the normal flow of the document, so surrounding items ignore it
-   After it add left, right, top or bottom to specify the offset

`position: fixed;` → the element is positioned relative to the viewport (the browser window); its position on the screen does not change when the document is scrolled

* * *

### Stacking Order

`z-index: 0;` → this only apply to non statically positioned content

* * *

### Box model

Border

```css
* {
    border: solid black 4px;
    border: 4px 4px 4px 4px; /*top right bottom left - can use thin medium thick*/
    border-color: green;
    border-style: solid; /*none hidden dotted dashed solid double groove ridge inset outset*/
    border-radius: 100%;
}
```

Margin - **space outside the border**

```css
* {
    margin: 5px 5px 5px 5px; /*top right bottom left - use auto to center*/
}
```

Padding - **space inside the border** (between content and border)

```css
* {
    padding: 6px 6px 6px 6px; /*top right bottom left*/
}
```

Box shadows - inset (if present) specify that also an inner shadow is present

```css
*{
    box-shadow: 0px 0px 3px 1px #12a0a0, inset 0px 0px 3px 1px #12a0a0;
        /* x-direction, y-direction, blur, spread, color*/
}
```

Scale the dimension of the object

```css
* {
    transform: scale(2);
}
```
