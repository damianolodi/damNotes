---
title: "Python Installation and Setup"
draft: false
arguments: []
weight: 19
---

### Installation

#### macOS
    
- Download the installer of Python 3 form the official website and install it. An application calle _Python_ will be created in the _Applications_ folder

- Create an alias so that `python` command will call `python3` instead
    
    - in `Users/user_name/` type `nano ~/.bash_profile`

    - check that the last line is adding python to the path calling `PATH=...`

    - write `alias python=python3` at the bottom of the file

#### Windows

- Download the installer of Python 3 form the official website and install it. Make sure to check the _Add Python to your path_ option during the process

- Check the installation calling `python --version` in the powershell

* * *

### VS Code Setup

#### Shortcuts

-   `cmd + shift + P` → open command palette

-   Python interpreter used (version) is displayed in the botton left corner. Can be changed clicking on that

-   When modify settings in json, on the left of each line there is an icon that suggest all the possible value for each parameter

#### Extensions

-   **Python**

-   **vscode-icon**
-   

#### Settings

-   **color themes** → default dark theme is ok

-   **file icons** → _vscode-icon_ or _material icon theme_

-   open user settings and place the following code

```json
    "workbench.settings.editor": "json",
    "workbench.settings.openDefaultSettings": true,
    "workbench.settings.useSplitJSON": true,
    "editor.fontSize": 16,
    "debug.console.fontSize": 16,
    "terminal.integrated.fontSize": 16,
    "python.formatting.provider": "black",
    "editor.formatOnSave": true
```

    - then reopen the settings so that _global settings_ and _user settings_ are side by side

    - place `"python.pythonPath": "python_path"` where *python_path* is the path returned by the command `which python3` in Termianl. This will change the defaul python interpreter

    - for each project, one can create a virtual env. and select as the interpreter. VS Code will use it as the default env. for the project when run in the integrated termianl

#### Resources

-   [VS Code Python Setup on Mac](https://youtu.be/06I63_p-2A4) - Corey Schafer

* * *

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
