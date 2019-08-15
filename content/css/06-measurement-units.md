---
title: "Measurement Units"
draft: false
---

vw, vh, vmin, vmax, rem

`px` -> pixels are used to set the exact size of an element

`em` -> the _em_ represents the size of the base font being used. It is a relative unit of measurement. They change the size of text relative to the parent element’s size of text

`rem` -> it means _root em_. Instead of checking parent elements to size font, it checks the root element. The root element is the `<html>` tag.

-   **One advantage of using rems is that all elements are compared to the same font size value, making it easy to predict how large or small font will appear**
-   _If you are interested in sizing elements consistently across an entire website, the rem measurement is the best unit for the job. If you’re interested in sizing elements in comparison to other elements nearby, then the em unit would be better suited for the job_

`%` -> relative unit of measurement. The default size of text in web browsers is 16 pixels, or 16px. When percentages are used, they set the size of text relative to this default size
