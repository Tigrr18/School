# Module 9
## Module 9.1
### Introduction
- Basic Structure of a Python Program
- Indentation
  - Why use whitespace
- Flow control
  - While loop
  - For loop
    - Range statement
  - If and elif
- Functions
  - Syntax
  - Parameters
  - Default arguments
### Indentation
- As previously noted, python uses whitespace to delimit coding blocks
  - No curly braces, other than for data structures like dictionaries
- Whitespace can be tab or spaces
- Note: either works, but they should not be mixed in the same file
- In general, python recommends using 4 spaces rather than tab
  - IDE can usually be configured to do this automatically

## Module 9.2
### Python Functions
- Python provides function definition
``` python
def foo(number):
  print("my number is ", number)
  return number * 2
```
- Note the following
  - functions are introduced with the **def** keyword
  - parameters require **no type**
  - return types are also not explicitly specified
  - we again use ":" and whitespace to define the function block
  - function return **none** by default
- python arguments use pass-by-value
  - essentially the same as C and Java
  - Keep in mind that references to objects allow you to change object members inside the function, just like Java
- Also note that functions can be assigned to variables
  - lets say that we have a function called boo()
  - so we can do an assingment as follows
  - ```python
    boo2 = boo
    ```
  - boo2 is now essentially an alias for the same function
  - dont get carried away with this, it can become very confusing
### Default Argument Values
- nice feature of Python is to configure default arguments
- allows proammers to specify defaul values for the arguments that are not provided by the function's user
- default are specified as "far=default"
```python
def foo(mun, text="text", thing=43.5):
  print("my num is ", num)
  print("my text is ", text)
  print("my thing is ", thing)
```
- If no default is provided, then the argument **must** be provided
- Once a default parameter is specified in the function definition, any remaining parameters **must also** have defaults
```python
def foo(n, x=2, m) #invalid synthax
foo(3,4) # no way to know if 4 is x or m
```
- If a subset of args are provided, they are applied to the parameters in a left to right order
- you can change this order by explicitly providing the parameter name
```
def foo(n, m=4, z=3):

foo(3, z=7) #okay call, m is default to 4
```
