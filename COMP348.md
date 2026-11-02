# COMP 348 - Principles of Programming Language
Class on different types of programming languages
Midterm: Nov 4th, in class
Midterm material: up to end of Module 9
Final:

Links:
- [Module 1](#module1)
  - [1.1: Introduction](#11-introduction)
  - [1.2: Language Evaluation](#12-language-evaluation)
  - [1.3: Influences on Language Design](#13-influences-on-language-design)
  - [1.4: Implementation](#14-implementation)
- [Module 2](#module2)
  - [2.1: Historical Language Evolution](#21-historical-language-evolution)
  - [2.2: The Early High-level Languages](#22-the-early-high-level-languages)
  - [2.3: New Language Concepts](#23-new-language-concepts)
  - [2.4: Object Orientation and the Modern-Era](#24-object-orientation-and-the-modern-era)
- [Module 3](#module3)
  - [3.1: Intro to C](#31-intro-to-c)
  - [3.2: Preprocessing and Header Files](#32-preprocessing-and-header-files)
  - [3.3: Console Display](#33-console-display)
- [Module 4](#module4)
  - [4.1: Functions and Files](#41-functions-and-files)
  - [4.2: Creating Header Files](#42-creating-header-files)
  - [4.3: Visibility](#43-visibility)
- [Module 5](#module5)
  - [5.1: Basic Data Types](#51-basic-data-types)
  - [5.2: Arrays and Structs](#52-arrays-and-structs)
  - [5.3: Static and Automatic Memory Allocation](#53-static-and-automatic-memory-allocation)
  - [5.4: Dynamic Memory Allocation](#54-dynamic-memory-allocation)
  - [5.5: C Strings](#55-c-strings)
  - [5.6: Parameter Passing](#56-parameter-passing)
- [Module 6](#module6)
  - [6.1: Debugging](#61-debugging)
  - [6.2: Profiling](#62-profiling)
- [Module 7](#module7)
  - [7.1: Python Intro](#module71-python-intro)
  - [7.2: Basic Data Types](#module72-bsaic-data-types)
  - [7.3: Composite Data Types](#module73-composite-data-types)
  - [7.4: Computational Complexity](#module74-computational-complexity)
- [Module 8](#module-8)
  - [8.1: List Extensions](#module-81-list-extensions)
  - [8.2: Dictionaries](#module-82-dictionaries)
  - [8.3: Tuples and Sets](#module-83-tuples-and-sets)
- [Module 9](#module-9)
  - [9.1: Control Flow](#module-91-control-flow)
  - [9.2: Python Functions](#module-92-python-functions)

# Module 1
## 1.1: Introduction
### Module 1 Topics
- Reasons for studying principles of programming languages
  - Programming domains
  - Language Categories
- Language evaluation criterias
  - Language design trade-offs
- influences on language design
- implementation methods
### Why do we care?
- increased ability to express ideas
- improved background for choosing appropriate languages
- increased ability to learn new languages
- better understanding of the significance of the language implementation
- better use of languages that are already known
### Programming domains
- Scientific application
  - Large numbers of floating point calculations
  - Extensive use of Arrays and Matrices
  - Classic Language Example: Fortran
- Buisness applications
  - Produce reports
  - Extensive charater/text support
  - Native support for Decimal numbers (Monetary values)
  - Classic Language Example: COBOL
- Artificial Intelligence
  - Manipulation of symbols rather than numbers
  - linked lists were the fundamental data type
  - Classic language example: LISP
- System programming
  - Need efficiency because of continuous use
  - Ideally suited for operating systems, compilers, etc
  - Classic language example: C
- Web software
  - Eclectic collection of languages
  - Markup: HTML
  - Scripting: PHP
  - General-purpose: Java
### Language categories
- Imperative:
  - Central features are variables, assignment statements, and iteration
  - includes languages that support object-oriented programming
  - includes scripting languages
  - Common examples: C/C++, Java, Perl, JavaScript, Go, Python, Rust, Swift
- Functional:
  - Primary means of making computations is by applying functions to given parameters
  - doesnt rely on variable assignment or iterations (loops)
  - Common examples: LISP, Scheme, Clojure, Haskell, F#
- Logic
  - Rule-Based (Builds on formal logic)
  - No specific ordering of statements
  - Common example: Prolog
- Markup/Programming Hybrid
  - Tag-Based text documents
  - Sometimes extended to support some programming
  - Common Examples: HTML, XML

## 1.2: Language Evaluation
### Language Evaluation Criteria
1. [**Readability:**](#evaluation-criteria-readability) The ease with which programs can be read and understood
2. [**Writability:**](#evaluation-criteria-writability) The ease with which a language can be used to create programs
3. [**Reliability**](#evaluation-criteria-reliability) Conformance to specifications (i.e. consistently does what it is expected to do)
4. [**Cost:**](#evaluation-criteria-cost) The __total__ cost associated with the use of the language
5. [**Others:**](#evaluation-criteria-others) Portability, Generality & well-definedness👍

### Evaluation Criteria: Readability
- Overall simplicity
  - A manageable (concise) set of features and constructs
    - Special words/keywords (ex: while, for, int)
    - Operators (ex: +, -, /)
- Orthogonality
  - A relatively small set of primitive constructs can be combined in a relatively small number of ways
  - We want to avoid special cases that depend on the context
    - for example, assebly languages sometimes have multiple ADD instructions, that each depend on the location of the operands
      - ADDR(X, Y): Add two register values together
      - ADDM(X, Y): Add two operands from memory
    - This is __less__ orthogonal than a single *location-agnostic* ADD
- Adequate supply of __built-in__ data types
  - Primitives like integers and floats
  - Composite types like lists and trees
- Synthax considerations
  - Flexible composition rules for identifiers
  - Special words and methods that can be used to form complex new/novel structures
  - Self-descriptive (se;f-documenting) constructs and intuitive/meaningful keywords
### Evaluation Criteria: Writability
- Simplicity and orthogonality
  - Few constructs, a small number of primitives, a small set of rules for combining them
- Support for abstraction and code re-use
  - The ability to define and use complex structures or operations in ways that allow details to be ignored
    - Object oriented programming is an obvious example of this
    - Java generics and C++ templates are more sophisticated examples
  - Expressivity
    - The ability to accomplish a lot with a relatively modest amount of code
      - Strength and number of operators and predefined functions
### Evaluation Criteria: Reliability
- Type checking 
  - Automatic testing for tgype usage errors
    - ex, are we adding types that can actually be combined
- Exception handling
  - intercept run-time errors and corrective measures
- Aliasing
  - Presence of two or more distinct referencing methods for the same memory location (Ex: A = B = New Dog("Spot");)
  - This often introduces very subtle bugs when code is modified by one reference
- Readability and Writability
  - A language that does not support "natural" ways of expressing an algorythm will require the use of "unnatural" approaches, and hence reduce reliability
### Evaluation Criteria: Cost
- Monetary costs
  - Training programmers to use the language
  - Writing programs
    - Poor applicability to the application domain increases development time
  - Language tools (open source or not? how costly is the software)
  - Maintaining and updating programs
- Code costs
  - Compilation (source code translation efficiency)
  - Run-time performance
### Evaluation Criteria: Others
- Portability
  - The ease with which programs can be moved from one architecture to another (Operating system, CPU, etc)
    - Java and its JVm are very portable
    - C, with its low-level compilers, will depend on machine hardware, therefore not very portable
- Generality
  - The applicanbility to a wide range of applications
- Well-definedness
  - The completeness and precision of the language's official definiton
    - ex: proper standardization
## 1.3: Influences on Language Design
## 1.4: Implementation

# Module 2
## 2.1: Historical Language Evolution
## 2.2: The Early High-level Languages
## 2.3: New Language Concepts
## 2.4: Object Orientation and the Modern-Era

# Module 3
## 3.1: Intro to C
## 3.2: Preprocessing and Header Files
## 3.3: Console Display

# Module 4
## 4.1: Functions and Files
## 4.2: Creating Header Files
## 4.3: Visibility

# Module 5
## 5.1: Basic Data Types
## 5.2: Arrays and Structs
## 5.3: Static and Automatic Memory Allocation
## 5.4: Dynamic Memory Allocation
## 5.5: C Strings
## 5.6: Parameter Passing

# Module 6
## 6.1: Debugging
## 6.2: Profiling

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
