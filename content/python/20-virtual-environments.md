# Virtual Environments
Install `virtualenv` if you don't have it.

## Creating a virtual environment
`cd` into the project folder and type
```
conda create --name project-name-env dependecy1 dependency2 ...
```

## Activate and deactivate environments
To activate an environment type
```
source activate project-name-env
```
To deactivate use
```
source deactivate project-name-env
```

## Export the environment
To export the environment, to keep track and have the possibility to reproduce the environment if something go wrong, create a `.yaml` file with
```
conda env export > environment.yaml
```

To create a virtual environment from a `.yaml` file use
```
conda env create -f environment.yaml
```

## List all the environments
To list all the environments on the machine, and to know where they are located, use
```
conda env list
```

- - - -
#code/python/tips