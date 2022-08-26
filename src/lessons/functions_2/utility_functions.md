# 6.2 Utility Functions

Estimated Time: 40 Minutes

In this section, you will more about functions from a design perspective.

## Import Your Own Functions
We previously discussed a way to import basic modules from outside your code. Here we will check how do we import functions from our code.
Sometimes we need to design a program across many files where each of them has the implementation of specific functions.

A main function would need to import specific functions from these files.
Imagine that you have a file called `areas.py` where you have the following function:

```
def square_area(length, width):
    return length * width
```
You are implementing another general module that calculates areas of shapes. You can import this function by:

```
# Import statment
from areas import square_area

# Usage example
sq_area = square_area(10, 20) 
```

You can also change the name of the function at import - example:

```
# Import statment
from areas import square_area as sq

# Usage example
sq_area = sq(10, 20)  
```
### dir() built-in function

## Design with Functions (Utilities)
Whenever you start thinking about implementing a program. You need to take some points into consideration regarding manageability of your code.

### Functions added value
Examples of some aspects to check when start thinking about functions:
- Reusability: Functions are reusable parts of code that can be called at any part of the whole program. Try to identify the most repetitive parts of your code and move them into functions.  
- Readability: The first point can support this point. Moreover, Having clean functions with clear names increases the readability of your code with assists other programmers to integrate well with your program.
- Function Stack: When implementing functions, you need to make sure that they integrate well. Avoid the case where you have many functions calling each other where eah functions implements a tiny operation.

### Utilities
A main concept to approach coding problems is **Divide & Conquer**. Taking a big problem and decompose it into smaller ones. 
In a program, implementing a wide flow can take several steps. Approaching each one of these steps as a standalone problem may make it easier to implement. Each step can take the form of function.
A gorup of internal functions that we implement for our own usage are called **utility functions**.

Imagine that you are asked to implement a program that heavily depends on basic calculation operations (addition, division, subtraction, multiplication). At this case it makes sense to have an internal module called `utilities.py` that implements all of these functions.
An example usage of the module would be something like:
```
from utilities import addition, division, subtraction, multiplication

    def student_average(students, stdudent_count):
        sum = 0 
        for student in students:
            sum = student['mark']
        
        avg = division(sum, stdudent_count)
```
## Simple Use Case