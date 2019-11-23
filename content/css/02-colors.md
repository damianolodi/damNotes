---
title: "Colors"
draft: false
arguments: []
weight: 2
---

## General

`color: #AABBCC;` --> hex values

`color: rgb(0,255,255);` --> rgb values

`color: rgb(5%,50%,100%);` --> rgb values

`color: rgba(255,255,255,0.5);` --> rgb with **opacity** between 0 and 1

`color: hsl(180,100%,50%);` --> _HSL is supported only by CSS3, so older browser can have problem with the encoding of this statement_

-   **hue** `0°-360°` (color)
-   **saturation** `%` (amount of gray in a given color)
-   **lightness** `%` (amount of white in a given color)

* * *

## Background

`background-color: green;`

`opacity: 50%;`

`background: url("https://...");` --> place **image as background**

`background: linear-gradient(45deg, red, yellow, rgb(204, 204, 255));`

-   (_direction_, color1, color2, color3,...)

`background: repeating-linear-gradient(45deg, yellow 0px, red 40px, green 40px, blue 80px);`

-   (_direction_, color1 and start pixel, color2 and stop pixel, color3 and start pixel, color4 and stop pixel)
-   subsequent color mix each other if they start and stop at different position
-   lots more parameters accepted, see documentation
