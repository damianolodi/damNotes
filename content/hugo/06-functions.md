---
title: "Functions"
draft: false
arguments: []
weight: 6
---

All functions are reported in the [documentation](https://gohugo.io/functions/).

* * *

-   `{{ .Site.Params.homeText | markdownify }}` &rarr; access the _site parameter_ `homeText` (in the _config_ file) and apply the [markdownify](https://gohugo.io/functions/markdownify/#readout) function

-   `{{ $css := "css/bootstrap.min.css" | absURL }}` &rarr; **define a variable** and apply the [absURL](https://gohugo.io/functions/absurl/) function

-   `{{ hugo.Generator }}` &rarr; add in the html head to display the hufo version as a metadata in the source code

* * *

### String Manipulation

-   `{{ print SOMETHING }}` &rarr; print the argument using the Golang [print](https://gohugo.io/functions/print/#readout) function. See `printf` to apply string [format](https://gohugo.io/functions/printf/#readout)

* * *

### Range

-   `{{ range $index, $value := .Pages }}` &rarr; range and assign an index to each iteration

* * *

### Conditionals

-   `{{ if (op arg1 arg2) }} {{ else if (op arg1 arg2) }} {{ else }} {{ end }}` &rarr; `op` is operator:
    -   `eq` &rarr; equal
    -   `lt` &rarr; less than
    -   `le` &rarr; less than or equal to
    -   `gt` &rarr; greater than
    -   `ge` &rarr; greater than or equal to
