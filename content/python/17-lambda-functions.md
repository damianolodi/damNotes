# Lambda Functions
Small anonymous functions can be created with the [lambda](https://docs.python.org/2/reference/expressions.html#lambda) keyword.
This function returns the sum of its two arguments
```py
lambda a, b: a+b

lambda val: val > 1000000
``` 
* **Lambda functions can be used wherever function objects are required.**
They are syntactically restricted to a single expression. Semantically, they are just syntactic sugar for a normal function definition. 
Like nested function definitions, lambda functions can reference variables from the containing scope
- - - -
#code/python/tips