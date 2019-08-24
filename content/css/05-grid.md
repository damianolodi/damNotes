---
title: "Grid"
draft: false
arguments: []
weight: 5
---

> For a complete guide visit [CSS Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)

* * *

## Dictionary

-   **Line** --> the dividing lines that make up the structure of the grid;
-   **Track** --> the space between two adjacent grid lines;
-   **Area** --> the total space surrounded by four grid lines;

* * *

## Properties of the parent (container)

`display: grid;` --> create a grid container

-   `grid, inline-grid`

`grid-template-columns: track-size1 track-size2 ...;`

-   can be expressed in `fr`

`grid-template-rows: track-size1 track-size2 ...;`

-   can use the `repeat(n°, size)` function
-   can use the `minmax(min, max)`
-   can be `auto-fill` and `auto-fit`

`grid-template-areas`

```css
div {
    grid-template-areas: "grid-area-name1 grid-area-name2 ..."
                         "grid-area-name3 grid-area-name4 ...";
}
```

-   Use `.` to mean empty cell
-   Defines a grid template by referencing the names of the grid areas
-   Repeating the name of a grid area causes the content to span those cells.

`grid-column-gap: line-size;` --> specifies the size of the grid lines

`grid-row-gap: line-size;` --> applied only between cells, not on the outers lines

`grid-gap: grid-row-gap grid-column-gap;` --> in the future the grid prefix will be removed

`justify-items: start;` -->  align all grid items along the row axis

-   `start, end, center, stretch`

`align-items: baseline;` --> align all grid items along the column axis

-   `start, end, center, stretch`

`place-items: align-items justify-items;`

`justify-content: center;`

-   `start, end, center, stretch`
-   `space-around, space-between, space-evenly`

`align-content: center;` --> Needed if the total size of the grid is less than the size of the container

-   `start, end, center, stretch`
-   `space-around, space-between, space-evenly`

* * *

## Properties of the children (item - direct descendant)

`grid-column-start: line-number;`

-   `line-name, span(number), span(name), auto`

`grid-column-end: line-number;`

-   `line-name span(number) span(name) auto`

`grid-row-start: line-number;`

-   `line-name span(number) span(name) auto`

`grid-row-end: line-number;`

-   `line-name span(number) span(name) auto`

`grid-column: grid-column-start / grid-column-end;`

`grid-row: grid-row-start / grid-row-end;`

`grid-area: area-name;` --> assign the element to the area called

-   `<row-start> / <column-start> / <row-end> / <column-end>`

`justify-self: start;` --> aligns only the grid item inside a cell along the row axis

-   `start, end, center, stretch`

`align-self: start;` --> aligns only the grid item inside a cell along the column axis - align vertically

-   `start, end, center, stretch`

`place-self: align-self justify-self;` --> can be auto

```python

```
