# 6.2 Helper Functions

Estimated Time: 40 Minutes

In this section, you will more about functions from a design perspective.

## Import Your Own Functions
We previously discussed a way to import basic modules from an outer code. Here we will check how do we import functions from our code.
Sometimes we need to design a program across many files where each of them has an implementation of specific functions.

A main function may need to import other helper functions from within your project.
Imagine that you have a file called `areas.py` where you have the following function:

```python
def square_area(length, width):
    return length * width
```
You can use this `helper function` when implementing another general module that calculates areas of shapes: 

```python
# Import statment
from areas import square_area

# Usage example
sq_area = square_area(10, 20) 
```

If you do not like the name of the original function but you still want to use it. You can also change the name of the function at import - example:

```python
# Import statment
from areas import square_area as sq

# Usage example
sq_area = sq(10, 20)  
```
### dir() built-in function
One way to know what functions does a module provide is by using the built-in function called `dir()`
for example - it we want to check attributes and functions within `random` module, we may do something like:

```python
import random
 
# Prints list which contains names of
# attributes in random function
print("The contents of the random library are::")
 
# module Object is passed as parameter
print(dir(random))
``` 
Output:
```python
The contents of the random library are ::

['BPF', 'LOG4', 'NV_MAGICCONST', 'RECIP_BPF', 'Random', 'SG_MAGICCONST',
'SystemRandom', 'TWOPI', '_BuiltinMethodType', '_MethodType', '_Sequence',
'_Set', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__',
'__name__', '__package__', '__spec__', '_acos', '_ceil', '_cos', '_e', '_exp',
'_inst', '_log', '_pi', '_random', '_sha512', '_sin', '_sqrt', '_test', '_test_generator',
'_urandom', '_warn', 'betavariate', 'choice', 'expovariate', 'gammavariate', 'gauss',
'getrandbits', 'getstate', 'lognormvariate', 'normalvariate', 'paretovariate', 'randint',
'random', 'randrange', 'sample', 'seed', 'setstate', 'shuffle', 'triangular', 'uniform',
'vonmisesvariate', 'weibullvariate']
```

> **_NOTE:_**  dir function have other usages which are out of the scope of this lesson.

## Design with Functions (Helpers/Utilities)
Whenever you start thinking about implementing a program. You need to take some points into consideration regarding manageability of your code.

### Functions added value
Examples of some aspects to check when start thinking about functions:
- **Reusability:** Functions are "reusable parts" of code that can be called at any part of the whole program. Try to identify most repetitive parts of your code and move them into functions.  
- **Readability:** This is related somehow to the first point. Moreover, having clean functions with clear names increases readability of your code which assists other programmers to integrate well with your program.
- **Function Stack:** When implementing functions, you need to make sure that they integrate well. Avoid the case where you have many functions calling each other where each function implements a tiny operation.

### Helper Functions
One of the main concepts to approach coding problems is **Divide & Conquer**. Taking a big problem and decompose it into smaller ones. 
In a general software program, implementing a long flow can take several steps. Approaching each one of these as a standalone problem may make it easier to implement. 
Each step can take the form of one or more functions depending on its complexity level.
A group of internal functions that we implement for our own usage are called **helper functions**.

Imagine that you are asked to implement a program that has a high dependency on basic calculation operations (addition, division, subtraction, and multiplication). 
At this case it makes sense to have an internal module called `helpers.py` that implements all of these functions.
An example usage of the module would be something like:
```python
from helpers import addition, division, subtraction, multiplication

    def student_average(students, stdudent_count):
        sum = 0 
        for student in students:
            sum = student['mark']
        
        avg = division(sum, stdudent_count)
```
## Simple Use Case
At this section, we will study a use case where we need to apply the **Divide & Conquer** strategy in our design.

Imagine the case that you are asked to design and implement a software program to assist 7th grade students in understanding how to calculate area of various shapes.
The program starts by asking the user to enter a shape from a list, for example:
- Rectangle
- Circle 
- Triangle

Based on this choice, the program continues by asking the user for needed inputs to calculate the area of the needed shape.

One option is to implement the whole code into one long file that has functions for the areas of each shape. In that case:
- What would happen when you need to add a new shape function? And where? What will happen if you need to widen your project to have another feature?
- Imagine that you need to use same shape functions at another project. How would you do that? 
- A team member of yours wants to give you a hand in implementation - how would you organise this ?

On the other hand, let us break the problem into two parts (and then check previous mentioned points):
- Part 1 - **Core Functions** - Main operational functions that the whole program would need.
- Part 2 - **Main Flow** - Program flow and steps that would use core functions to implement the flow of the program and user interaction.

We will start by implementing core functions into an internal module called `utilities.py` that may look like:

```python
from math import pi

def circle_area(radius):
    area = float(pi*r*r)
    return area 

def rectangle_area(length, width):
    area = float(length * width)
    return area

def triangle_area():
    are = float((base*height)/2)
    return area
```
Once we have our core functions ready for usage, we can proceed by implementing the flow itself, which may look like:

```python
from utilities import circle_area, rectangle_area, triangle_area

area = 0
shape_choice = input("Choose one of the following shapes 1)Circle 2)Rectangle 3)Triangle")

if shape_choice.lower() == 'circle':
    radius = input("Please enter the radius of the needed circle")
    area = circle_area(radius=radius)

elif shape_choice.lower() == 'rectangle':
    length = input("Please enter the lenght of the needed rectangle")
    width = input("Please enter the width of the needed rectangle")
    area = rectangle_area(length=length, width=width)

elif shape_choice.lower() == 'triangle':
    height = input("Please enter the height of the needed triangle")
    base = input("Please enter the base of the needed triangle")
    area = circle_area(base=base, height=height)
else:
    print(f"Selected shape is not supported {shape_choice.lower()} - Please choose an item from the list")

print(f"Calculated area for {shape_choice} is {area}")

``` 

If we take a closer look at this design, we notice the following:
- What would happen when you need to add a new shape function? And where? --> __It will be added at the utility module, so you can import it anywhere in your code.__
- Imagine that you need to use same shape functions at another project. How would you do that? --> __You will simply import the utilities module by `import utilities` after having a clear path for module__.
- Integration with other team members will be easier, __each team member can start working on a different file.__