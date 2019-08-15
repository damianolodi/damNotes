---
title: "Variables"
draft: false
---

-   Define the variable using

```css
body {
    --var-name: value;
}
```

_It becomes available to use inside the element in which you create it and within any elements nested within it._

-   By creating your variables in `:root`, they will be **available throughout the whole web page**

```css
:root {
    --var-name: value;
}
```

One can then over-write these variables by setting them again within a specific element.

-   **Assign** the variable using

```css
div {
    background: var(--var-name);
}
```

-   Use this to _prevent older browsers_ that doesn't support variables

```css
div {
    background: var(--var-name, black);
}
```
