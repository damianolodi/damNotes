---
title: "Atom"
draft: false
---

# Python in Atom

## Packages List

-   `Script` -- to run code in Atom
    		\* `cmd + i` to run the script
-   Disable `autocomplete-plus` and `autocomplete-snippest`
-   Install `autocomplete-python`
-   Install `file-icons`
-   Install `minimap` - when working on big screens and on big scripts
-   Install `python-autopep8`
    		_ Enable `Format on Save`
    		_ Install autopep8 with `pip`
-   Install `linter-flake8` -- to correct error
    		\* Install `flake8` with `pip`

## Editor Settings

-   Select `Scroll past the end`
-   Tab lenght set to `4`
-   To increase the font size go to Settings -> Themes -> Your Stylesheet and print


    // font size for the script viewer
    .script-view .line {
      font-size: 16px;
    }

## Anaconda distribution

-   To test if the installation added it to our path, write `python` in the terminal
-   To see where python was installed and where is our actual local environment, use `which python`
-   To list all the packages installed write `pip list` or `conda list` -- the second can be used also to install packages that are not python related (??)
