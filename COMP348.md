# COMP 348 - Principles of Programming Language
Class on different types of programming languages
Midterm: Nov 4th, in class
Midterm material: up to end of Module 9
Final:

Links:
- Module 1
  - 1.1: Introduction
  - 1.2: Language Evaluation
  - 1.3: Influences on Language Design
  - 1.4: Implementation
- Module 2
  - 2.1: Historical Language Evolution
  - 2.2: The Early High-level Languages
  - 2.3: New Language Concepts
  - 2.4: Object Orientation and the Modern-Era
- Module 3
  - 3.1: Intro to C
  - 3.2: Preprocessing and Header Files
  - 3.3: Console Display
- Module 4
  - 4.1: Functions and Files
  - 4.2: Creating Header Files
  - 4.3: Visibility
- Module 5
  - 5.1: Basic Data Types
  - 5.2: Arrays and Structs
  - 5.3: Static and Automatic Memory Allocation
  - 5.4: Dynamic Memory Allocation
  - 5.5: C Strings
  - 5.6: Parameter Passing
- Module 6
  - 6.1: Debugging
  - 6.2: Profiling
- Module 7
  - 7.1: Python Intro
  - 7.2: Basic Data Types
  - [7.3: Composite Data Types](#module74)
  - [7.4: Computational Complexity](#module74-computational-complexity)
- [Module 8](#module-8)
  - [8.1: List Extensions](#module-81-list-extensions)
  - [8.2: Dictionaries](#module-82-dictionaries)
  - [8.3: Tuples and Sets](#module-83-tuples-and-sets)
- [Module 9](#module-9)
  - [9.1: Control Flow](#module-91-control-flow)
  - [9.2: Python Functions](#module-92-python-functions)

# Module 7
## 7.1: Python Intro
## 7.2: Basic Data Types
## 7.3: Composite Data Types
## 7.4: Computational Complexity

# Module 8
## Module 8.1: List Extensions
## Module 8.2: Dictionaries
## Module 8.3: Tuples and Sets

# Module 9
## Module 9.1: Control Flow
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

### Purpose
- ZEN principle
  - Intended to be simple and clean
  - Removing curly braces makes code much less clutter
- White space indentation makes sure everyone’s code essentially looks the same
  - We dont have 10 styles of indentations
- Second reason: an if can work without curly braces for one line, but if this if gets updated, we need to add them in or there will be issues  (even if tabbing looks right)

### While Loops
- Python provides conventional control flow statements
- Loops can be provided with either the while or for constructs
- Keep the following in mind:
  - Conditional expression does not require delimiters
    - While x < 1 works as well as while (x < 1)
  - The use of “:” after the expression
  - The contents of the while loop are indented
  - The while loop ends when the indentation ends

### For Loops
- Python uses a simple for loop style that resembles java’s for-each
```python
For x in y:
```
- The “in” keyword separates the singular element name from the “array”
- The variable following in simply has to be a sequence type
  - Items are iterated over in order
- Like in C and Java, loops can also use break and continue

### Range
- For loops are often used with the range function
- This can be used to define a sequence of values for the loop iteration
- Ranges are inclusive/exclusive, i.e. they do not include the last value in the range
- Ranges can also have a start/end
```python
Range (4,8) #from 4 to 7
```
- They can also have a step
```python
Range (4,10,5) #from 4 to 19 by steps of 5
```

### If statements
- If statements are very similar to other languages
- Also utilizes “elif” (else if) logic and a final else
  - A “:” must be used on each like
- Note: originally, there was no switch case statement in python, however, python now has a match case statement

### Testing and Conditionals
- Python includes the values True and False that may be used in conditional evaluations
- Rather than NULL, python uses none to indicate non-existant value
- The boolean operators, from highest to lowest priority are:
  - Not
  - And
  - Or
- Both and and or only evaluate the second operand if necessary
Conditional operations are similar to other languages and include:
  - <
  - <=
  - >
  - >=
  - ==
  - !=
- We also have a couple of tests for object identity
  - Is
  - Is not

## Module 9.2: Python Functions
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
```python
def foo(n, m=4, z=3):

foo(3, z=7) #okay call, m is default to 4
```
