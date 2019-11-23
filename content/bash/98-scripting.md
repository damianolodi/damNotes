---
title: "Scripting"
draft: false
arguments: ["Interpreter",
            "Arguments",
            "Execution Permission"]
weight: 98
---

First line should always be

```bash
#!/bin/bash
```

This is a sort of _special comment_ which tells the program which type of shell it should use to translate what is written in the following lines. (E.g. if `#!/bin/python` is written, the following code is interpreted as python code)

- `var_name="value"` &rarr; declare a variable

- `$var_name` &rarr; access the value of a variable

- `$1`, `$2`,... &rarr; placeholders which access the arguments passed to the scprit when run

```bash
    var_name=$1 # assign the first argument passed to this variable
```

* * *

After the script is complete, type in the terminal

```bash
chmod +x script_name.sh
```

to give execution permission to the file. Otherwise, it is just a common text file that cannot be executed.

- `+x` add the execution permission to all users

To run it, use `./script_name.sh`. If `script_name.sh` is used, it will not work because, in this case, the system will search the command in one of the directoried listed in the _PATH_ variable.

From now on, the `ls` command will display the script with a different color to accentuate that it has execution permissions.

* * *

### Exit Status

If not specified differently, each script will exit with _exit status_ equal to _0_. This can be verified by running the script and writing `$?` in the terminal.

- `$?` &rarr; **access the _exit status_** of the last program ran.

To change the _exit status_, use the command `exit n` in the script, where `n` is a number. This will also terminate the script. (Are you sure??) Usually, 0 indicates that everything was successfull, while different integer values are uset to communicate different types of error.

It can also be usefull to verify if an error occured from inside the script itself, or one can even create scripts to correct possible errors:

```bash
<something>

if [[ $? == 0 ]]
then
    echo "Tutto ok"
else
    <code>
fi
```
