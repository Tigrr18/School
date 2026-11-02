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
5. [**Others:**](#evaluation-criteria-others) Portability, Generality & well-definedness

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
### Influences on language design
- Computer Architecture
  - Languages are developed around the most prevalent computer architecture, known as the **von Neumann** model
- Program design methodologies
  - New software development methodologies led to new programming paradigms and by extension, new programming languages
### The von Neumann "loop"
- Instruction processing utilizes a simple **fetch-decode-execute** processing loop
- A high level representation is as follows:
  - Initialize the program counter
  - Repeat until program ends:
    - Fetch the instructions pointed to by the counter
    - Increment the program counter
    - Decode the instruction, using the Control Unit
    - Execute the instruction using ALU and other circuitry
      - Read and write to memory if required
      - Jump to another instruction/location if required
  - End repeat
### Computer architecture influence
- Early language designers knew the physical architecture very well
- Direct mapping of the von Neumann model becaume the basis for imperative languages
  - Program variables model memory cells/addresses
  - Assignments statemenets model data transfer
    - "X = 4" models a transfer of the value 4 to a memory address
  - Looping constructs represent efficient iteration
    - While/for models a simple jump/goto instruction at the assembly level
### Programming methodologies influence
- In the early years (1950s and early 1960s) applications were often relatively simple
  - The primary concern was machine efficiency
  - In other words, we coded for the benefit of the computer, not the programmer
- By the late 1960s, "people efficiency" become more important
  - The focus: readability, better control structures
- Prominent themes initially included:
  - Organizing code in "units" that could be independently extended
  - More structured programming (minimize "go to" jumps)
  - In summary, we want to avoid haphazard "spaghetti" code
- By the 1970s we are moving from process-oriented design (i.e. collection of functions) to data-oriented design
- Main themes include::
  - Data abstraction (hiding implementation details)
  - Simple APIs for lists, trees, maps, etc
- By the mid 1980s, object-oriented programming is becoming common
  - Objects manage their own state
  - Data abstraction + inheritance + polymorphism
## 1.4: Implementation
### Language implementation methods
1. Compilation
  - Programs are translated into machine language
  - Common use: large commercial applications
2. Pure interpretation
  - Source code is directly processed by another program known as an interpreter
  - Common use: small programs where prior compilation may not be necessary or even possible
3. Hybrid implementation systems
  - A compromise between compilers and pure interpreters
  - Here, we compile into an intermediate form that is later interpreted by a run-time system
  - Common use: small and medium sized systems where efficiency/performance is not the first concern
### Layered few of computer
- The operating system and language implementation are layered over the computer's machine interface
- Note that a "hybrid" language (ex Java) actually consists of two levels:
  - The byte code compiler (ex: javac)
  - The virtual software tha interprets the byte code at runtime (ex: JVM)
### Compilation
- Here, we translate the high-level program (source language) into machine code (machine language)
  - This gives us relatively slow translation, but very fast execution
- The compilation process has several phases:
  1. **Lexical analysis:** converts characters in the source program into *lexical* units
  2. **Syntax analysis:** transforms lexical units into parse trees that represent the *syntactic structure* of the program
  3. **Semantic analysis:** generates intermediate code representing the *logical operations* of the program
    - like a pseudo assebly language
  4. **Code generation:** final binary machine code is generated
### The compilation process
- The logical model of the compiler architecture 
- In practice, a single framework can support multiple languages and CPUs
  - We simply plug in different language-specific parsers and/or CPU-specific machine code generators
### Linking and loading
- The programmer's code __and__ the system/library code must be combined together into a single executable application
- **Loading:** The process of identifying the various program components and reading them into memory
- **Linking:** The process of preparing references to variables and methods across all units so that the code functions as if it has been compiled as one single unit
  1. **Static** linking: all compiled units are actually combined into a single binary image
  2. **Dynamic** linking: libraries are loaded on-the-fly (i.e. at runtime) and may be shared across multiple applications
### Pure interpretation
- No source code translation is performed until runtime
  - Easy to port to other platforms since you don't have to generate any machine code
- Allows data types to be dynamically defined at runtime
  - Compiled languages generally require types to be pre-defined for the sake of efficiency
- Slower execution (10 to 100 times slower than compiled programs)
- It is now rare for traditional high-languages due to performance concerns
  - Exceptions to this may be found with languages meant to run within web browsers (ex: JavaScript, PHP)
  - Even here, source code may be converted to a simple intermediate form at runtime
### Pure interpretation process
- In comparison to the compiler model, this is a VERY simple design
  - Small/new languages are often prototyped this way
  - Production-quality compilers may take several years to develop
  - A small interpreter can be written in as litte as a few weeks
### Hybrid implementation systems
- Represents a compromise between compilers and true interpreters
  - A high-level language program is translated to an intermediate "language" - often called bytecode - that allows easy interpretation
  - Conversion can either be done beforehand or at run-time
- Code execution is faster than pure interpretation, as we do not have to perform lexical analysis, parsing, etc
- Examples include:
  - PERL programs are partially compiled into a simple bytecode in order to detect errors before subsequent interpretation
  - Initial implementations of Java used a sophisticated bytecode that mapped to an artificial CPU
    - The intermediate form provides portability to any machine that has a byte code interpreter and a run-time system (together, they are called the Java Virtual Machine)
### Hybrid implementation process
- In practice, the byte code can take different forms:
  - It could reseble human readable assembly language
  - It could be recorded in a binary format
- Either way, it does NOT correspond to any specific CPU
### just-in-time implementation systems
- Here, we initially translate programs to an intermediate format
- When the byte code version of the program is later executed, an associated language component compiles "popular" functions/methods into CPU-specific machine code
  - The machine code version is kept for subsequent calls
- In essence, JIT systems are "delayed" compilers
- Common examples include:
  - The JVM (The original byte code is converted into machine code at runtime)
  - Microsoft's .net languages essentially work the same way
### Preprocessors
- A preprocessor examines a source file(s) immediately before the program is compiled
- It identifies macros (i.e. commands) written in a special macro language and modifies/updates the source code accordingly
  - Essentially, it substitutes the macro with the new source code
  - Note that this macro language is NOT the same as the programming language
- A well-known example: C preprocessor
  - It expands #include, #define, and similar macros
  - For example, #include will literally insert the included code into the current source file
### Summary
- The study of programming languages is valueable for a number of reasons:
  - To increase our capacity to use different constructs
  - It enables us to choose languages more intelligently
  - It makes learning new languages easier
- The most important criteria for evaluating programming languages include:
  - Readability, writability, realiability, cost
- Major influences on language design have been machine architecture and software development methodologies
- The primary methods of implementing programming languages are compilation, pure interpretation, and hybrid implementations

# Module 2
## 2.1: Historical Language Evolution
### Module 2 topics
- Minimal/direct hardware programming
  - Machine code
  - Assembly language
- Compiled high language high level languages
  - Fortran
- Functionnal programming
  - LISP
- Atepts at *human friendly* coding
  - COBOL
- The first steps towards more structured programming
  - ALGOL
- Early dynamic languages
  - APL
- The beginnings of data abstraction
  - SIMULA
Early descendents of the ALGOLs
  - The C language
- Object oriented programming
  - Smalltalk
  - C++
  - Java
### Genealogy of common languages
- The chart starts (at the top) with the big domain specific languages (fortran, COBOL, and LISP)
  - neither Fortran nor COBOL have directly influenced the __sythax__ of many languages
- LISP leads to most of the common functional languages, including Clojure and Erlang
- The two OO pioneers (Simula and Smalltalk) lead to different streams (C++/Java versus Objective C)
- C influenced a broad group of languages, including C++, Java and even Python
### Machine code/Assebly language
- Machine code is the binary code that corresponds to the machine's basic instruction set
- Assembly language is the one-to-one mapping of the human readable mnemonics to the machine instructions
- Assembly language was developed early in the life of computers (Late 1940s-1950s)
- However, because of its direct mapping to the machine code, it has little effect on high level language design
### Minimal hardware programming
- What was wrong with using machine code?
  - Poor readability
  - Poor modifiability
  - Expression coding was tedious
    - Ex: ((X*3)+2)/(log(4)) was extremely tedious to code in
  - Machine deficiencies
    - In the meginningm, there was no simple indexing mechanisms, so it was hard to manipulate arrays
- Bottom line: difficult to code reliably and quickly
## 2.2: The Early High-level Languages
### IBM 704 and Fortran
- **For**mula **Tran**slating System
- Fortran I: 1957
  - Designed for the new IBM 704, which had index registers and floating point hardware
  - Encouraged a __compiled__ programming language because there was no place to hide the cost of interpretation
    - Before this, slower interpretation was okay since you had to wait for the software to emulate the floating point value anyway
  - Environment of development
    - Computers were small and unreliable
    - Applications were scientific
    - No programming methodology or tools
    - Machine efficiency was the most important concern
### Design process of Fortran
- Impact of environment on design of Fortran I
  - No need for dynamically allocated storage
    - Everything (I.e. data elements) were fixed at compile time
  - Need good array handling and counting loops
  - No string handling or any form of sophisticated input/output
    - Those things were for budiness software (e.g. COBOL)
### Fortran I overview
- First implemented version of Fortran:
  - Names could have up to six characters 
  - Post-test counting loop (do)
  - Conditional statements (if)
  - User-defined subprograms
  - No explicit data typing statements
    - Variables beginning with I, J, K, L, M and N were integers, the rest were floats
- Compiler released in April 1957, after 18 worker-years of effort
  - For a long time, compilers were REALLY hard to develop
- No separate compilation (of separate components)
  - Programs larger than 400 lines rarely compiled correctly, mainly due to poor reliability of 704
  - The computer would probably fail before the compilation was done
- Code was very fast
  - Within a factor of two of machine code
- Quickly became widely used
### Fortran versions
- Fortran II (1958)
  - Independent compilation
    - Compile only the parts you are adding/updating
- Fortran IV (1962)
  - Explicit type declaration
  - String handling
  - If/else structure
  - ANSI standard in 1966
- Various updates up to the present time
### Early Fortran program
```fortran
    INTEGER A,B,C
    READ(5,501) A,B,C
501 FORMAT(3I5)
    IF(A.EQ.0 .OR. B.EQ. .OR. C.EQ.0) STOP 1
    S = (A + B + C) / 2.0
    AREA = SQRT( S * (S - A) * (S - B) * (S - C))
    WRITE(6,601) A,B,C,AREA
601 FORMAT (4H A= ,I5,5H B=,I5,5H C=,I5,8H AREA= ,F10.2,12HSQUARE UNITS)
    STOP
    END
```
### Fortran evaluation
- Highly optimizing compilers
  - Partially enabled by the fact that types and storage of all variables are fixed before run time (eventually became more flexible)
- Dramatically and permanently changed the way computers are used
  - That said, it was not a direct influence on the syntax of specific languages
  - In other words, other languages were not designed to be a "better Fortran"
### Functional programming: LISP
- **LIS**T **P**rocessing Language
  - Designed at MIT by John McCarthy (1958)
- Syntax is influenced by the __*Lambda Calculus*__
  - Formal system by Alonzo Church for expressing computation based on function abstraction
- only two data types are used in LISP:
  - Atoms
  - Lists (can contain atoms or other lists)
- Well suited to AI research at the time:
  - Recursively Process data/symbols in lists
  - Symbolic computation (rather than number crunching)
    - E.g. natural language processing
### Functional Style
```lisp
(DEFUN equal_lists (list1 list2)
  (COND
    ( (ATOM list1) (EQ list1 list2) )
    ( (ATOM list2) NIL )
    ( (equal_lists (CAR list1) (CAR list2))
      (equal_lists (CDR list1) (CDR list2)) )
    (T NIL)
  )
)
```
### LISP evaulation
- Pioneered functional programming
  - no need for variables or assignment statements
  - Control via recursion and conditional expressions
  - COMMON LISP, Scheme and now Clojure are contemporary dialects of LISP
- ML, Haskell, and F# are also functional programming languages, but use very different fyntax
  - We can distringuish between pure functional languages (e.g. Haskell) and others that provide a mix of functional and imperative (e.g. F#)
### COBOL
- **CO**mmon **B**uisness **O**riented **L**anguage
- First design meeting in 1959
- Design goals
  - Must look like simple english
  - Must be easy to use, even if tat means it will be less powerful
  - Must broaden the base of computer users, presumably to include non-progammers
  - Must not be biased by current compiler problems
- Design committee members were all from computer manufacturers and DoD branches
- Syntax based loosely on a language called Flow-Matic
### COBOL code
``` cobol
IDENTIFICATION DIVISION
PROGRAM-ID. Multiplier.
AUTHON. John Smith.
* Example program using ACCEPT, DISPLAY and MULTIPLY to
* get two single digit numbers from the user and
* multiply them together

DATA DIVISION.
WORKING-STORAGE SECTION.
01 Num1       PIC 9 VALUE ZEROS.
01 Num2       PIC 9 VALUE ZEROS.
01 Result     PIC 99 VALUE ZEROS.

PROCEDURE DIVISION.
DISPLAY "Enter first number (1 digit) : " WITH NO ADVANCING.
ACCEPT Num1.
DISPLAY "Enter second number (1 digit) : " WITH NO ADVANCING.
ACCEPT Num2.
MULTIPLY Num1 BY Num2 GIVING Result.
DISPLAY "Result is = ", Result.
STOP RUN.
```
## 2.3: New Language Concepts
### ALGOL
- **ALGO**rithm **L**anguage
  - Work began in the late 1950s
  - ALGOL 60: major influential version
- Meant to be a little more abstract
  - Not tied to any specific computer architecture
- Some of the many additions:
  - Concept of data type was formalized
  - Names could be any length
  - Arrays could have any number of subscripts
  - Subscripts were placed in brackets
  - Compound statements (BEGIN ... END)
  - IF had an ELSE-IF clause
### ALGOL 60 sample
```algol
procedure Absmax(a) Size:(n,m) Result:(y) Subscripts:(i,k);
  value n, m; array a; integer n, m, i, k, real y;
comment The absolute greatest element of the matrix a, of size n by m,
        is transfered to y, and the subscripts of this element to i and k;
begin
  integer p, q;
  y := 0; i := k := 1;
  for p := 1 step 1 until n do
    for q := 1 step 1 until m do
      if abs(a[p,q]) > y then
        begin
          y := abs(a[p, q]);
          i := p; k := q
        end
end Absmax
```
### ALGOL 60 evaluation
- Successes
  - It was the standard way to publish algorithms for over 20 years
  - Virtually all subsequent imperative languages are based on it (including C)
  - First language whose syntax was formally defined by BNF (Backus Naur Form)
    - Standard mechanism by which languages grammars are defined, even today, eg:
    - ```<list> ::= <term> | <term> <optional-whitespace> <list>```
    - **Translation:** a list is made up of a single term (defined elsewhere in the grammar) OR a term, an optional whitespace, and then another list (recursive definition)
- Downside: Never really succeeded commercially
### APL: an early dynamic language
- APL: **A** **P**rogramming **L**anguage
- Characterized by dynamic typing and dynamic storage allocation
  - Determined at runtime rather than compile time
- This means:
  1. Variablers are __untyped__ at the source code level
    - A variable acquires a type when it is assigned a value
  2. Storage is allocated to a variable when it is assigned a value
### APL evaluation
- Designed originally as a hardware description language (not an actual programming language) at IBM by Ken Iverson around 1960
  - Highly __expressive__ (many operators, for both scalars and arrays of various dimensions)
  - Use of non-traditional symbols required special input mechanism
  - Programs are __very__ difficult to read
- Still in (very) limited use
  - But influential in terms of the focus on dynamic execution
### Beginnings of data abstraction: SIMULA 67
- Designed primarily for system simulation in Norway by Nygaard and Dahl: **SIMU**lation **LA**nguage
  - A language to model complex entities interaction across discrete time units
  - Basic syntax based on ALGOL 60
- Primary contributions
  1. Co-routines - cooperating subprograms
  2. Classes, objects and inheritance
- Widely considered to be the first Object Oriented language
  - Became a heavy influence for the OO design of C++
  - Other languages, in turn, were influenced by C++ (Java)
```simula
Class Rectangle (width, Height); Real Width, Height;
    ! Class with two parameters;
  Begin
    Real Area, Permimeter; ! Attributes;

    Procedure Update;
    Begin
      Area := Width * Height;
      Perimeter := 2*(Width + Height)
    End of Update;

    Boolean Procedure IsSquare;
      IsSquare := Width=Height;
    
    Update;   ! Initialize new rectangle;
    OutText("Rectangle created: ");
    OutFix(Width,2,6);
    OutFix(Height,2,6);
    OutImage

  End of Rectangle;
```
### C - 1972
- Designed for systems programming
  - Developped at Bell Labs by Dennis Richie
  - In conjunction with the UNIX OS
- Evolved primarly from BCLP and B, but also ALGOL 68
- Powerful set of operators, but relatively weak type checking 
  - Initial version did not even check function parameters
- Not particularly innovative itself
  - Initially spread through UNIX (at universities)
  - __**Free**__ open source compilers
- Though designed as a systems language, it has been used in many application areas
### PROLOG
- **PRO**gramming **LOG**ic
- Developed by Comerauder and Roussel (University of Aix-Marseille) in early 1970s
- Based on formal logic
  - Non-procedural (no function/method definition)
  - relied on the application of "rules"
- Can be summarized as being an intelligent database system that uses an inference process to infer the truth of given queries
- Comparatively inefficient
- Few application areas
  - Sometimes used to do matching again things like a family tree or animal kingdom
### PROLOG example
- Assuming the following rule set
```prolog
mother_child(trude, sally).

father_child(tom, sally).
father_child(tom, erica).
father_child(mike, tom).

sibling(X,Y)  :- parent_child(Z, X), parent_child(Z, Y).

parent_child(X, Y) :- father_child(X, Y).
parent_child(X, Y) :- mother_child(X, Y).
```
- A query could be resolved as follows
```prolog
?- sibling(sally, erica)
  Yes
```
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
  - \>
  - \>=
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
