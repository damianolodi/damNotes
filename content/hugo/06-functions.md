---
title: "Functions"
date: 2019-08-06T21:19:34+02:00
summary: "Hugo functions"
tags: ["hugo"]
draft: false
---

All functions are reported in the [documentation](https://gohugo.io/functions/).

* * *

-   `{{ .Site.Params.homeText | markdownify }}` → access the _site parameter_ `homeText` (in the _config_ file) and apply the [markdownify](https://gohugo.io/functions/markdownify/#readout) function

-   `{{ $css := "css/bootstrap.min.css" | absURL }}` → **define a variable** and apply the [absURL](https://gohugo.io/functions/absurl/) function

-   `{{ hugo.Generator }}` → add in the html head to display the hufo version as a metadata in the source code

* * *

### String Manipulation

-   `{{ print SOMETHING }}` → print the argument using the Golang [print](https://gohugo.io/functions/print/#readout) function. See `printf` to apply string [format](https://gohugo.io/functions/printf/#readout)
