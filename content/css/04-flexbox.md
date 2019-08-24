---
title: "Flexbox"
draft: false
arguments: []
weight: 4
---

Everything refers back to the **main axis** and the **cross axis** of the container.

> For a complete guide visit [CSS Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

* * *

## Properties of the parent

`display: flex;` --> the element becomes a flex-container - its child items becomes flex-items (only the direct descendants)

`flex-direction: row;` --> row, row-reverse, column, column-reverse set the main axis of the flex container

`flex-wrap: wrap;` --> wrap the flex-items if necessary

-   `flex-flow: flex-direction flex-wrap;`

`justify-content: center;` --> justify along the main axis

-   `flex-start, flex-end, center`
-   `space-between, space-around, space evenly`

`align-content: stretch;` --> justify along the cross axis

-   `flex-start, flex-end, center`
-   `space-between, space-around, stretch`

`align-items: center;` --> determine how items are aligned along the main axis (along a single line)

-   `flex-start, flex-end, center, stretch, baseline`

* * *

## Properties of the children

`flex-basis: 100%;` --> defines the default size of an element before the remaining space is distributed

`flex-grow: 1;` -->  if set to a positive number, it allows flex-items to grow along the main axis from their flex-basis

`flex-shrink: 1;` -->  if set positive, allows the items to shrink instead of overflow

-   `flex: flex-grow flex-shrink flex-basis;`

`flex-wrap: nowrap;` --> specifies whether flex items are forced into a single line or can be wrapped onto multiple lines

-   `nowrap, wrap, wrap-reverse`

`align-self: center;` --> align flex-items to the current flex line

-   `auto, flex-start, flex-end`
-   `center, baseline, stretch`

`order: integer-number;` --> order along the main axis
